# Changelog — `f311970f-95cb-4d58-8088-365984eb2d31`

## 2026-05-18 — Pass Zod / contrat strict (enum `source` + Suno `model`)

- Normalisation `reference-plan.json`: toutes les entrées `source` → **`agent_reference_plan`** (alignement `contracts/artifact-schemas.md`).
- `suno-prompt.json`: `status.model` → **`Suno 5.5 Advanced / Custom Mode`** (skill Suno / schéma attendu).
- Revue manuelle : ordre des sections dans `suno-prompt.md`, champs obligatoires sur l’ensemble des JSON listés.

## 2026-05-18 — Skills sync (`main` + maryse doc)

- Vérifié `fetch`/`merge` de `origin/main` sur la branche recipe (inchangée car déjà à jour).
- Recalibration des usages `@SiliconeSpatula` : rôles + prompts Seedance (`segment-01`, `segment-02`) alignés avec `reference-detail/utensil-task-mapping.md` après la clarification *maryse* sur `main`.
- `reference-plan.json` → entrée ustensile et `recipe-analysis.json` → hypothèses / `promptPolicySources` mis à jour pour tracer explicitement la séparation maryse vs `@TurningSpatula`.

## 2026-05-18 — Pass conformité `artifact-schemas`

- Harmonisation des lignes `timing` + blocs correspondants dans `prompt`/`promptInitial` de `seedance-segments.json` sur le gabarit `start-endXs: beat` défini dans `contracts/artifact-schemas.md`.
- Nettoyage des champs Style / Exclude de `suno-prompt.json`/`.md` pour éviter le nomming explicite d’une plateforme dans Suno alors que les garde-fous lyric interdisent les références aux réseaux.
- Réécriture de la section décisionnelle sur la sémantique du fichier `checkpoint-manifest.json` après revue crypto-SHA impraticable dans le même objet commit.

## 2026-05-18 — Initial `recipe_ingest` checkpoint

- Created `recipe-analysis.json` from the TikTok wrap hack URL (Crunchwrap supreme card) with explicit timing keys (`prep`, `cook`, `total`), string-only policy arrays, and clarifying questions for tortilla type + quadrant orientation.
- Authored `logical-scenes.json` with **40** English logical scenes (texture-first hook, taco beef, hinge cut, quadrant fills, tri-fold mechanic, skillet blister arc, cross-section climax, satisfied Licorn finale).
- Built `seedance-segments.json` with **8** References-mode segments (≤9 refs each) including kitchen continuity pairs, ASMR-only audio policy, and generated-state placeholders.
- Published `reference-plan.json` mapping global assets plus four `gpt_image_2` recipe-state targets.
- Added synchronized `suno-prompt.json` + `suno-prompt.md` (`schemaVersion` 1) with funk-pop scoring direction distinct from lyric prompts.
- Documented production defaults, scope cuts (no nori tangent), and outstanding questions in `decisions.md`.
