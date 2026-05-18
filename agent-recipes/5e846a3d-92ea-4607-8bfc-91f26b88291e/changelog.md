# Changelog — Bibimbap coréen

## 2026-05-18 — recipe_ingest

- Created `recipe-analysis.json` from the Atelier des Chefs Bibimbap coréen source.
- Recorded source access caveat: slash-final URL fetch hit timeout/429, while the recipe research pass extracted usable content from the URL without trailing slash.
- Added clarifying questions for the anomalous rumsteck quantity, egg presentation, chili sauce identity, and final serving geometry.
- Created `logical-scenes.json` with 36 scenes, opening on a yolk-break texture hook and ending with the finished bowl plus satisfied Licorn character.
- Created `seedance-segments.json` with 8 Seedance 2 References segments, explicit timing, ASMR-only audio, hard cuts, kitchen continuity pairs, scale locks, and negatives.
- Created `reference-plan.json` with existing kitchen/character/utensil references plus planned recipe-specific state references for fragile food states.
- Created `suno-prompt.json` and `suno-prompt.md` for a manual Suno workflow; no Suno API or paid generation was called.
- Created `decisions.md` documenting production assumptions and unresolved source questions.
- Updated `checkpoint-manifest.json` with the pushed artifact checkpoint SHA after the first checkpoint push.

## 2026-05-18 — general review map

- Added a review map in `decisions.md` explaining where to study recipe analysis, editorial scene planning, Seedance generation prompts, references, Suno prompts, changelog, and checkpoint metadata.
- Corrected `checkpoint-manifest.json` to point at the latest pushed checkpoint commit available before this update.

## 2026-05-18 — sync with updated main skills

- Pulled `main` into the recipe branch and re-read the updated recipe/Seedance/asset/Suno skills.
- Updated `seedance-segments.json` and `reference-plan.json` to replace the legacy `@Spatula` reference with `@SiliconeSpatula`, matching the renamed asset `assets/ustensils/silicone_spatula.png` and the updated utensil-task mapping.
- Added a decision note explaining the spatula-family update and retained `@Tongs` for hot food movement.
- Applied the updated scene-verifier guidance: added visible hand references for segments 03 and 05, moved the rice steam reference to segment 02, added `@TurningSpatula` for fried egg transfer in segment 06, strengthened terrazzo/no-wood locks, and reclassified three scenes as context re-anchors.
