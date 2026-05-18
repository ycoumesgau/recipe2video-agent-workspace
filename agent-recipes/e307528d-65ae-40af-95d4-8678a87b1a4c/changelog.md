# Changelog - e307528d-65ae-40af-95d4-8678a87b1a4c

## 2026-05-18 - Recipe ingest

- Created recipe-analysis.json from the Del's Cooking Twist source URL and creator instructions.
- Added orecchiette as the locked pasta shape throughout the analysis, scenes, Seedance prompts, and reference plan.
- Added roasted pistachios as a supplemental recipe step and final crunchy topping.
- Created 36 logical scenes with texture-first hook, ASMR pacing, and final Licorn satisfaction.
- Created 8 Seedance 2 References-mode segments with kitchen continuity pairs, explicit reference roles, hard cuts, ASMR-only audio, and no speech/voiceover/music.
- Created reference-plan.json using existing kitchen, character, pose, and utensil assets; no generated recipe-state images planned at ingest per creator constraint.
- Created suno-prompt.json and suno-prompt.md as manual Suno Custom Mode prompts for later music generation.
- Created decisions.md documenting adaptation choices, scale locks, and the no-generated-intermediate-reference decision.

## 2026-05-18 - Main sync and skill refresh

- Merged `origin/main` into the recipe branch to pick up updated asset-reference skill guidance, including the spatula-family distinction.
- Re-audited Seedance references: no legacy `@Spatula` usage, no generated recipe-state references added, all segments keep kitchen continuity pairs and <=9 references.
- Reclassified five utility/detail scenes as context beats to restore the target 75-80% detail / 20-25% context balance without changing the editorial arc.
- Replaced final vocalization-risk audio wording with non-vocal kitchen room tone cues.
