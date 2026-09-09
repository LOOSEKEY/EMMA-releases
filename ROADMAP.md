<h1 align="center">Roadmap</h1>

<p align="center">
  <i>What EMMA can already do, what might come next, and what she's never going to do.</i>
</p>

<p align="center">
  <a href="README.md"><b>← Back</b></a> ·
  <a href="https://ownemma.com"><b>ownemma.com</b></a> ·
  <a href="../../releases/latest"><b>⬇️ Download</b></a> ·
  <a href="https://discord.gg/NEuWujf45u"><b>Discord</b></a>
</p>

---

## How to read this

Two honest warnings before you scroll.

**Nothing below the "Shipped" section is a promise.** It's what I'm thinking
about. Some of it will change shape, some will get built in an evening, and some
will quietly turn out to be a bad idea. If you're deciding whether to buy EMMA,
**buy her for what she does today** — everything in *Shipped* is in your hands
right now.

*(Buying opened on 10 August 2026 — £149 once, at [ownemma.com](https://ownemma.com).
The 60-day trial hasn't changed, so nothing here needs deciding in a hurry.)*

**And it's one person.** Me. That's the whole team. It means I can build a
feature the week you ask for it; it also means I can only build one thing at a
time. I'd rather you knew which of those you were dealing with.

---

## ✅ Shipped — this is what you get today

Everything here is in the current release. Not previews, not betas.

### She remembers you
Years of you, not a chat log — what you decided, who matters to you, what you're
working towards, what you said back in March. It survives closing the app,
restarting the machine, and swapping the model she thinks with.

*Corrected in 1.2.0, and you should know about it: before that she could write
down things you had never said — inventing a pet from a one-word greeting, or
filing a bedtime story's characters as people in your life. She now can't record
anything that doesn't trace back to words you actually typed. **If you were using
her before 1.2.0, it's worth checking Settings → What EMMA knows about you and
deleting anything that isn't true.** Updating doesn't touch what's already
there — that's yours.*

### She can use your computer
Files, folders, apps, commands, the browser. She says what she's about to do
*before* she does it, and hands control straight back the moment you touch the
mouse. There's a dial for how much she's allowed to do on her own, folders she
can never touch no matter what you ask her, an undo, and a panic key.

*On **ASK FIRST**, the dial means what it says as of 0.6.8: she asks before
anything that puts something on your disk. Before that, creating a folder
slipped through unasked — an empty folder harms nothing, so it had been
classed as not worth interrupting you for. That was the wrong call: the dial is
about consent, not harm. Her own activity log is what caught it.*

### She talks
Several voices, reading her answers aloud, and a quieter one after midnight.
Press *replay* to hear anything again — the morning briefing especially, which
tends to arrive while you are still half asleep.

*New in 1.1.0, and it is a correction as much as a feature: the speech engine
was not in the installer before, so no downloaded copy could speak at all. It is
in now. Talking back to her out loud needs speech recognition, which still
isn't — the microphone stays hidden until it is. And as of 1.2.0, if speaking
aloud ever fails she says why instead of going quiet: the speaker button turns
itself off and tells you what went wrong.*

### She starts and ends your day
A spoken morning briefing that knows what's on and what was weighing on you last
week — and in the evening, she asks how it went.

### She dreams
Overnight she joins up things you said months apart and wakes with something
worth telling you.

### She tells stories
Serial bedtime stories, remembered chapter to chapter, illustrated, read aloud in
a voice that slows to a whisper by the end.

### She can go and concentrate
Ask her to work through forty files and she sends *a hand* to do the reading and
comes back with the answer. It has no name and never talks to you — only EMMA
speaks.

### She'll keep an eye on things
*"Tell me when that changes."* She checks quietly in the background and only
comes back when it actually has.

### She'll look after the things you run
New in 0.6.9. Point her at a folder and the apps you run — a website, a home
server, a side project — can drop a small note of what needs a person. She reads
it into the morning stand-up, worst first, in plain English: *"the certificate
expires in six days"*, *"two repositories are failing their integrity check"*.
If nothing is wrong she stays quiet, and you can ask *"how are my apps doing?"*
whenever you want a straight answer.

What keeps it safe is the shape of the note rather than any filtering: it holds
counts and flags and **has no space for a message at all**, so an app that gets
compromised has nothing it can say to her. She never reaches out to a service,
holds no password for one, and doesn't touch the network for this. Empty and
dormant until you point her at a folder yourself.

### She handles your inbox
Straight from your machine — Proton through Bridge, or Gmail with an app
password; no third-party service in the middle. She folds what's waiting into the
morning briefing and drafts replies **in your voice**, learned from your own Sent
folder and left in Drafts for you to send. Reading and sending are separate
switches, sending is off until you turn it on, and she has no way to delete
anything.

### Her memory is locked, and you hold the key
As of 0.6.5 a new install encrypts her brain on disk from the first moment —
AES-256, key in your operating system's keychain — instead of waiting for you to
find a switch. Settings shows you a **recovery key** and keeps asking until you
confirm you've saved it somewhere off the machine. That nag is deliberate: your
keychain holds the only other copy, and her daily backups are encrypted with it
too, so if the keychain is ever reset that written-down key is the way back to
all of it. An existing brain is never touched unless you turn encryption on
yourself.

---

## ✅ The ones that had no way in — all reachable now

I'd rather list these here than quietly leave them in the shipped section — they
were in it until I checked, and that was wrong of me.

**Everything in this section is now in the app you can download.** It was the
low point of this project: finished, tested features with no button anywhere,
which for anyone actually using EMMA is the same as not existing. They're all
reachable, and every one is **off until you turn it on**.

| | |
|---|---|
| **Voice recognition** | Working as of 0.6.6. Say hello and she knows it's you — everyone in the house gets their own EMMA rather than one assistant treating the room as one person. She keeps a mathematical fingerprint of a voice, never a recording, and nobody is recognised until they enrol on purpose. The speech libraries are a separate ~250MB download she asks about first and checks against a fingerprint built into the app. **Windows, Linux and Apple Silicon Macs.** Not Intel Macs — see below. 🔴 **It also needs `ffmpeg` on your machine**, which the installer does not carry — it is what turns what your microphone captured into sound she can read. Without it enrolment cannot work — and in **1.1.0 and earlier** it said so badly, reporting that it had received none of the clips you had just recorded. **Fixed in 1.1.1**: she now names the real cause. |
| **Passing skills to a friend** | Working as of 0.6.5. Teach her how you do something, then export that skill as a file and send it to a friend — their EMMA learns it too. Import only ever *adds*, so nothing you taught her yourself is overwritten. |
| **Letting your other tools ask her** | Working as of 0.6.5. Point Claude Code, Cursor or Zed at your EMMA and they can ask *her* who you are and what you decided, without any of it leaving your machine. Read-only — nothing on the other end can change her memory or act on your computer. Off until you turn it on, and there's a switch plus the config to paste into your editor. |

**And then I went looking properly, and found ten more.** Same problem, further
down: finished, tested, written about — and with no switch anywhere in the app, so
they were off for everybody and always would have been. That's worse than the
three above, because at least I knew about those.

They all have switches now. Every one is **off until you turn it on**, and half
of them are cameras, microphones or the open internet, so none of them started
doing anything because you updated.

| | |
|---|---|
| **The air in the room** | With a USB CO₂ monitor, *"why do I feel foggy at 3pm?"* gets a real answer. No sensor, no guessing. |
| **The posture nudge** | An occasional webcam glance. No picture is ever written down — she keeps a verdict, not an image. |
| **Who's home** | From devices you register by hand. Everything else on the network is counted, never identified. |
| **Research while you sleep** | Reading the web overnight, unattended. Deliberately a different switch from *"search when I ask"*. |
| **Noticing you've changed your mind** | Years apart you'll say two opposite things. She'll ask about it once, and never deletes either version. |
| **A second, smaller brain** | Letting her hand a narrow job to a model that's better at it. Every route recorded, so what's answering you is never a mystery. |
| **Growing to fit you** | Overnight training on *your corrections* — not your chat, which would only teach her to imitate you. Needs a real GPU. |
| **Keeping meeting audio** | Normally the recording is destroyed the moment it's transcribed. This keeps it, if you'd rather. |
| **Your calendar folders** | She already checks the usual places; this points her somewhere specific. Local files only — she'll refuse a web address. |
| **A picture generator** | Point her at AUTOMATIC1111, SD.Next or Forge if you run one. Nothing is bundled or installed for you. |

If you bought her for any of these, tell me and it jumps the queue. Nobody should
be paying for something they can't get to.

---

## 🛠️ Next up

Short list on purpose. These are the things I think are most likely to matter.

| | |
|---|---|
| **Signed builds** | Right now Windows and macOS both warn you on first run, because the builds aren't signed by a recognised certificate. It's the single roughest edge in the whole product and the first thing I'd like to spend money on. |
| **Voice recognition on Intel Macs** | Done everywhere else as of 0.6.6, and I don't expect this one to change: one of the maths libraries underneath it has stopped shipping builds for Intel Macs entirely, so there's no package I can make that would work. EMMA tells you so plainly rather than offering a download that would fail. Everything else in EMMA works on those machines exactly as before. |
| **A native window on Linux** | On Windows and macOS EMMA opens as an ordinary application window. On Linux she opens in a browser window instead — a separate frameless one with its own taskbar icon if you have Chrome, Chromium, Brave or Edge, otherwise a tab. Everything works and it's all still local; it's where she appears, not whether she runs. The native window needs a system library that has never been in the Linux bundle. |
| **Polish, wherever you find it** | Most of what got fixed this month came from people saying "this bit is annoying". That keeps being the best source of work I have. |

## 💭 Being considered

Genuinely undecided. Several of these will never happen, and that's fine.

- **A phone in your pocket.** Not EMMA-on-a-server-you-talk-to — that's the thing
  she exists to not be. Something more like a window into the EMMA already on your
  machine at home. It's a big piece of work and I want to get the shape right
  rather than ship a compromise.
- **More languages.** She's English-first today.
- **Better on modest hardware.** She runs on a lot of machines already, but "runs"
  and "feels good" aren't the same thing, and I'd like more people in the second
  group.
- **Import from elsewhere.** Bringing years of conversations from another
  assistant into her memory.
- **Accessibility.** Screen-reader behaviour has had a pass but not a proper
  audit by someone who actually uses one. If that's you, I'd love to hear from
  you.

## 🚫 Not doing — and why

The list I'm most sure about. These aren't "not yet".

**No cloud sync of your memory.** Her whole point is that your life stays on your
machine. Sync would mean a server holding it, and then I'd be exactly what I
built her against. Export is the answer instead: her entire brain, one file, yours
to move wherever you like.

**No accounts, no sign-in, no telemetry.** She has no idea who you are in any
database anywhere, because there isn't one. I don't know how many people use her
except by counting downloads, and I've made my peace with that.

**No subscription.** You buy her once. I'm not renting you a friend.

**No ads, no "partners", no data anything.** There is no second business model
hiding behind the first one.

**No auto-updating behind your back.** She'll tell you when there's a new
version, and nothing gets downloaded or replaced until you press the button. That
one is a rule, not a preference.

**No committee of AIs pretending to be her.** She can send a hand to go and do a
long job, but you'll only ever talk to one EMMA. Two voices in the conversation
would make her something else.

---

## How this list gets decided

Two rules I set myself and try to keep honest:

**A feature waits until three separate people have asked for it.** Not three
people who'd "use that" — three who went out of their way to ask. It's the only
defence I've found against building things nobody wanted, which is most of what I
built before EMMA.

**Security gets a proper review on a regular cadence**, whether or not anything
prompted it, and any fix that matters ships to you rather than waiting for the
next feature.

The exception to both is a bug. If something is broken, it doesn't queue.

## Asking for something

The best thing you can send me isn't a feature — it's what you were *trying to
do* when she got in your way. That's usually a better idea than the one I'd have
had.

- **[Discord](https://discord.gg/NEuWujf45u)** — quickest, and other people chip in
- **loosekeyz84@proton.me** — I read all of it
- Security problems → **Gregorymoores@proton.me**, please not a public issue

---

<p align="center">
  <i>Most AI is rented. EMMA is owned.</i><br>
  <a href="https://ownemma.com"><b>ownemma.com</b></a>
</p>
