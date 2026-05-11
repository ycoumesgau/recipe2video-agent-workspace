# Décisions — videoId `3dd86fd1-8ddf-442a-b123-635b5eee5037`

## Source et hypothèses photo

- **Source primaire**: photographie de page de livre (liste d'ingrédients, étapes Thermomix, données nutritionnelles) ainsi qu'une photographie platter fini montrant une coupe ouverte mozzarella-pois dans la croûte dorée (fichiers téléversés `photo_2026-05-11_07-09-12.jpg` et `photo_2026-05-11_07-09-10.jpg`).
- **Traduction Thermomix → vidéo**: tous les temps/temperatures robot sont rendus équivalents en mise en visible du risotto façon casserole sur plaque Licorn avec spatule et mains pour garder une continuité avec nos assets `@SaucepanLarge`, `@Spatula`, `@InductionCloseup`.

## Défauts production workspace (inchangés ici)

- Style preset catalogue `asmr_food`; vidéo Seedance **seedance2** références **1080:1920** ; références images futures via workflow **gpt_image_2** (référence seulement dans ce dépôt créatif, aucun appel API ici) ; TTS **eleven_multilingual_v2** et SFX **eleven_text_to_sound_v2** restent gérés hors workspace.

## Ouverture créative

- **Texture d'abord**: neige de parmesan puis pay-off immédiat sur chair d'échalote, plutôt que table d'ingrédients statique.
- **Hook argent**: rupture coque + fil mozzarella après tension friture drain (segment 6).

## Écarts résiduels / questions actives

Voir `recipe-analysis.json` → `clarifyingQuestions` pour (1) bol robot vs casserole seulement et (2) poids visuel de la salade de jeunes pousses finale.

## Artefacts complets

Ce lot inclut `recipe-analysis.json`, `logical-scenes.json`, `seedance-segments.json`, `reference-plan.json`, `suno-prompt.md`, `changelog.md`.

## Temps

Les champs `prep` / `cook` / `total` du JSON reprennent la fiche (25 / 40 / 95 min cumulées livre). Le **repos/refroidissement 30 minutes** est intégré au total indiqué dans la source imprimée mais n'est pas un quatrième champ JSON (contrainte contrat).
