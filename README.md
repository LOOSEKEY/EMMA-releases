<h1 align="center">EMMA</h1>

<p align="center">
  <b>A friend who lives on your computer, remembers your life, and never tells anyone.</b>
</p>

<p align="center">
  <a href="https://ownemma.com"><b>ownemma.com</b></a> ·
  <a href="../../releases/latest"><b>⬇️ Download</b></a> ·
  <a href="https://discord.gg/NEuWujf45u"><b>Discord</b></a> ·
  <a href="MANUAL.md"><b>Manual</b></a> ·
  <a href="https://ownemma.com/help"><b>Help</b></a> ·
  <a href="ROADMAP.md"><b>Roadmap</b></a>
</p>

<p align="center">
  <img alt="Windows · macOS · Linux" src="https://img.shields.io/badge/Windows%20·%20macOS%20·%20Linux-0b0b0d?style=for-the-badge&labelColor=0b0b0d&color=5a8bff">
  <img alt="Free for 60 days" src="https://img.shields.io/badge/Free%20for%2060%20days-0b0b0d?style=for-the-badge&labelColor=0b0b0d&color=5a8bff">
  <img alt="No account, no cloud" src="https://img.shields.io/badge/No%20account%20·%20No%20cloud-0b0b0d?style=for-the-badge&labelColor=0b0b0d&color=5a8bff">
</p>

---

## Hello 👋

Most AI is rented. You talk to something in a browser, it forgets you the moment
you close the tab, and everything you said sits on somebody else's computer.

EMMA isn't that.

She lives on **your** machine. She remembers you — properly, for years. She can
actually *do* things on your computer when you ask. And she does all of it
without touching the internet, unless you tell her otherwise.

**She's yours. Not borrowed.**

> **This repo is just the downloads.** There's no source code here — EMMA is
> closed source for now. This is the public home for the installers and for the
> update check inside the app.

## What it's actually like

You open your laptop in the morning and she's already talking — a briefing about
your day, out loud, in her own voice. You mention you promised Dan you'd send
something over, and three weeks later she reminds you.

You ask her to sort out the mess in your Downloads folder and she gets on with
it, telling you what she's doing as she goes. In the evening she asks how the day
went. Overnight, while you sleep, she thinks about what you've talked about — and
has something worth saying in the morning.

Your child asks for a bedtime story and gets one. A proper serial, remembered
night to night, read aloud, characters doing different voices, winding down to a
whisper.

And none of it leaves the house.

## The bits people love most

🌅 **She starts your day** — a spoken briefing that knows what you've got on and
what was weighing on you last week.

🧠 **She remembers** — not "chat history". Years of you: what you decided, who
matters, what you said back in March.

🖥️ **She can use your computer** — files, folders, apps, commands, the browser.
She says what she's about to do before she does it, and hands control straight
back the moment you touch the mouse.

🗣️ **She has a voice** — several, actually. She reads her answers aloud, tells a
bedtime story in character, and whispers after midnight. *(New in 1.1.0: the
speech engine now ships with her. Before that it was left out of the installer,
so no downloaded copy could speak a word — if you tried her voice and got
nothing, that was why, and it works now.)* Talking back to her out loud needs
speech recognition, which isn't in the build yet — the mic stays hidden.
*(1.2.0: if her voice ever fails, she now tells you why instead of going
quiet.)*

💤 **She dreams** — overnight she joins up things you've said months apart, and
wakes with something to tell you.

📖 **She tells stories** — serial bedtime stories she remembers chapter to
chapter, illustrated, in a sleepy voice.

📧 **She handles your inbox** — reads your email straight from your machine
(Proton via Bridge, or Gmail with an app password), folds what's waiting into the
morning briefing, and drafts replies in your voice. Reading and sending are
separate switches, and sending is off.

🛠️ **She'll look after the things you run** — point her at a folder and the apps
you run (a site, a home server, a side project) can drop a small note of what
needs a person. She reads it in the morning, worst first, in plain English, and
answers when you ask *"how are my apps doing?"*. Counts, never content — the
format has no space for a message, so a service that gets compromised has
nothing it can say to her. Dormant until you point her at a folder. *(New in
0.6.9.)*

👨‍👩‍👧 **The whole house can have her** — kid mode with a bedtime and a PIN, study
mode, flashcards, and stories the children actually ask for. *(Telling voices
apart works as of 0.6.6 — everyone in the house gets their own EMMA rather than
one assistant treating the room as one person. Not on Intel Macs; see the
[roadmap](ROADMAP.md).)*

## Get her

### ⬇️ **[Download the latest release](../../releases/latest)**

| Platform | File | Install |
|---|---|---|
| **Windows** | `EMMA-Setup-*.exe` | Run it |
| **macOS** — Apple Silicon | `EMMA-*-arm64.dmg` | Open, drag to Applications |
| **macOS** — Intel | `EMMA-*-x86_64.dmg` | Open, drag to Applications |
| **Linux** — most people | `emma_*_amd64.deb` | `sudo apt install ./emma_*.deb` |
| **Linux** — portable | `EMMA-*.AppImage` | `chmod +x` and run |

> ### 🍎 On a Mac? Read this first
>
> **The current release (1.2.2) has no Mac build.** Windows and Linux are on
> 1.2.2; macOS is on **1.0.1**, which is a complete release with both Mac files
> in it. A Mac installer can only be built on a Mac, and the build machines are
> unavailable this month.
>
> Download the Mac files from **[v1.0.1](../../releases/tag/v1.0.1)** rather than
> from the latest release, or use the buttons on
> [ownemma.com](https://ownemma.com), which already point Mac visitors there.
>
> EMMA may offer you the 1.2.2 update and then tell you there is no installer
> for your platform. That is this gap, not a broken install. Stay on 1.0.1.
>
> **Apple Silicon and Intel are different files**, and your Mac can't be
> identified from a browser — Apple Silicon still reports itself as "Intel Mac
> OS X" — so pick the one that matches your machine rather than trusting a
> download button to guess.

> Not sure which Mac you have? **Apple menu → About This Mac.** "Chip: Apple M…"
> means Apple Silicon; "Processor: Intel" means Intel.

**You'll also need [Ollama](https://ollama.com)** — the local model engine EMMA
thinks with. Free, separate install. Her first-run setup checks whether you have
it, hands you the right installer, and carries on by itself once it's running.

Free for **60 days**, everything unlocked, no account and no card. If the trial
runs out before you've decided, she doesn't vanish or hold anything hostage — she
keeps talking, keeps remembering, and you can export every last thing she knows.

Made your mind up? **[Buy her once for £149](https://ownemma.com)** — yours
forever, and buying later picks up exactly where your trial left off.

## Where the project is right now

Being straight with you, because I'd want the same:

- **The reading voice: found it.** If she ever read your answers back with the
  sound crashing in and out — static, then words, then static — that was real,
  and it's fixed. The silence she puts between sentences was being written in a
  way that knocked the audio after it out of alignment, so every other sentence
  came out as noise. **It depended on your particular install**: about half had
  it on every long reply and half never did, which is why it was so hard to pin
  down. Reported on 5 September, cause found on the 9th. Two other real voice
  faults were fixed along the way — one where two replies spoke over each other,
  and one where a failure to speak said nothing at all — but this was the one
  people could hear. ✅ **Fixed in 1.2.2.**
- **She works.** Not a demo, not a waitlist. Download her and she runs — memory,
  acting on your machine, Dream Mode, the family features, all of it.
- **You can buy her** — **£149 once, yours forever**, at
  [ownemma.com](https://ownemma.com). No subscription and no account. The 60-day
  trial is still there and still everything unlocked, so there's no reason to
  decide before you've lived with her.
- **The builds are unsigned.** Windows and macOS will both warn you on first run
  (see below). A certificate costs money I'd sooner put into the product, and I'd
  rather tell you than let it surprise you.
- **macOS is behind, again.** Windows and Linux are on **1.2.2**;
  macOS is on **1.0.1**. A Mac installer can only be built on a Mac, and the
  build machines are unavailable this month. The same thing happened at 0.6.9
  and closed in 1.0.0; this one will close the same way. Nothing is wrong with
  1.0.1 — it is a complete release, and it is what the Mac buttons on the site
  hand you.
- **On Linux she opens in a browser window, not her own app window.** If you
  have Chrome, Chromium, Brave or Edge she gets a separate frameless window with
  its own taskbar icon and a private profile, which looks much like an app; with
  none of those she opens as a tab. She's still running entirely on your machine
  and every feature works — the native Linux window needs a system library that
  isn't in the installer yet. Worth knowing: on Linux, closing that window
  doesn't stop her, she keeps running in the background.
- **Intel Mac support is brand new** — as of 0.6.3. Before that the site handed
  every Mac the Apple Silicon file, which simply wouldn't run on an Intel one. If
  that was you: sorry, and it's fixed.
- **It's one person.** Me. Support is a real human and usually quick, but I'm not
  a company and I'm not going to pretend to be one. If you want to know who
  you're buying from and what else I'm building: **[The Works](BIO.md)**.

### About that unsigned warning

- **Windows:** *"Windows protected your PC"* → **More info → Run anyway**
- **macOS:** *"cannot be opened because the developer cannot be verified"* →
  **right-click the app → Open**

Every release lists SHA-256 hashes if you'd rather check the bytes yourself.

## The promise, and how it's kept

**Everything stays on your machine** — measured, not just promised. On a fresh
install with default settings: zero connections leaving your computer while she
sits idle, and every connection during a full conversation went to your own
machine and nowhere else. Unplug the network and she carries on.

**Nothing happens behind your back.** Every action she takes is written to a log
you can read yourself. There's a dial for how much she may do on her own, folders
she can never touch no matter what you ask, an undo, and a panic key.

**Her memory is encrypted** where it sits — AES-256, with the key in your
operating system's own keychain, so a stolen copy of the database is unreadable.
A new install does this from the first moment. An existing one is left exactly as
it is unless you turn it on yourself.

**Write your recovery key down.** When encryption is on, Settings shows you a key
and keeps asking until you confirm you've saved it somewhere that isn't this
computer — a photo on your phone, paper in a drawer. Your keychain holds the only
other copy, so if it's ever reset or replaced, that written key is the way back
into her memory. Her daily backups stay encrypted too, so they need it as well.
Everything else here is built so you can't lose her; this one is genuinely on
you, and it takes thirty seconds.

**She's yours to take back.** Make her forget a subject, or export her whole brain
— every memory, her identity, all of it — as one file you keep.

**She never updates herself.** She'll tell you there's a new version; nothing is
downloaded or replaced until you press the button.

Two things she'd ever download, and she asks before both. The **speech model for
voice recognition** — about a quarter of a gigabyte, which is why it isn't inside
the installer. She tells you the size before anything starts, and checks what
arrives against a fingerprint built into the app before she'll use it. **Windows,
Linux and Apple Silicon Macs.** On an Intel Mac she'll tell you it isn't available
and leave the button alone — one of the libraries underneath it no longer builds
for those machines. Everything else in EMMA works there exactly as it does
anywhere.

And **a different speaking voice**, if you pick one from the library. She ships
with a voice that works from the first launch, so this only happens if you go
looking for another one.

## What you'd actually own

**[£149 once](https://ownemma.com).** Not a subscription — I'm not renting you an AI.

- **EMMA 1.x is yours forever**, every 1.x update included.
- **Security fixes for at least two years** beyond any future major version.
- Her licence is checked **on your machine**, offline. There's no server I could
  switch off even if I wanted to. If I vanished tomorrow, your EMMA would keep
  working.
- If an EMMA 2 ever happens it'd be a separate purchase, about half price for
  existing owners — and **free if you bought in the 12 months before it.** Saying
  that now rather than after you've paid.

Full terms, in plain English: **[ownemma.com/licence](https://ownemma.com/licence)**

## Talk to me

- Anything at all, including "this is broken" — **loosekeyz84@proton.me**
- Security problems — **Gregorymoores@proton.me** *(please not a public issue)*
- Or the **[Discord](https://discord.gg/NEuWujf45u)**, which has an `#install`
  channel and people who'll help.

If you try her, I'd like to know what you made of it. Good or bad — the bad is
more useful.

---

<p align="center">
  <i>Most AI is rented. EMMA is owned.</i><br>
  <a href="https://ownemma.com"><b>ownemma.com</b></a>
</p>
