# For-prompt

A collection of roleplay and creative-writing system presets.

## Files

### [`Lucid Loom Raw.md`](Lucid%20Loom%20Raw.md)

A flattened, frontend-agnostic Markdown port of Lucid Loom v3.3. All SillyTavern macros (`{{setvar}}`, `{{getvar}}`, `{{user}}`, `{{char}}`, `{{roll}}`, etc.) and every HTML/CSS utility have been stripped and either removed or replaced with plain-prose equivalents. The craft logic, Lumia persona, 12-step weave planner, Anti-Slopinator, Character Voice Iconoclast Protocol, Reactive Weave Protocol, NSFW/Violence Enhancers, Trauma Guards, Flaw-First Decision Tree, and every other enabled module from Lucid Loom v3.3 are preserved. The mandatory 8-step reasoning workshop from `preset.md` has been grafted on top of the existing weave planner (now 12 steps) — in particular the *Easy Move vs. Better Move* craft step, which was not in the original Lucid Loom.

The mandatory 8-step reasoning workshop (including the Easy-Move-vs-Better-Move discipline step) is grafted on top of the original weave planner, which now runs a unified 12-step `<think>` block every reply.

Intended for raw-chat interfaces (any system prompt field) that do **not** render HTML or CSS. Formatting is plain Markdown: thoughts in `*asterisks*`, dialogue in `"quotes"`, scene breaks as `***`. Tested mental-target model class: Claude Opus / Sonnet 4.x with large context. Samplers are set in your chat UI, not the preset.

### [`Lucid Loom v3.3.json`](Lucid%20Loom%20v3.3.json)

The original SillyTavern/RisuAI preset. 316 prompts, toggle-based, with Lumia-the-Weaver persona, scalable CoT, colored dialogue/thoughts, HTML visuals, position tracker, `[FINAL WEAVE]` round-table, per-model sampler recommendations, and a full synergies/conflicts README built into the first prompt. Requires a SillyTavern-family frontend. Use this if you want the configurable toolkit.

### [`Nemo Engine 8.01 Exp.json`](Nemo%20Engine%208.01%20Exp.json) · [`Stabs-GLM5.1-Directives-v2.6.json`](Stabs-GLM5.1-Directives-v2.6.json)

Third-party presets retained for reference.

## Which preset to use

| Need | Use |
|---|---|
| Raw chat UI, no HTML support, Claude/Sonnet/Opus | **Lucid Loom Raw.md** |
| SillyTavern with full feature set, colored dialogue, HTML artifacts, fine-grained toggles | **Lucid Loom v3.3.json** |

## Notes

- Lucid Loom Raw keeps the Standard Lumia voice by default. Appendix A at the bottom of the file lists optional personality addenda (Wicked, Bubbly, Mommy, Sultry, Angsty) that the Human can paste into their first message to override.
- The Chaos Modifier's random rolls are selected internally by the model rather than emitted by a frontend macro — Claude-class models handle this reliably.
- The plain-text Loom Ledger at the end of each response replaces the original HTML `<loomledger><details>` block. Same information, no markup.
