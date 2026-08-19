# EMMA — the user manual

*Everything she does, and where to find it. For v0.6.8.*

This is the reference. If you're **installing her for the first time**, or
something is **broken**, start at [ownemma.com/help](https://ownemma.com/help)
instead — that's the short version with the fixes in it.

---

## Contents

1. [The window](#1-the-window)
2. [The top bar](#2-the-top-bar)
3. [Talking to her](#3-talking-to-her)
4. [What she remembers](#4-what-she-remembers)
5. [Letting her use your computer](#5-letting-her-use-your-computer)
6. [Her world — all the panels](#6-her-world--all-the-panels)
7. [Settings](#7-settings)
8. [Dream Mode](#8-dream-mode)
9. [Everyone else in the house](#9-everyone-else-in-the-house)
10. [Your email](#10-your-email)
11. [Letting your other tools ask her](#11-letting-your-other-tools-ask-her)
12. [Backups, moving machines, leaving](#12-backups-moving-machines-leaving)
13. [Where her files actually live](#13-where-her-files-actually-live)
14. [Trial, licence, updates](#14-trial-licence-updates)
15. [Getting a human](#15-getting-a-human)

---

## 1. The window

Three things, and that's the whole app:

- **The conversation** — the middle. Type at the bottom, press Enter.
- **The top bar** — the dials and switches that decide how she behaves.
- **Her world** — the ☰ menu on the right. Every panel lives in there.

Nothing is hidden in a right-click menu. If you can't find something, it's in
**Her world**.

She runs entirely on your machine. The model doing the thinking is
[Ollama](https://ollama.com), installed separately, running locally. There is no
account and no server — which is also why **she is exactly as capable as your
hardware lets her be**. That's the trade.

---

## 2. The top bar

Left to right:

| Control | What it does |
|---|---|
| **Chats** | Your conversation threads — pick one up again, or browse back |
| **Clear chat** | Starts a fresh thread. Your **memory is untouched** — this clears the screen, not what she knows |
| **Memory** | What she knows about you — see §4 |
| **Notifications** | What she did while you were away |
| **Dreams** | Overnight thinking — see §8 |
| **Careful mode** | She double-checks her answers before replying. Slower, better on anything that matters. |
| **Safety dial** | How much she may do to your computer without asking — see §5 |
| **Spine dial** | How much she pushes back — see below |
| **Live mode** | Off by default. On, she may search the web and read pages. |
| **Sanctuary mode** | Hides everything, instantly, when you lend someone your machine. `Alt+Shift+S` |
| **Model picker** | The model she's thinking with. Warns you honestly when one is too big for your hardware. |
| **☰ Her world** | Everything else — see §6 |

### The spine dial

Click to cycle. This is tone, not capability:

- **Agreeable** — leans towards support, rarely pushes back.
- **Candid** *(default)* — honest with you, and will disagree, kindly.
- **Challenging** — argues her side and holds her ground, with receipts.

---

## 3. Talking to her

**Type** in the box and press Enter. **Stop** appears while she's working — press
it and she stops mid-sentence.

**Voice.** Turn it on in Settings → *Her voice*. You can talk hands-free and
interrupt her mid-sentence, like you would a person. She has several voices, and
she'll drop to a whisper late at night.

**Files.** Drag a document, image, audio or video file into the conversation and
ask about it.

### The two commands worth knowing

```
/papercut the drawer scrollbar was hidden on my screen
```

Logs something that annoyed you. No model call, nothing sent anywhere — it just
writes a line to a file on your disk. `/pc` is the short form.

```
/papercuts
```

Shows everything you've logged, bundled with your OS, hardware and version, and a
**Copy all** button. Paste that into an email and it's the single most useful
thing you can send.

**Small annoyances are exactly what's wanted.** Big bugs get found. It's the
"this felt off and I can't say why" ones that can't be seen from the inside.

---

## 4. What she remembers

Open the **memory** panel in the top bar. It isn't a black box — you can read all
of it, edit it, and delete it.

| Section | What's in it |
|---|---|
| **Things I want to check** | Memories that may have stopped being true. Appears only when she has a question. |
| **What EMMA knows about you** | The facts she's gathered. Add your own, delete any. |
| **Who EMMA is becoming** | Her notes on herself |
| **Soul File** | Her entire brain as one file — **Export brain** or **Import…**. She also keeps a quiet daily copy of the whole thing (the last 7), and **Back up now** takes one on the spot. |
| **Forget** | Two ways to make her forget, below |

*Looking for everything ever said? That's two other places: **Chats** in the top
bar for your threads, and **Her world → Search** to search across years.*

### Things I want to check

A memory that's years old has one failure mode nothing else does: it remembers
things that **stopped being true**. You moved. You quit. You changed your mind.

So she reads back over what she knows while you sleep, and when two things
collide she raises it — *"you told me you were vegetarian last year, still
true?"* — with both versions shown side by side. **She asks; she never edits.**
She can't know which one is right, so she doesn't guess.

Three answers, and *"both are true"* is a real one — people genuinely do contain
multitudes. Answering is the only place in EMMA where a fact is forgotten
because *you* said so.

### Making her forget

- **Forget everything about…** — name a topic, and she shows you *exactly* what
  would go before anything is deleted. Nothing disappears before you've seen the
  list.
- **Forget the last hour** — for when you said something you'd rather she didn't
  keep.

### Encryption

Settings → **Encrypt memory at rest**. AES-256, key held in your operating
system's keychain.

> ⚠️ **Write your recovery key down.** When you switch encryption on she shows
> you a recovery key once and asks you to confirm you've saved it. It is the only
> way back into your own memory if the keychain entry is ever lost or
> overwritten. Keep it somewhere that isn't this computer.

---

## 5. Letting her use your computer

She can read files, write files, run commands, and drive a browser. The **safety
dial** in the top bar decides how much of that happens without your say-so. Click
it to cycle:

| Position | What happens |
|---|---|
| **Full** | She acts, then tells you what she did. Fastest. |
| **Ask** | Anything that changes your system stops and waits for your Allow / Deny. |
| **Lock** | She touches nothing. Conversation only. |

**"Changes your system" means changes your system** — writing a file, creating a
folder, running a command. Not a judgement about whether it's harmful.

Two things sit **above** the dial and apply even on Full:

- **Protected paths** — SSH keys, GPG, cloud credentials. Refused at every dial
  position, no exceptions. Add your own in Settings → *Protected paths*.
- **The audit log** — everything she does, in a tamper-evident chain, readable
  line by line under **Her world → Activity**.

And two ways back:

- **Stop** — halts her mid-task.
- **Undo** — reverses file changes she made. In **Her world → Activity**, under
  *Reversible changes*.

**Watch me (computer use)** in Settings lets her see and drive the screen. She
says what she's about to do before she does it, and hands control straight back
the moment you touch the mouse.

---

## 6. Her world — all the panels

Everything under the ☰ menu, in menu order:

| Panel | What it's for |
|---|---|
| **Activity** | Every action she's taken, filterable by tool and outcome |
| **Search** | Everything ever said, across years |
| **Documents** | Files you've given her to keep and reason over |
| **Goals** | Goals and projects she tracks with you |
| **People** | Who matters to you, and what she knows about them |
| **Meetings** | She attends the call and writes the minutes |
| **Journal** | Reflect with her, with prompts |
| **Your style** | How you like her to write — learned, and editable |
| **Your story** | The biography she drafts from memory |
| **Story time** | The Bookshelf and the Story Board — serial bedtime stories |
| **Tutor** | Study mode and flashcards |
| **Transcripts** | Drop an audio file, get it transcribed |
| **Podcast** | A two-voice audio overview she makes of anything |
| **Photos** | Find a picture by describing it |
| **Video** | Drop a video and ask her about it |
| **Letters** | A time capsule to your future self, her yearly letter to you, and the almanac — predictions for the year, sealed until next January |
| **Rehearsal room** | Practise the hard conversation — she plays the other person, then steps out of it and tells you honestly how you did. Or "argue me out of this", and she takes the other side properly. Nothing said in here is remembered. |
| **Skills** | What she's learned to do. The **⤓** on a row exports that one as a file, and a friend's EMMA can import it. People swap them in Discord `#skills`. A skill from someone else waits for you to read it before she'll use it. |
| **Standing orders** | Tasks she runs on her own, on a schedule |
| **Insights** | Patterns in what she's been doing |
| **Models** | Install, remove and switch models |
| **Settings** | See §7 |
| **MCP connections** | See §11 |

---

## 7. Settings

**Her world → Settings.** Everything below is off unless you turn it on, and
this is the order you'll meet them in on screen.

### The top of the panel

- **How she looks** — dark or light, and the colour she's drawn in.
- **Her voice** — which voice she speaks in.
- **Family voices** — a voice per person. Consent is required and recorded.
- **Kid mode** — a restricted EMMA with a bedtime. See §9.
- **Encrypt memory at rest** — AES-256, and your recovery key. See §4.
- **Let her remember the screen** — she can see what's on it.
- **Let her hear the room** — ambient listening, with a *Forget what she's
  holding* button.
- **Check for updates** — see §14.
- **License** — your key, and what's left of your trial. See §14.
- **Watch me (computer use)** — lets her see and drive the screen. She says what
  she's about to do before she does it, and hands control straight back the
  moment you touch the mouse.
- **Knowing who's speaking** — she recognises enrolled voices and greets each
  person as themselves. Needs a one-time voice-model download (about a quarter of
  a gigabyte, checksummed, and only fetched when you click). Not available on
  Intel Macs.
- **Let your other tools ask her** — see §11.

### Her senses

- **The air in the room** — plug in a USB CO₂ monitor and *"why do I feel foggy at
  3pm?"* gets a real answer. No sensor, no guessing.
- **The posture nudge** — an occasional webcam glance. No frame is ever written
  down.
- **Who's home** — from devices you registered by hand. Everything else on the
  network is counted, never identified. Optionally goes discreet when a guest
  arrives.

### What she may do without asking

- **Research while you sleep** — deliberately a separate consent from "search when
  I ask", because they're different questions.
- **Notice when you've changed your mind** — she'll ask about it once, and never
  deletes either version.
- **Use a second, smaller brain** for narrow jobs, with every route recorded.
- **Let her grow to fit you** — overnight training on your corrections, never on
  your chat.
- **Keep meeting recordings** — normally the audio is destroyed the moment it's
  transcribed.

### Where she looks

- **Calendar folders** — point her at local `.ics` files and the morning briefing
  finally knows your real day. A web address is refused, not quietly ignored.
- **Picture generator** — point her at AUTOMATIC1111, SD.Next or Forge if you run
  one.

### Your email

- **Let her read your email** and **Let her send email as you** — two separate
  switches, and sending is off. See §10.

### Protected paths

Folders she may never touch, at any dial position. Credentials and key stores are
in there already. Add your own.

---

## 8. Dream Mode

Turn it on before bed. Overnight she goes back over what you've talked about,
joins up things you said months apart, and has something worth saying in the
morning.

Everything is in the **Dreams** panel in the top bar. The switches, in order:

- **Dream Mode** — the master switch. She sleeps on the day when you open her in
  the morning.
- **Dream journal** — she also writes a short, surreal entry. She's allowed to be
  weird in here.
- **Mood** — she gently senses the emotional tenor of your days. Private, and
  never shown to anyone.
- **Rituals** — a morning stand-up and an evening wind-down card, bookending your
  day.
- **Dream automatically overnight, around ‹hour›** — so she's already dreamt
  when you wake, rather than dreaming while you wait. This runs while EMMA is up;
  to dream with the window closed, install the background service
  (`desktop/install.sh --service`).
- **Whisper after dark** — softens her spoken replies between the hours you set.
- **Sleep on it now** — don't wait for tonight.

And what she leaves you:

- **On this day** — what was happening a year ago
- **Sleep on a problem** — hand her something before bed, get her thinking on it
- **What EMMA's wondering about you** — the questions she's sitting with
- **Mood over time** — yours, across the year
- **Dream journal** — what she actually thought about
- **Past briefings** — every morning briefing she's given you

It's the strangest thing she does and the thing most people end up liking most.

---

## 9. Everyone else in the house

EMMA is one being with many relationships — not one shared account.

- **Family voices + voice recognition** — say hello and she knows who you are, and
  greets you like it. Everyone gets their own memories, not one shared assistant
  treating the room as a single person. Nobody is recognised until they've
  enrolled themselves on purpose; she keeps a mathematical fingerprint of a voice
  and never a recording.
- **Kid mode** — a restricted EMMA with a bedtime. Restriction is the resting
  state: she starts restricted and stays that way until an adult says otherwise.
- **Sanctuary mode** (`Alt+Shift+S`) — for lending someone your laptop. Everything
  goes discreet at once.

---

## 10. Your email

Settings → **Your email**. Off until you turn it on.

She talks to your mail server directly from this machine over IMAP — no OAuth
app, no consent screen, no third party in the loop:

- **Proton** — through Proton Bridge on `127.0.0.1`, so nothing leaves your
  computer. *(Bridge needs a paid Proton plan.)*
- **Gmail** — on an app password.
- **Something else** — any IMAP server.

Passwords go into your OS keychain, never into a settings file.

**Reading and sending are two separate switches, and sending is off.** With
reading on, she triages what's waiting into your morning briefing. With sending
on, she writes replies **in your voice** — learned from your own Sent folder —
and files them to **Drafts**. She has no way to delete anything.

> Email is the first thing a stranger can put in front of her without you
> choosing it. That's why it's two switches instead of one.

---

## 11. Letting your other tools ask her

Settings → **Let your other tools ask her**, or **Her world → MCP connections**.

Point Claude Code, Cursor or Zed at your EMMA and they can ask *who you are* —
your facts, your style, your projects — and the answer never leaves your disk.
It's **read-only**, and the panel shows you exactly what they'll be able to ask
before you switch it on. There's a **Copy config** button for your editor's MCP
settings.

---

## 12. Backups, moving machines, leaving

**Memory → Export Soul File** gives you her entire brain as a single file you own.
That one file is your backup, your migration, and your exit.

- **Backing up** — she takes automatic backups, and you can export whenever you
  like.
- **Moving to a new machine** — export on the old one, install on the new one,
  import.
- **Leaving** — export, then uninstall like any other app. Nothing is held back
  and nothing is kept anywhere else, because there is nowhere else.

**Your export always works** — during the trial, after it expires, whatever
happens. Your memory is never held hostage to a payment.

---

## 13. Where her files actually live

| System | Folder |
|---|---|
| **Windows** | `%APPDATA%\EMMA` |
| **macOS** | `~/Library/Application Support/EMMA` |
| **Linux** | `~/.local/share/EMMA` |

Her memory is `emma.db` in there. Set `EMMA_DATA_DIR` to put it somewhere else.

---

## 14. Trial, licence, updates

**60 days, everything unlocked, no account.** When it ends she becomes a
read-only companion — still talking, export still working, **nothing deleted**.
Buy six months later and everything she remembered is still there.

**£149 once, yours forever.** Your key arrives by email straight after checkout.
Your licence is checked on your own machine, with no server involved. **14-day
no-questions refund.**

**Updates never happen on their own.** Settings → *Check for updates* → **Check
now**. If there's one, pressing **Update** downloads the installer, checks it
against the checksum published in the release notes, and starts it. On Windows
and the Linux AppImage she closes and comes back on the new version; a `.deb` or
a Mac `.dmg` opens in your own system's installer for you to finish. She will
never update herself behind your back.

---

## 15. Getting a human

Both of these reach the person who built her:

- **[The EMMA Discord](https://discord.gg/NEuWujf45u)** — install help in
  `#install`, skills people are passing around in `#skills`, everything else in
  `#chat`. Fastest, and someone else may have hit the same thing.
- **loosekeyz84@proton.me** — anything at all, including "this is broken".

Security problems: **Gregorymoores@proton.me**, and please not a public issue.

There's no support desk. It's one person, and he reads everything.
