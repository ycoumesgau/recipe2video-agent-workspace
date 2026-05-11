# Changelog — 71986b31-9318-4409-a6ed-5bbfd22fac3e

## 2026-05-11 — Ingest initial (photos)

- Création de `recipe-analysis.json` à partir des pages photo : ingrédients, étapes visibles, transformations critiques, questions de clarification (Thermomix vs casserole, type de mozzarella).
- Ajout de `logical-scenes.json` : 40 scènes logiques (plage 30–48), arc hook texture + chronologie risotto → forme → panure → friture → service Licorn.
- Ajout de `seedance-segments.json` : 7 segments `seedance2` mode References, ratio 1080:1920, timings serrés, audio ASMR sans parole ni musique; alignement du segment 1 sur 5 prises pour couvrir les cinq scènes du hook.
- Ajout de `reference-plan.json` : references `assets/` Licorn + trois plans `gpt_image_2` pour états fragiles.
- Rédaction de `suno-prompt.md`, `decisions.md`, et de cette entrée de journal.

## 2026-05-11 — Revue source (vision) & manifeste

- Enrichissement des `assumptions` dans `recipe-analysis.json` : ustensiles listés (spatule, casserole), mood surface et arrière-plan vu sur la photo plat, indice éditorial grand public (sans reproduire de marque à l’écran), macronutriments imprimés en option hors prompt vidéo.
- Mise à jour de `checkpoint-manifest.json` après push : `commitSha` pointe vers la révision précédant le dernier amend de manifeste (limitation d’auto-référence Git) ; la tête de branche distante à consulter est `git rev-parse origin/cursor/recipe-ingest-arancini-71986b31-9d5a`.
- `decisions.md` : commentaire sur la lecture du manifeste vs la tête de branche.