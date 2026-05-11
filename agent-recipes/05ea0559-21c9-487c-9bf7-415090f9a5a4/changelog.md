# Changelog — `05ea0559-21c9-487c-9bf7-415090f9a5a4`

## Recipe ingest (initial)

- Added `recipe-analysis.json` from URL source with structured steps, ingredients, `timing` keys `{prep,cook,total}`, string arrays for `criticalTransformations`, `visualTextureOpportunities`, `possibleHooks`, `promptPolicySources`, and clarifying questions on tortilla style and sauce-depth coverage.
- Added `logical-scenes.json` with **38** editorial scenes; texture-first arc; character satisfaction closer.
- Added `seedance-segments.json` with **7** References-mode segments, explicit timing blocks, ASMR-only audio policy, and mappings to logical scene IDs.
- Added `reference-plan.json` merging existing Licorn assets with four planned `recipe_state` images for fragile sauce, assembly, bake, and pull geometries (historical note; superseded by library-only revision in section below).
- Added `suno-prompt.md` aligned to cozy ASMR-food arc without tutorial lyrics.
- Added `decisions.md` capturing defaults, assumptions, and deferred clarifications.

## Seedance simplify — library references only

- Removed all `recipe_state` / bespoke dish PNG hooks from `reference-plan.json` and from each `seedance-segments.json` reference list (sauce simmer, casserole pack, blister bake, cross-section pull). Food-specific look lives in rewritten English prompts plus negatives/hard-cut timing instead of duplicated stills comparable to overcooked arancini-style reference stacks.
- Trimmed redundant `@` handles per segment accordingly; QA reference counts stay beneath the nine-image cap with more slack.
- Noted ingest policy tweak in `recipe-analysis.json` `promptPolicySources` and softened clarifyingQuestions copy where it mentioned custom reference imagery.
- `logical-scenes.json` scene-27 editorial note reframed (“prompt text, no dish PNG”) to match execution strategy.

## Checkpoint hygiene

- `checkpoint-manifest.json` `commitSha` aligned to pushed branch tip (`6905901…` lineage) whenever metadata-only checkpoint commits land after content commits.
