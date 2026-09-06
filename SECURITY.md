# Security

EMMA is sold on one promise — **nothing leaves your machine**. A security report
isn't a nuisance here; it's someone helping keep the only claim the product
rests on. Reports are welcome, credited, and answered by a human.

## Reporting a vulnerability

**Email `Gregorymoores@proton.me`.**

Please don't open a public issue for a security bug, and please give me a chance
to fix it before posting publicly.

If you'd rather encrypt it, send a first mail with no details and I'll reply
with a key.

Useful things to include, roughly in order of how much they help:

- **What an attacker gets**, and what they'd need to start — local user? another
  process on the machine? a page the user visits? a file or email they open?
- **The version** — Settings → About, or the `version` field of
  `http://127.0.0.1:8000/api/health`.
- **OS and how you installed her** — Windows `.exe`, macOS `.dmg`, Linux `.deb`
  or AppImage.
- **Steps to reproduce**, or a proof of concept. A rough sketch is fine. I'd
  much rather have a vague real bug than nothing.

### What to expect

| | |
|---|---|
| First reply | within **72 hours** |
| Assessment + a plan | within **7 days** |
| Fix for something serious | as fast as a release can be cut and shipped |
| Credit | your name or handle in the release notes, unless you'd rather not |

This is one person, not a company. That means no bureaucracy and a real answer —
but also that "72 hours" is a promise about **attention**, not about a fix being
ready. There's no paid bounty programme. If that ever changes it'll say so here.

## What's in scope

Anything in a released build: the app, the local API on `127.0.0.1:8000`, the
licence check, encryption at rest, the agentic "hands" and their confirmation
layer, Dream Mode, and the email and document features that take input from
outside your machine.

**Especially interesting**, because they're where untrusted data meets EMMA:

- Anything that makes her **talk to the network** when she shouldn't. The
  complete list of what *may* leave your machine, and every one of these is off
  or inert until the owner turns it on:
  **live mode** (web search, page fetches, and the browser tools, which are only
  available while it's on) · **the update check**, one anonymous request, off by
  default · **a spoken voice** you choose, downloaded once · **the voice-
  recognition model**, a one-time ~250MB download · **your email**, spoken
  directly to your own mail server if you connect it · **a non-default model
  engine**, if you configure one. The model itself is local by default.
  **Anything outbound that isn't on that list is a finding**, and so is anything
  on it that fires without the owner having enabled it.
- Anything that gets **past the confirmation layer** on the agentic actions —
  files, apps, commands.
- Anything reachable from an **email or an attachment** she reads (IMAP, since
  0.6.5), or a **document** you hand her. That's the one input a stranger can
  put in front of her without you choosing it.
- Anything that lets a **web page you visit** reach the local API. This is the
  classic one for a localhost app, and it is **partly** defended — read this
  carefully, because the gap is deliberate and it is where the real findings
  are:
  - **Defended:** a request carrying an `Origin` whose host isn't loopback is
    refused `403`, which covers every `fetch`/XHR and every form POST — that is,
    every cross-site *state-changing* call. The `Host` header must be loopback
    too, which closes DNS rebinding. **A bypass of either is a real finding.**
  - **Not defended:** a cross-site **plain GET**. A `<img src="http://127.0.0.1:8000/…">`,
    `<script>` or `<link>` on any page sends **no `Origin` header at all**, and
    requests with no Origin are allowed on purpose, because that is also what
    `curl` and legitimate local clients look like. **So anything reachable by GET
    alone is genuinely interesting**, including a flaw in the web framework
    underneath EMMA's own handlers rather than in her code.
  - This is not hypothetical: it is exactly how a `starlette` advisory
    (PYSEC-2026-2281) was reachable on Windows until **1.0.1**. *Listening only
    on loopback is not a defence against a page in your own browser.*
  - The candidate fix — refusing no-Origin requests that carry
    `Sec-Fetch-Site: cross-site`, which browsers send and `curl` does not — is
    known and not yet implemented.
- Anything that **mints or forges a licence**, or lets one machine's licence
  work where it shouldn't.

## Known and already public

Not vulnerabilities, but things people report and deserve a straight answer on:

- **The builds are unsigned.** Windows and macOS will warn you on first run. It
  means "unsigned", not "unsafe" — a certificate costs money that's currently
  going into the product instead. Every release publishes **SHA-256 checksums**
  in its notes, and the in-app updater verifies them before installing anything.
- **She never auto-updates.** She'll tell you a version exists; nothing is
  downloaded or replaced until you press the button.
- **Her memory is encrypted at rest** (AES-256, key in your OS keychain) from
  0.6.5 onward, and there's a recovery key you're asked to write down. If your
  keychain is ever reset, that written-down key is the only way back in — please
  actually save it.
- **A Windows credential-leak path, fixed in 1.0.1.** The web framework EMMA
  serves her own interface with had an advisory where, on **Windows only**, a
  crafted request could start an outbound connection before being rejected —
  enough to leak your Windows account credentials in a form that can be attacked
  offline. Reaching it needed a malicious page open in your browser while EMMA
  was running, and the cross-origin guard did not stop it (see the GET note
  above). **Update to 1.0.1 or later.** macOS and Linux were never affected.

## What I do on my side

- **A deep security scan every 60 days, without fail** — a standing rule since
  18 July 2026, not "when I get to it". Every runtime dependency audited, the
  full git history swept for committed secrets, and a reachability pass on
  every finding rather than a wall of CVE numbers.
- **The most recent was 2026-09-06**, run the day 1.1.0 shipped, because that
  release put three new libraries inside the installer for the first time — the
  speech engine and the runtime underneath it. Two things came out of it:

  - **`pypdf` shipped with a known flaw, and one of its three advisories was
    reachable.** A crafted PDF could make her chew CPU and memory while
    extracting text from it. It is a hang, not a breach — nothing runs, nothing
    leaks — and **nobody can post one in**: she lists the *names* of email
    attachments and never opens them, so it takes a PDF you hand her yourself.
    ✅ **Fixed in [1.1.1](https://github.com/LOOSEKEY/EMMA-releases/releases/tag/v1.1.1)**,
    published the same day it was found rather than held for a convenient
    moment. The other two advisories are not reachable from EMMA: one needs a
    document's outlines and one needs a *writing* path, and she does neither.
  - **The voice files she downloads aren't checked against a fingerprint.** The
    speaker-recognition model is (a pinned address plus a hash built into the
    app, so a compromised server can't make anything run). The spoken voices are
    not, and as of 1.1.0 those files are read by a much larger piece of
    machinery than before. Nobody can exploit that without taking over
    HuggingFace or breaking TLS, and it needs you to have chosen a voice — but
    it's a gap against the standard set everywhere else, and it's being closed.

  **No secret has ever been committed, across the whole history** — 445 commits,
  every branch — and the key that signs licences has never been in the
  repository at all.

- **The one before was 2026-09-01**, the morning after 1.0.0. It found the
  Windows advisory above, and separately that **web search had never actually
  worked in a shipped build** — the library was missing from the installer and
  the failure looked exactly like the internet being down. Both fixed and
  published the same day as **1.0.1**.
- **Anything that matters ships as a release**, with SHA-256 checksums in the
  notes, rather than waiting for a convenient moment.
- **Notices go up in `#security` on the [Discord](https://discord.gg/NEuWujf45u)**
  — what was found, what shipped, what to update. It's read-only: I post, nobody
  else can, so it can't become a place where a live vulnerability gets published
  before there's a fix. **Reports still go to email**, not to that channel.
  Findings are normally posted **after** the fix ships, which is the right way
  round; if something is ever urgent enough to say first, it will be said there
  first.

## Where the source is

EMMA is closed source; this repository carries the releases, the roadmap and
this policy. That doesn't narrow what you can report — everything above is about
shipped builds, which is what an attacker has too.

---

*Product and downloads: [ownemma.com](https://ownemma.com) · questions that
aren't security-sensitive are better in the
[Discord](https://discord.gg/NEuWujf45u).*
