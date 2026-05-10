# Changelog

## 2026-05-10 - recipe_ingest

- Created `recipe-analysis.json` from the Gimme Some Oven chicken enchiladas recipe and the linked homemade red enchilada sauce recipe.
- Created `logical-scenes.json` with 36 logical scenes targeting a 60-second ASMR food video.
- Created `seedance-segments.json` with 8 Seedance 2 References segments, explicit reference roles, hard cuts, ASMR-only audio, and mandatory timing.
- Created `reference-plan.json` with existing global kitchen/character/utensil references plus planned generated recipe-state references.
- Created `suno-prompt.md` as a manual, copy-ready Suno prompt with required fields separated.
- Created `decisions.md` documenting source assumptions, editorial choices, production defaults, and readiness.
- Planned recipe-specific image references only; no Runway, Suno, Supabase, Mux, Remotion, OpenAI, or paid generation service was launched.
- Updated `checkpoint-manifest.json` with latest pushed commit SHA `922e0d36aae2dbde55745c225339d49376d71cd2`.

## 2026-05-10 - recipe_ingest retry after checkpoint contract fix

- Updated `recipe-analysis.json` in this run by recording the checkpoint contract fix in `promptPolicySources`.
- Kept the existing complete planning set because the recipe source remains complete and no clarifying questions are needed.
- Prepared the project artifacts for commit and push on branch `cursor/recipe-ingest-52c97bec-2620` per the retry request.
- Committed and pushed the project artifacts in commit `9c088d11b4662c46df35694738e34c51a3dcbaa2`, then updated `checkpoint-manifest.json` to record that pushed artifact checkpoint.

## 2026-05-10 - recipe_ingest retry after parser and workspace-rule fixes

- Updated `recipe-analysis.json` in this run by recording `parser-workspace-rule-fix` in `promptPolicySources`.
- Refreshed `checkpoint-manifest.json` timestamp for this retry while keeping all required artifacts ready.
- No source gaps were introduced; `clarifyingQuestions` remains empty.
- Committed and pushed retry artifacts in commit `6b9e30b187d553ebeabce1c8753869e380dd721b`, then recorded that pushed checkpoint in `checkpoint-manifest.json`.

## 2026-05-10 - recipe_ingest retry after GitHub-consistency retry patch

- Updated `recipe-analysis.json` in this run by recording `github-consistency-retry-patch` in `promptPolicySources`.
- Refreshed `checkpoint-manifest.json` timestamp and marked the artifact set as `syncReady`.
- Kept all planning artifacts ready; the source remains complete and `clarifyingQuestions` remains empty.
- Committed and pushed sync-ready artifacts in commit `76339e650840e4e4387c53cbeefd9c37b6f2562f`, then recorded that pushed checkpoint in `checkpoint-manifest.json`.

## 2026-05-10 - recipe_ingest retry after manifest parser compatibility fix

- Updated `recipe-analysis.json` in this run by recording `manifest-parser-compatibility-fix` in `promptPolicySources`.
- Kept `checkpoint-manifest.json` parser-friendly with top-level `latestPushedCommitSha` and `artifacts`.
- Added `checkpoint-manifest.json` to the manifest `artifacts` list so the sync package advertises the checkpoint file explicitly.
- Committed and pushed parser-compatible artifacts in commit `26000f2933a199f9aef85f05e498478033c3d9a0`, then recorded that pushed checkpoint in `checkpoint-manifest.json`.

## 2026-05-10 - recipe_ingest strict recipe-analysis contract normalization

- Updated `recipe-analysis.json` in this run to match strict contract types.
- Converted `recipe.timing` to `prep`, `cook`, and `total` keys.
- Converted `criticalTransformations` and `possibleHooks` to arrays of plain strings.
- Confirmed `visualTextureOpportunities` and `promptPolicySources` remain arrays of plain strings.
