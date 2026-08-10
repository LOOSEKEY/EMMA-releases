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

- Anything that makes her **talk to the network** when she shouldn't. Nothing
  should leave your machine except the model you chose and an update check you
  can switch off.
- Anything that gets **past the confirmation layer** on the agentic actions —
  files, apps, commands.
- Anything reachable from an **email or an attachment** she reads (IMAP, since
  0.6.5), or a **document** you hand her. That's the one input a stranger can
  put in front of her without you choosing it.
- Anything that lets a **web page you visit** reach the local API. This is the
  classic one for a localhost app and it's specifically defended — she refuses
  browser-borne cross-origin requests and validates the `Host` header — so a
  bypass is a real finding.
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

## Where the source is

EMMA is closed source; this repository carries the releases, the roadmap and
this policy. That doesn't narrow what you can report — everything above is about
shipped builds, which is what an attacker has too.

---

*Product and downloads: [ownemma.com](https://ownemma.com) · questions that
aren't security-sensitive are better in the
[Discord](https://discord.gg/NEuWujf45u).*
