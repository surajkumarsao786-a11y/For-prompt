# For-prompt

A collection of roleplay and creative-writing system presets.

## Files

### [`Freaky Frankenstein Raw.md`](Freaky%20Frankenstein%20Raw.md)

A flattened, frontend-agnostic Markdown port of [`Tavo_Freaky Frankenstein 4 MAX_HTxS.json`](Tavo_Freaky%20Frankenstein%204%20MAX_HTxS.json). All SillyTavern macros (`{{user}}`, `{{char}}`) have been replaced with `<USER>` / `<CHAR>` placeholders, and the one HTML construct (the `<details><summary>` Plot Momentum block) has been rewritten as a plain markdown bullet list. The signature pseudo-XML rule-config aesthetic is preserved — that's the preset's identity.

The original 7-task `<think>` reasoning chain is now an 8-task chain — the new **Task 8: The Easy Move vs. The Better Move** is grafted on top to force a craft-discipline pass before the prose is written. An explicit NC-17 content policy header has also been added at the top (canonical ages are canonical, sexual-content floor at 14+, no softening), bringing the deployment-time content policy in line with the preset's actual intended use.

Intended for raw-chat interfaces (any system prompt field) that do **not** render HTML or CSS. Every reply produces a single-line time/place header, the 3–4 paragraph prose body in Hybrid POV (close third for the world, second-person "you" for the Human's sensations), and a plain-text **🎯 Plot Momentum** tracker at the end with the four next-beat path options (A/B/C/D) the model commits to executing on its next turn.

Tested mental-target model class: Claude Opus / Sonnet 4.x with large context. Samplers are set in the chat UI, not the preset.

### [`Tavo_Freaky Frankenstein 4 MAX_HTxS.json`](Tavo_Freaky%20Frankenstein%204%20MAX_HTxS.json)

The original SillyTavern preset by Tavo. 17 enabled modules, pseudo-XML rule-config style, with Hybrid POV, Plot Momentum tracker, VAD Emotional System, species-accurate vocalizations, hard banned-vocabulary list, and a 7-task Realism Mode chain-of-thought. Use this if you are running SillyTavern.

### [`Lucid Loom v3.3.json`](Lucid%20Loom%20v3.3.json)

A separate large SillyTavern preset (Lumia-the-Weaver, toggle-based, 316 prompts). Retained for reference.

### [`Nemo Engine 8.01 Exp.json`](Nemo%20Engine%208.01%20Exp.json) · [`Stabs-GLM5.1-Directives-v2.6.json`](Stabs-GLM5.1-Directives-v2.6.json)

Third-party presets retained for reference.

## Which to use

| Need | Use |
|---|---|
| Raw chat UI, no HTML support, Claude/Sonnet/Opus | **Freaky Frankenstein Raw.md** |
| SillyTavern with full feature set | **Tavo_Freaky Frankenstein 4 MAX_HTxS.json** or **Lucid Loom v3.3.json** |

## Notes on the Raw conversion

- `{{user}}` and `{{char}}` from the JSON are replaced with `<USER>` and `<CHAR>` placeholder tokens. The model treats them as pointing to the Human's player character and the AI-voiced primary character respectively, both of which are fully defined by the character card or opening scene the Human pastes after activation.
- The Plot Momentum tracker is now a plain-markdown block appended after the prose, separated by `---`. No `<details>`/`<summary>` tags, no JavaScript-style collapsibles. Same fields, same logic: NPC Agenda, Physics, Scene Pacing, four Path options (A default / B conflict / C action / D twist), Selected Path, Strategy Reason. The model commits to the selected path on the very next turn.
- The Time-Place header at the top of every response uses Unicode emojis only (🕰️ 🗓️ 📍 ☀️ 🌧️ 🌫️ 🌩️) — no HTML, no images, no font tags. These render fine as text in any chat UI.
- The Onomatopoeia override uses `*asterisks*` (Markdown emphasis), not raw HTML or BBCode — `*Squelch!*`, `*Thwack*`, `*slap slap slap*`.
- All other rules (Hybrid POV, Anti-Stiff Prose, Increased Dialogue, VAD Emotional Matrix, Female Vocal Acoustics, Scene Separation Protocol, Attentional Salience, Banned Vocabulary, Tone Calibration, NSFW Mode, HQ NPC Genesis with the "pick the 5th name" rule, Challenge-Me negativity bias) are preserved verbatim from the JSON, with only `{{user}}`/`{{char}}` substitutions.
