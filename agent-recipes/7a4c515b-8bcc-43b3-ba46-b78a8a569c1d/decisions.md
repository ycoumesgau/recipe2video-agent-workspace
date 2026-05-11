# Décisions — `7a4c515b-8bcc-43b3-ba46-b78a8a569c1d`

## Source et périmètre

- Ingest à partir de photos (`photo_2026-05-11_07-09-12.jpg`, `photo_2026-05-11_07-09-10.jpg`) : recette « Arancini mozzarella, riz & petits pois » (catégorie apéritifs / entrées), rendement 24 pièces, temps source 25 min prép / 40 min cuisson / 1 h 35 total (repos froid 30 min intégré au bloc risotto en fin de cuisson).
- Le texte source décrit une cuisson type Thermomix ; **décision de production** : la vidéo Licorn montre casserole, induction et gestes classiques (sauté, déglacage, brassage, friture) pour garder des actions lisibles en macro ASMR.

## Hypothèses acceptées

- Taille des boules annoncée : **6 cm** ; cube mozzarella par unité dérivé de 125 g pour ~24 boules (valeur indicative pour cadrage et references `gpt_image_2`).
- **Huile 180–190 °C** : la prompt Seedance évite tout chiffre lisible comme incrustation ; la thermométrie reste direction créative ou hors cadre.
- Salade conseillée (jeunes pousses) conservée comme **beat de fraîcheur** en clôture.

## Paramètres production (non exécutés ici)

- Preset style : `asmr_food` ; vidéo `seedance2` (1080:1920) ; références image fragiles via `gpt_image_2` ; TTS `eleven_multilingual_v2` ; SFX `eleven_text_to_sound_v2`. Aucun appel API dans ce dépôt.

## Ouvert / questions

- Voir `recipe-analysis.json` → `clarifyingQuestions.equipment-framing` : validation si un plan robot doit apparaître ou si tout reste sur casserole Licorn.

## Storyboard

- Ouverture texture-first sur **déglacage vin / vapeur** (scène 1) avec **scène 2** qui clarifie le grain toasté ; pas de plateau d’ingrédients en intro.
- Sept segments Seedance couvrant 36 scènes logiques ; états fragiles (liaison risotto, sphère scellée, double panure, dorure friture, coupe filante) portés par des références image dédiées dans `reference-plan.json`.
