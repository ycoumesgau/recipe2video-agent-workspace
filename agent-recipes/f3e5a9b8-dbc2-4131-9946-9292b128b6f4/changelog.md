# Changelog - Lasagne dumpling

## 2026-05-18 - Recipe ingest

- Created `recipe-analysis.json` from the Bon pour toi recipe URL, including ingredients, steps, timing, critical transformations, texture opportunities, possible hooks and prompt policy sources.
- Created `logical-scenes.json` with 36 logical scenes, using a texture-first final-dish hook, compressed utility steps and frequent ASMR payoff beats.
- Created `seedance-segments.json` with 8 Seedance 2 References segments, explicit hard cuts, timing, ASMR-only audio, kitchen continuity pairs and scale/geometry locks.
- Created `reference-plan.json` using existing kitchen, character, pose and utensil assets wherever possible.
- Planned only one generated recipe-state reference, `FinishedDumplingLasagnaCutaway`, because it is the minimum safeguard for the final non-standard geometry and prevents tomato/cheese lasagna drift.
- Created `suno-prompt.json` and `suno-prompt.md` as copy-ready manual Suno prompts, kept separate from the Seedance ASMR-only video prompts.
- Created `decisions.md` documenting creative choices, scale assumptions, reference minimization and remaining non-blocking ambiguity.
- Added `checkpoint-manifest.json`; final commit SHA will be updated after the artifact commit is pushed.
- Tightened review findings before commit: segment 05 now includes visible hands, pose and mandatory tong handling for hot steamer actions; segment 05 repeats the 20 cm pan and 3-5 cm height scale lock; final bite reveal consistently uses `@Spoon`.

## 2026-05-18 - Artifact readiness refresh

- Rechecked the recipe artifact set for the general artifact-generation request.
- Confirmed all required planning artifacts are present for the recipe workspace.
- Refreshed `checkpoint-manifest.json` so Recipe2Video has an up-to-date pushed checkpoint pointer for the current artifact set.

## 2026-05-18 - Main sync and updated skills

- Merged the latest `origin/main` into the recipe branch.
- Updated utensil references according to the refreshed asset-reference skills: `@SiliconeSpatula` for spreading filling layers and `@TurningSpatula` for supported portion lifts.
- Updated `recipe-analysis.json`, `logical-scenes.json`, `seedance-segments.json`, `reference-plan.json`, Suno notes, `decisions.md`, and this changelog to remove legacy generic spatula usage.
- Kept the reference-generation plan minimal with only `FinishedDumplingLasagnaCutaway` as a generated recipe-state reference.

## 2026-05-18 - Main sync and reference conditioning

- Merged the latest `origin/main` again after the reference-image generation contract changed.
- Added `conditioningReferences` to the generated `FinishedDumplingLasagnaCutaway` entry so GPT-Image 2 receives the kitchen, cookware, and dominant utensil anchors.
- Confirmed no character-class anchors are used for recipe-state conditioning.
