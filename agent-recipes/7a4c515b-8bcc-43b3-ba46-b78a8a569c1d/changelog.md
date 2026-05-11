# Changelog — `7a4c515b-8bcc-43b3-ba46-b78a8a569c1d`

## 2026-05-11

- Création du projet d’ingest photo : `recipe-analysis.json` avec ingrédients, étapes recontextualisées hors Thermomix pour la vidéo, timings `prep` / `cook` / `total`, listes conformes (chaînes seules pour transformations, textures, hooks, politiques).
- Ajout de `logical-scenes.json` : **36** scènes (30–48), arc macro-first, balance détail/contexte, fin avec personnage satisfait et plat héros.
- Ajout de `seedance-segments.json` : **7** segments mode References, ratio 1080:1920 implicite, audio ASMR intégré sans parole ni musique, rôles explicites pour `@KitchenIslandDefault` et références cuisine / personnage.
- Ajout de `reference-plan.json` : actifs globaux existants + **5** états recette planifiés en génération `gpt_image_2` pour verrouiller liaison risotto, scellage, double panure, dorure et coupe filante.
- Rédaction de `suno-prompt.md` (champs Suno en anglais, par `.cursor/rules/suno-music.mdc`).
- Documentation des choix et hypothèses dans `decisions.md`.
- Mise à jour de `checkpoint-manifest.json` : `commitSha` = commit Git du bundle `recipe-analysis.json` + scènes + segments + plan + Markdown (`de07546…` dans cette livraison) ; la **tête de branche** après le commit du manifeste est le SHA complet à utiliser côté outillage pour récupérer aussi le manifeste (voir message JSON agent).
