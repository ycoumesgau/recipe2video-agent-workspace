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
