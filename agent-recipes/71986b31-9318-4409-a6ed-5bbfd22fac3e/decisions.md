# Décisions — 71986b31-9318-4409-a6ed-5bbfd22fac3e

## Source et couverture

- Ingest à partir de photos de livre (page recette + page plat) : arancini à la mozzarella avec riz à risotto et petits pois, rendement 24 pièces, boules ~6 cm, double panure, friture 180–190 °C.
- Les durées **prep / cook / total** reprennent l’imprimé; le **repos 30 min** après mélange est documenté dans les étapes et hypothèses car la clé `recipe.timing` du contrat ne prévoit que `prep`, `cook`, `total`.

## Choix éditoriaux Recipe2Video

- **Ouverture** : texture sur la croûte panée puis cassure et fil mozzarella (cheese pull) avant de revenir au risotto, conformément aux règles d’ouverture « texture d’abord » sans ligne d’ingrédients neutre.
- **Appareil** : la source mentionne des réglages type Thermomix; les prompts Seedance privilégient casserole / plaque pour l’ASMR et la lisibilité, sauf réponse favorable à la question ouverte sur le maintien du robot.
- **Fin** : plat céramique brune + salade de pousses alignés sur la photographie de droite; personnage Licorn visible, satisfait, sur le dernier segment.
- **Plans images fragiles** : trois références alimentaires planifiées pour `gpt_image_2` (risotto packable, sphère panée crue double couche, coupe filante) — voir `reference-plan.json`.

## Questions encore ouvertes

- Voir `recipe-analysis.json` → `clarifyingQuestions` (choix Thermomix vs casserole; type de mozzarella pour le cœur).

## Hypothèses acceptées

- Le fil mozzarella au hook suppose un produit récemment frit / tiède; un service froid est exclu pour ce payoff.

## Sync Git

- `checkpoint-manifest.commitSha` reflète le dernier commit où le contenu combiné (manifeste + artefacts) a été figé via `git commit --amend` après enrichissement analyse/changelog. La tête de branche après `git push` peut être un commit manifest-only au-dessus ; pour l’ingestion Recipe2Video, résoudre la ref distante de la branche du projet en priorité si le tout dernier SHA poussé est requis.
