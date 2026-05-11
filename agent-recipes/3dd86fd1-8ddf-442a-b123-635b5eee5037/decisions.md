# Décisions — videoId `3dd86fd1-8ddf-442a-b123-635b5eee5037`

## `checkpoint-manifest.json`

- Champ `commitSha` : **hash du commit où les artefacts ingest (JSON + markdown hors manifest) ont été enregistrés** ; le commit qui ajoute uniquement le manifest pointe donc vers cet ancêtre pour l'app qui fige le bundle.
- Champ `branch` : branche utilisée pour pousser cet ingest.

## Source et hypothèses photo

- **Source primaire**: photographie de page de livre (liste d'ingrédients, étapes Thermomix, données nutritionnelles) ainsi qu'une photographie platter fini montrant une coupe ouverte mozzarella-pois dans la croûte dorée (fichiers téléversés `photo_2026-05-11_07-09-12.jpg` et `photo_2026-05-11_07-09-10.jpg`).
- **Traduction Thermomix → vidéo**: tous les temps/temperatures robot sont rendus équivalents en mise en visible du risotto façon casserole sur plaque Licorn avec spatule et mains pour garder une continuité avec nos assets `@SaucepanLarge`, `@Spatula`, `@InductionCloseup`.

## Références visuelles (révision générale)

- **Bibliothèque Licorn uniquement** dans les tableaux Seedance/`reference-plan` : îlots `@KitchenIslandDefault` / `@KitchenIslandOverhead` / `@KitchenIslandWide`, `@InductionCloseup`, `@SaucepanLarge`, `@Spatula`, `@CharacterSheet`, `@PoseTopDown`, `@PoseThreeQuarterRight`, `@PoseThreeQuarterLeft`.
- **Aucune** entrée `recipe_state` prévue côté génération image (pas de placeholders type `CoolRisottoPeaParmesanFold`, etc.). Les morphologies risotto→boule→panure→frit→coupe filante sont **imposées par le texte de prompt Seedance**, avec coupes franches et physique explicite, acceptant qu’un modèle puisse encore dériver plus qu’avec des plaques de référence offline.
- Ceci reflète une demande produit : plat jugé suffisamment simple pour un unique passage Seedance par segment sans surcharge de six images hors librairie.

## Feedback génération segment 3 (échelle)

- Retour terrain : variante **boule trop grande** (type ballon de foot). Les prompts `segment-03` précisent désormais **diamètre cible ~5–6 cm**, comparaison aux mains/plan de travail, plan contexte au moins une fois, et négatifs explicites contre sphères surdimensionnées. **Segments 04 à 06** rappellent la même échelle pour la continuité breading → friture → coupe.
- `logical-scenes` **15–18** : notes et descriptions synchronisées avec cette côte.

## Défauts production workspace (inchangés ici)

- Style preset catalogue `asmr_food`; vidéo Seedance **seedance2** références **1080:1920** ; **`gpt_image_2` inchangé en documentation pipeline** mais **non utilisé comme prérequis** pour cet arc arancini ; TTS **eleven_multilingual_v2** et SFX **eleven_text_to_sound_v2** restent gérés hors workspace.

## Ouverture créative

- **Texture d'abord**: neige de parmesan puis pay-off immédiat sur chair d'échalote, plutôt que table d'ingrédients statique.
- **Hook argent**: rupture coque + fil mozzarella après tension friture drain (segment 6).

## Écarts résiduels / questions actives

Voir `recipe-analysis.json` → `clarifyingQuestions` pour (1) bol robot vs casserole seulement et (2) poids visuel de la salade de jeunes pousses finale.

## Artefacts complets

Ce lot inclut `recipe-analysis.json`, `logical-scenes.json`, `seedance-segments.json`, `reference-plan.json`, `suno-prompt.md`, `changelog.md`.

## Temps

Les champs `prep` / `cook` / `total` du JSON reprennent la fiche (25 / 40 / 95 min cumulées livre). Le **repos/refroidissement 30 minutes** est intégré au total indiqué dans la source imprimée mais n'est pas un quatrième champ JSON (contrainte contrat).
