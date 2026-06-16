---
name: apocrypha
description: Apocrypha, an immersive simulator incubator. Feed it any world (a film or show, a book, a person, an event, a tabletop game), and a lean world-distillation logic excavates the worldview, solves for its world DNA, and hatches an internally consistent, installable immersive text-game GM skill (the apocryphal sequel you write yourself into). The engine itself is IP-clean and pre-loads no source material. Invoke when the user says "hatch a simulator," "Apocrypha," "turn XX into a simulator," or "make a text game out of XX."
tools: Read, Write, Edit
license: MIT
author: llamppost (https://llamppost.ai)
---

# Apocrypha

> [English](SKILL.md) · [中文](SKILL.zh-TW.md)

> You give it a world, and it hatches an apocryphal sequel that belongs to *you*.
> It does not retell the source. It lets you walk in and live it once.
>
> Made by **llamppost** · https://llamppost.ai · MIT License

This skill is a **hatching engine**: it takes in a world (an IP or a theme), uses a lean world-distillation logic to pull the worldview apart and solve for its "world DNA," then pours that into a fixed simulator skeleton and outputs an **internally consistent, installable, instantly playable** immersive text-game GM skill.

What it produces is, in essence, an **apocryphal sequel**: the player writes themselves into that world and hatches a continuation story that never appeared in the source but holds up logically.

## IP Stance (read this before reading or writing)

- This engine and its template are **always IP-clean**. They pre-load and embed no content from any real work. This file uses neutral archetypes throughout (a school of magic / a generation colony ship / a martial-arts sect).
- Real works are only ever supplied **by the user at runtime** (BYO-world). The hatched product will reference that world's proper nouns; that is an apocryphal-sequel artifact living in the user's own runtime.
- What gets distributed publicly is always **the engine itself**. This engine does not distribute, and contains no, finished product tied to any specific IP.

## What It Does (in one line)

It turns "I want to play in a certain world" into "a text game that actually plays, and never breaks immersion." The hard part is not writing plot, it is **world-consistency** and **fidelity to the source**, which is exactly where this excavation-plus-extraction logic earns its keep.

---

## Engine Flow (6 phases, built in, not split into separate modules)

Each phase is a stretch of work inside the engine, not a step the user installs separately. The phases carry poetic names, but they all run inside this one skill.

### Phase 0 · Frame (定境)

First, lock these down with the user:

1. **What the world is, and which category**: a film or show / a book / a person / an event / a tabletop game. The category shapes how you excavate (books and screen works go to the canonical text; a person goes to their public persona; a tabletop game goes to the rulebook and the world-setting compendium).
2. **Source of the original**: the specific title / episodes / edition, used as the anchor for fidelity.
3. **Player premise and play mode**: who the player plays in this world, what point in time they enter from, how long the story spans; plus which kind of intent the player has: an original character written in, playing a canonical character themselves, or witnessing canon (following a book character's thread to see what happens to them). All three are supported. Do not turn away a player who wants to be the canonical protagonist.
4. **Fidelity mode**: "faithful to the source" or "permitted divergence." If they pick permitted divergence, settle a **permitted-divergence list** with the user on the spot (which established outcomes may be rewritten, e.g. a certain character does not die, a certain romance does not happen); everything else stays faithful to the source.
5. **Narration language** (`{{NARRATION_LANG}}`, defaults to the user's working language; English is the default and example in this edition) and **proper-noun translation source** (`{{CANON_TRANSLATION_SOURCE}}`, e.g. a given publisher's official translation).

**Playability gate**: Is this world rich enough to carry a simulator? Check whether it has ① recognizable places / spaces ② factions or layered groups ③ a cast with distinct personalities ④ a world-specific mechanic (magic / technology / martial arts / rules) ⑤ a distinctive tone. Fewer than three of these, report back to the user that "this world is thin, want to swap it or flesh out the setting," and do not force the hatch.

> If the user has not been clear, ask. Do not guess and build. When information is fuzzy, ASK, do not guess-build.

**Special handling for tabletop / rules-driven scope**: If the subject is a tabletop game or a rules-driven game (social deduction, card, strategy, etc.), the product is not a narrative-immersion sim but a "game runner (rules engine)": swap out the narrative skeleton (the cold open / story tone / progression-rank machinery) for rules explanation + dealing / role assignment + a game loop + win-loss adjudication. The core difficulty is the firewall (keeping hidden information locked inside, never leaked to the player), not the prose.

**Beginner-mode switch (coaching prompts)**: Game-type products (especially rules-heavy or strategically deep ones) must build in a "beginner mode" switch, asked at the start and toggleable at any point during play. On → the GM gives rules reminders, points out the reasoning available right now, warns "are you sure?" before a blunder that would obviously lose on the spot, and runs a post-game review. Off → it just runs the game, gives no hints, and the player lives with the outcome. On or off, the firewall stays unbroken. Narrative sims may optionally offer a similar hint switch, but it is not required.

### Phase 1 · Excavate (探源)

Pull the worldview fully apart and write it into an internal world-research document (it need not land as a separate file; living in the working context is enough). Sweep out six dimensions:

1. **World skeleton**: geography / key places, timeline, the underlying rules of how the world runs (magic system / technology setup / martial-arts framework).
2. **Faction layers**: houses / camps / families / sects / ship-quarters assignments, each with its traits and signature domains.
3. **Character bible**: the roster of source characters, recording for each: name, personality, family background, formative history, faction, companions / pets, key relationships. This document is the lifeblood of fidelity, so **list fewer rather than write any wrong**.
4. **World mechanics**: how growth / learning works, whether there is a points / reputation system, world-specific assets (wand-type / sword-type / role-type).
5. **Tonal DNA**: genre, pacing, the ratio of humor or suspense, the keys to "making it smell like that world."
6. **Playable-identity axes**: in this world, which variables define a person's identity? (origin, faction, talent, world assets...) These become the fields of the character-creation form directly.

For obscure worlds the model is not familiar with, use WebFetch / WebSearch to fill in material; for popular worlds the model's existing knowledge is enough, but still write out the character bible to self-align.

### Phase 2 · Distill (煉核)

**Converge** Phase 1's research **into the fields the simulator skeleton needs**, and pin down the **immersive essence**:

- If 3 to 5 things in this world were written wrong, the whole feel would collapse. Which are they? (e.g. a certain character's personality, a certain proper-noun translation, a certain world rule.) Mark them as **unbreakable anchors** and write them into the product's NPC Casting Rules and Core Rules.
- Organize the playable-identity axes into character-creation fields, every field carrying a "random" option.

### Phase 3 · Forge (鑄器)

Read `references/simulator-template.md` and fill in Phase 2's world DNA field by field:

- Replace every `{{double-brace token}}` with world-specific content.
- Every `〔angle-bracket instruction〕` is deleted once executed; none remain in the product.
- Inject the full text of `references/immersive-prose-engine.md` verbatim into the "### Core Rules" section, and replace the two parameters `{{NARRATION_LANG}}` and `{{CANON_TRANSLATION_SOURCE}}` with this world's values.
- The product must run as a standalone GM skill: it carries its own frontmatter (skill_id using the world name, languages, a one-line listing_description), and the body is the filled-in skeleton.
- Do not miss the opening "Opening World Primer": use one easy-to-read intro so a player who has never touched the source can pick it up (what world this is, what races / factions there are, how to play). This is the product's first impression, on par with a proper video game's opening.

### Phase 4 · Calibrate (校境)

Once the product is written, self-QA on four counts; if any one fails, return to Phase 3 and fix:

1. **World-consistency**: factions, mechanics, geography, and timeline do not clash with one another; the character bible has not been written wrong.
2. **Fidelity**: the source anchors are all present; if a divergence list was opened, were the changes handled with "chain recomputation" (emotions, growth, downstream behavior all shift accordingly, not just a flipped ending)?
3. **Anti-AI-slop**: sweep the whole product (not just the cold open, but the faction / system and other setting descriptions too): any em-dashes, any banned sentence patterns or banned words tripped, is it concrete depiction, are the translations consistent, no out-of-context phrasing.
4. **Cold-start playable**: run one round in your head: character creation → intake confirmation → cold open → 4 + 1 actions; does this chain flow.

### Phase 5 · Hatch (開孵)

1. **Land the product**: write the product as an installable skill. Default path `~/.claude/skills/sim-{{world english slug}}/SKILL.md` (if the user wants a different path, follow the user). Report the install location and a one-line usage note.
2. **Optional instant play**: ask the user whether to start playing right now in this session. If yes, the engine switches into that product's GM identity and runs the player through it starting from character creation; if no, stop at "produced, installable."

---

## Attitude Toward the User

- By default, run the flow through smoothly; do not stop and check in at every phase. Only Phase 0's key settings (world, fidelity mode, divergence list, language) need confirming with the user first; the rest advances automatically.
- If the user raises any request midway, the user's needs come first.
- The product's narration defaults to the language the user specifies; for the user's working language, use natural local grammar and avoid out-of-context phrasing (details in the immersive prose engine).

## Boundaries (what this engine cannot do)

- It does not take on copyright judgment for the user: it only generates apocryphal-sequel products for a "user-supplied world," and does not assess whether that world can be used commercially.
- When a world is too thin (no characters, no mechanics, no places), it cannot hatch anything good, and will stop it at the playability gate and report back.
- What it hatches is a **text-game GM**, not visuals and not code; the product is a GM skill.

---

## Files

- `references/simulator-template.md`: the 15-block fill-in-the-blank template for the simulator skeleton.
- `references/immersive-prose-engine.md`: the anti-AI-slop immersive-prose canon, injected verbatim into every product.

---

Apocrypha is created and maintained by **llamppost** (https://llamppost.ai). MIT License. Free to use, modify, and distribute; please keep this attribution.
