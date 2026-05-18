# Changelog - TikTok Egg Boil

## 2026-05-18 - Recipe ingest

- Created `recipe-analysis.json` from the Whisper of Yum TikTok Egg Boil URL, including ingredients, source timings, assumptions, critical transformations, texture opportunities, hooks, and policy sources.
- Created `logical-scenes.json` with 36 scenes mapped to 7 Seedance segments, using a texture-first sauce/yolk hook and a detail-heavy ASMR structure.
- Created `seedance-segments.json` with 7 Seedance 2 References segments, hard-cut timing, ASMR-only audio prompts, scale locks for six standard chicken eggs, kitchen continuity pairs, and no generated intermediate food references.
- Created `reference-plan.json` using existing canonical kitchen, character, pose, expression, and utensil assets only.
- Created `suno-prompt.json` and `suno-prompt.md` for a manual Suno workflow, keeping music separate from Seedance video prompts.
- Created `decisions.md` documenting the jammy-yolk assumption, no-side-dish choice, sparse parsley lock, and reference-image restraint.
- Updated `checkpoint-manifest.json` with pushed artifact commit `5a108fb3e47bf8a3a8b907c434a9f0e624056a15`.

## 2026-05-18 - Artifact resend checkpoint refresh

- Confirmed the required recipe artifacts already exist for the project.
- Refreshed `checkpoint-manifest.json` to point at pushed commit `cd85114af12543bfd2077a5ad606562b10352738` for the artifact resend request.

## 2026-05-18 - Main pull and strict format refresh

- Pulled `origin/main` into the recipe branch and re-read the updated Recipe2Video skills and artifact contract.
- Confirmed the updated spatula-family naming does not require prompt changes for this recipe because it uses `@Spoon`, `@Tongs`, and `@SaucepanLarge`, not `@Spatula`.
- Updated `decisions.md` to remove the stale note about assets not being visible locally.
- Revalidated strict JSON structure and Seedance/Suno artifact constraints before checkpoint refresh.

