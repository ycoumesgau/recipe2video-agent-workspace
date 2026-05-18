# Changelog - Sushi Bowl

## 2026-05-18

- Created `recipe-analysis.json` from the Love and Lemons sushi bowl source URL.
- Added linked component details for baked tofu, spicy mayo, and quick pickled radishes because the main recipe references them externally.
- Created `logical-scenes.json` with 36 logical scenes, texture-first opening, and final Licorn kitchen satisfaction beat.
- Created `seedance-segments.json` with 8 Seedance 2 References segments, hard cuts, explicit timing, ASMR-only audio, kitchen continuity pairs, and scale locks.
- Created `reference-plan.json` with existing global assets and planned recipe-specific state references.
- Created `suno-prompt.json` and `suno-prompt.md` for manual Suno Custom Mode use.
- Created `decisions.md` documenting assumptions, unresolved clarifications, and production boundaries.
- Noted unresolved choices: optional pickled radishes and regular versus vegan spicy mayo.
- No paid generation or external production service was launched.
- Refreshed `checkpoint-manifest.json` during status review so it records the latest pushed artifact commit available at review time.
- Pulled `origin/main`, re-read the updated Recipe2Video skills, and replaced the legacy `@Spatula` utensil reference with `@SiliconeSpatula` in the tofu coating segment and reference plan.
- Tightened `recipe-analysis.json` to the contract keys only by moving video ID, serving yield, style preset, and production defaults into `decisions.md` for Zod-safe retrieval.
- Pulled the latest `origin/main` with Seedance 2 validation updates, raised all Seedance segment `durationTarget` values to integer 5-15 second windows, aligned prompt timings to those totals, and added `conditioningReferences` visual anchors to every generated recipe-state reference.
