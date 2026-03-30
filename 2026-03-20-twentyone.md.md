# Devlog #1 — TwentyOne: Pure Blackjack

> A browser-based blackjack game built with React, designed to feel like it belongs on the App Store.

---

## Why I Built This

I've been on a streak of portfolio projects lately, and I wanted to build something that was actually fun to use — not just impressive on a resume. Blackjack felt like the perfect target. The rules are simple enough that I could focus on the experience rather than the game logic, but complex enough that there were real decisions to make around state management, animations, and UI flow.

The concept I kept coming back to was: what if a blackjack game felt like a premium iOS app? Not flashy casino neon. Not pixel art retro. Just clean, considered, and polished. Think Offsuit or Monument Valley — apps where the design itself is part of the enjoyment.

That became the north star for everything.

---

## The Tech Stack

The whole thing is built in **React**, bundled into a single deployable HTML file using **esbuild**. That last part was important — I wanted to be able to drop it on itch.io without any server, any backend, or any build step on the player's end. One file. Open in browser. Play.

A few highlights from under the hood:

- **Balance history graph** rendered in SVG — no chart library, just math and paths
- **localStorage persistence** so your balance carries over between sessions
- **Animated dealer resolution** — cards reveal sequentially with timing that actually builds tension
- **Keyboard shortcuts** for people who want to play fast
- **A shop system** for spending your winnings on upgrades

The single-file bundle approach via esbuild was a fun constraint to work within. It forced me to think carefully about dependencies and keep things lean.

---

## Design Decisions

The UI is heavily inspired by the aesthetic of **Offsuit: Texas Hold'em Poker** on iOS — that kind of dark, felt-less, modern poker app look. No green baize. No cartoon chips. Just typography, spacing, and color doing the work.

A few specific decisions I'm happy with:

**Dark base with high-contrast cards.** The game background is near-black, which makes the white card faces pop without needing any tricks. It also just looks good on any screen.

**Dealer resolution timing.** I spent more time on this than anything else. The cards flip one at a time with a slight delay between each, and the bust/win state doesn't appear until the last card settles. It sounds like a small thing but it changes the whole feeling of the game — you're actually watching, not just waiting for a result.

**The balance graph.** I wanted something that made your session feel meaningful beyond just the number. Seeing your balance arc over time — the ups, the downs, the tilt spiral — gives the game a kind of narrative that a plain counter doesn't.

**Mobile-first layout.** The whole thing is built to feel right on a phone screen first, then scale up gracefully on desktop. That influenced everything from button sizing to how the card table area is structured.

---

## The Branding

Naming a game is weirdly hard. I landed on **TwentyOne: Pure Blackjack** because it does exactly what it says. No gimmicks, no progression systems you didn't ask for — just blackjack, played cleanly.

For the logo, I knew I didn't want the usual casino kitsch — gold coins, dice, neon. I wanted something that could sit on an App Store page and look like it belonged there. The approach I took was an Apple-style app icon: squircle shape, matte black background, a card fan with an Ace of Hearts, and the number "21" sitting heavy in the corner in a tight 800-weight sans-serif.

The title lockup underneath keeps it simple — **TwentyOne** in a bold weight, a thin rule, and **Pure Blackjack** in a lighter gray below it. The kind of thing Apple does with product names and it always just works.

I generated the final assets as both SVG (for scalability) and PNG at 2x resolution for itch.io cover use.

---

## What's Next

The core loop is solid. Where I want to take it next:

- Refining the shop — right now it's functional but I want the upgrades to feel more meaningful
- Sound design — even subtle card flip sounds would add a lot
- A proper itch.io page with screenshots and a cover that matches the branding
- Eventually exploring a path to the iOS App Store, which was always the stretch goal

---

*Built with React, esbuild, and a lot of strong opinions about whitespace.*
