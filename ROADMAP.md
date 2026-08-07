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

### She can use your computer
Files, folders, apps, commands, the browser. She says what she's about to do
*before* she does it, and hands control straight back the moment you touch the
mouse. There's a dial for how much she's allowed to do on her own, folders she
can never touch no matter what you ask her, an undo, and a panic key.

### She talks
Several voices. Hands-free conversation, interrupt her mid-sentence like you
would a person, and a quieter voice after midnight.

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
| **Voice recognition** | Working as of 0.6.6. Say hello and she knows it's you — everyone in the house gets their own EMMA rather than one assistant treating the room as one person. She keeps a mathematical fingerprint of a voice, never a recording, and nobody is recognised until they enrol on purpose. The speech libraries are a separate ~250MB download she asks about first and checks against a fingerprint built into the app. **Windows, Linux and Apple Silicon Macs.** Not Intel Macs — see below. |
| **Passing skills to a friend** | Teaching her works today, in conversation. Saving one out as a file and handing it over is built and lands in the next release — export on each skill, and an import that only ever *adds*, so nothing you wrote is overwritten. |
| **Letting your other tools ask her** | Built, and it has a switch now — plus the config to paste into your editor. Next release. |

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
| **Buying her** | Payments aren't switched on yet — she's free to use meanwhile. |
| **Voice recognition on Intel Macs** | Done everywhere else as of 0.6.6, and I don't expect this one to change: one of the maths libraries underneath it has stopped shipping builds for Intel Macs entirely, so there's no package I can make that would work. EMMA tells you so plainly rather than offering a download that would fail. Everything else in EMMA works on those machines exactly as before. |
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
