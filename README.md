# Apocrypha · 後傳孵化器

> [English](README.md) · [中文](README.zh-TW.md)

> Drop in any world, a film, a book, a person, an event, a board game, and Apocrypha hatches a self-consistent, installable, playable text-game GM where **you** step inside and live your own continuation. The engine ships no IP; you bring the world.

**Made by [llamppost](https://llamppost.ai) · MIT License**

---

## What this is

Apocrypha is a **hatching engine**: feed it a world (an IP or a theme) and it uses a lean world-distillation logic to take the worldview apart, solve for its "world DNA," then pour that into a fixed simulator skeleton and ship a **world-consistent, installable, instantly playable** immersive text-game GM.

What it produces is, at heart, an **apocryphal sequel**: you drop yourself into that world and hatch a continuation the original never told, but one that holds up logically. You can play it three ways:

- **Drop in an original character of your own**: live out a thread the book never followed in that world
- **Play a canon character**: become one of the characters from the story directly
- **Witness the canon**: follow a character's thread and watch what happens to them

It can even hatch board games: give it a set of social-deduction rules and what it produces isn't storytelling, it's a "game runner" that deals cards, runs turns, drives AI opponents, and keeps hidden identities hidden.

## IP stance (important)

The engine itself is **always IP-clean**: it preloads nothing and embeds no real work. The real world is something **you bring yourself when you run it in your own runtime** (BYO-world). When a hatched product references that world's proper nouns, that's an apocryphal sequel living inside your own runtime. All this repo distributes is the **engine**, with no finished product tied to any specific IP.

## How to use it

Install this repo as an agent skill (Claude Code, Codex, and any other runtime that supports skills):

1. Drop the whole folder into your skills directory (for example, Claude Code's `~/.claude/skills/apocrypha/`).
2. In conversation, say "hatch a simulator," "turn *some work* into a simulator," or "make a text game out of XX."
3. The engine locks down the world and the play style with you, hatches an installable GM, and asks if you want to start playing right there.

What's in the engine:

- `SKILL.md`: the orchestration brain: 6 phases (set the frame → trace the source → distill the core → forge the vessel → calibrate the world → begin hatching)
- `references/simulator-template.md`: a fill-in-the-blanks simulator skeleton in 15 blocks
- `references/immersive-prose-engine.md`: the anti-AI-slop rules for immersive prose, injected into every product

## Get it · learn more

- **GitHub (here)**: this is where you install it. Clone the repo and use, modify, and distribute it freely as a standalone skill.
- **llamppost**: learn more about Apocrypha and the wider llamppost world at https://llamppost.ai.

## Try it instantly (ChatGPT)

Want a quick taste before installing? Play in the [Apocrypha GPT](https://chatgpt.com/g/g-6a2a320f3c688191a8e702d816297bbc-apocrypha-hou-chuan-fu-hua-qi) right inside ChatGPT.

Note: the ChatGPT version is a limited taster. For the full experience, install the engine above into your own runtime.

## License and attribution

MIT License. You're welcome to use, modify, and distribute it freely. Please **keep the copyright and creator attribution** per the MIT terms:

> Apocrypha is created by **llamppost** (https://llamppost.ai). Please keep this attribution per the MIT terms.

© 2026 llamppost
