# Changelog - TikTok Egg Boil

## 2026-05-18 - Recipe ingest

- Created `recipe-analysis.json` from the Whisper of Yum TikTok Egg Boil URL, including ingredients, source timings, assumptions, critical transformations, texture opportunities, hooks, and policy sources.
- Created `logical-scenes.json` with 36 scenes mapped to 7 Seedance segments, using a texture-first sauce/yolk hook and a detail-heavy ASMR structure.
- Created `seedance-segments.json` with 7 Seedance 2 References segments, hard-cut timing, ASMR-only audio prompts, scale locks for six standard chicken eggs, kitchen continuity pairs, and no generated intermediate food references.
- Created `reference-plan.json` using existing canonical kitchen, character, pose, expression, and utensil assets only.
- Created `suno-prompt.json` and `suno-prompt.md` for a manual Suno workflow, keeping music separate from Seedance video prompts.
- Created `decisions.md` documenting the jammy-yolk assumption, no-side-dish choice, sparse parsley lock, and reference-image restraint.
- `checkpoint-manifest.json` will be updated after the pushed commit SHA is available.
