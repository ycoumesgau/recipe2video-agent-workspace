# Changelog — `2d019b96-13ae-4dc1-ae9a-07c25f5db515`

## 2026-05-11 — Ingestion initiale (photos)

- `checkpoint-manifest.json` : `commitSha` référence le commit d’ingest `2fdb66b84b552d98db3a05ebbc5f4b54095cb0a5` (tous les artefacts sauf alignement du manifest) ; le sommet git inclut ensuite un commit de métadonnées — utiliser le SHA du bloc `recipe2videoCheckpoint` pour l’état poussé le plus récent.
- Ajout de `recipe-analysis.json` à partir des pages livre (arancini mozzarella, riz, petits pois) : ingrédients, étapes visibles, timings (prep / cook / total), transformations critiques, opportunités texture / hooks, `promptPolicySources` en chaînes, et `clarifyingQuestions` sur robot vs casserole et rôle de la salade.
- Ajout de `logical-scenes.json` : **36** scènes (cible 30–48), ouverture macro « sizzle », payoffs réguliers, mapping `segmentId` pour tracer les blocs éditoriaux.
- Ajout de `seedance-segments.json` : **7** segments mode References, ratio **1080:1920**, prompts en anglais avec rôles explicites, audio ASMR sans parole ni musique, limites de références respectées.
- Ajout de `reference-plan.json` : kit global Licorn + **cinq** états générés requis pour risotto refroidi, sphère scellée, panure double crue, boule dorée, coupe/pull mozzarella.
- Ajout de `suno-prompt.md` : champs Suno séparés, paroles en anglais image-driven sans tutoriel.
- Ajout de `decisions.md` : hypothèses de transposition Thermomix → casserole Licorn et principes d’ouverture/finale.
