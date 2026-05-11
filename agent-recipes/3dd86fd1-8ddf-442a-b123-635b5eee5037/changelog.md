# Changelog — `3dd86fd1-8ddf-442a-b123-635b5eee5037`

## 2026-05-11 — Allègement références (sans `recipe_state`)

- Suppression des **six** images d’état arancini planifiées en amont dans `reference-plan.json`; le plan ne référenc plus que les PNG **kitchen / ustensiles / poses / perso**.
- Réécriture des `prompt` / `references` Seedance (**segments 02–07**) pour décrire risotto malléable, mise en boule mozzarella, panure double, dorure, coupe filante et plateau **uniquement en langage Seedance**, avec coupe dure conservée où la géométrie fragile (fil fromage, panure encore pâle) le nécessite.
- `recipe-analysis.json` → `promptPolicySources` : note explicite de cette stratégie.
- Risque résiduel : erreurs morphologiques davantage probable qu’avec références image ; QA devra retenter prompts ou régler coupes si artefacts visibles.

## 2026-05-11 — Ingestion initiale (photos)

- Création complète des artefacts Recipe2Video depuis les photos de livre + photo de dressage final.
- Ajout de **38** `logicalScenes` pour couvrir parmesan → risotto → refroidissement → farce mozzarella → double panure → friture → money shot fromage → plateau final personnage.
- Découpage en **7** segments Seedance References (somme cible ~39 s) ; la révision du **2026-05-11 (pm)** retire les six `recipe_state` image planifiés au profit de prompts Seedance texte seuls (voir changelog « Allègement références »).
- Déclaration de questions ouvertes (`appliance-vs-casserole`, `salad-plating-weight`) sans bloquer la présence des scènes optionnelles salade (scène 36 compressible).

## Écarts au contrat livre

- Vocal robot (vitesses / modes) remappé en langage cassette/fourchette pour compatibilité Seedance et assets disponibles.
