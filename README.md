<h1 align="center">EMMA</h1>

<p align="center">
  <b>A friend who lives on your computer, remembers your life, and never tells anyone.</b>
</p>

<p align="center">
  <a href="https://ownemma.com"><b>ownemma.com</b></a> ·
  <a href="../../releases/latest"><b>⬇️ Download</b></a> ·
  <a href="https://discord.gg/NEuWujf45u"><b>Discord</b></a> ·
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

🗣️ **She has a voice** — several. Talk hands-free, interrupt her mid-sentence
like you would a person, and she'll whisper after midnight.

💤 **She dreams** — overnight she joins up things you've said months apart, and
wakes with something to tell you.

📖 **She tells stories** — serial bedtime stories she remembers chapter to
chapter, illustrated, in a sleepy voice.

👨‍👩‍👧 **The whole house can have her** — kid mode with a bedtime and a PIN, study
mode, flashcards, and stories the children actually ask for. *(Telling voices
apart is built but not switched on yet — see the [roadmap](ROADMAP.md).)*

## Get her

### ⬇️ **[Download the latest release](../../releases/latest)**

| Platform | File | Install |
|---|---|---|
| **Windows** | `EMMA-Setup-*.exe` | Run it |
| **macOS** — Apple Silicon | `EMMA-*-arm64.dmg` | Open, drag to Applications |
| **macOS** — Intel | `EMMA-*-x86_64.dmg` | Open, drag to Applications |
| **Linux** — most people | `emma_*_amd64.deb` | `sudo apt install ./emma_*.deb` |
| **Linux** — portable | `EMMA-*.AppImage` | `chmod +x` and run |

> Not sure which Mac you have? **Apple menu → About This Mac.** "Chip: Apple M…"
> means Apple Silicon; "Processor: Intel" means Intel.

**You'll also need [Ollama](https://ollama.com)** — the local model engine EMMA
thinks with. Free, separate install. Her first-run setup checks whether you have
it, hands you the right installer, and carries on by itself once it's running.

Free for **60 days**, everything unlocked, no account and no card. If the trial
runs out before you've decided, she doesn't vanish or hold anything hostage — she
keeps talking, keeps remembering, and you can export every last thing she knows.

## Where the project is right now

Being straight with you, because I'd want the same:

- **She works.** Not a demo, not a waitlist. Download her and she runs — memory,
  acting on your machine, Dream Mode, the family features, all of it.
- **You can't buy her yet.** Payments aren't switched on — the last few steps are
  in progress. It'll be **£149 once, yours forever.** Until then she's free to use,
  and I'd rather people had her than sat on a list.
- **The builds are unsigned.** Windows and macOS will both warn you on first run
  (see below). A certificate costs money I'd sooner put into the product, and I'd
  rather tell you than let it surprise you.
- **Intel Mac support is brand new** — as of 0.6.3. Before that the site handed
  every Mac the Apple Silicon file, which simply wouldn't run on an Intel one. If
  that was you: sorry, and it's fixed.
- **It's one person.** Me. Support is a real human and usually quick, but I'm not
  a company and I'm not going to pretend to be one.

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

The one thing she'd ever download is the speech model for voice recognition —
about a quarter of a gigabyte, which is why it isn't inside the installer. She
asks first, tells you the size before anything starts, and checks what arrives
against a fingerprint built into the app before she'll use it. **Windows, Linux
and Apple Silicon Macs.** On an Intel Mac she'll tell you it isn't available and
leave the button alone — one of the libraries underneath it no longer builds for
those machines. Everything else in EMMA works there exactly as it does anywhere.

## What you'd actually own

£149 once, when buying opens. Not a subscription — I'm not renting you an AI.

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
