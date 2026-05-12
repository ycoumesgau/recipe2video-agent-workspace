---
name: suno-music-generation
description: Prépare les prompts Suno (JSON + markdown) pour Recipe2Video — chanson longue streaming + extrait vertical, qualité créative type repo videos, contrat application strict.
---

# Suno Music Generation (Recipe2Video)

## Quand l’utiliser

- L’utilisateur demande une musique, une chanson, une bande-son ou un prompt Suno pour une recette.
- Il faut créer ou mettre à jour les artefacts `suno-prompt.json` **et** `suno-prompt.md` dans `agent-recipes/<videoId>/`.
- Transformer un plan créatif (storyboard, segments Seedance, analyse recette) en brief Suno copiable dans Suno **Custom Mode**.
- Version longue pour diffusion (Spotify, etc.) puis version courte pour TikTok / Shorts / Reels.

## Sorties obligatoires (contrat Recipe2Video)

L’application valide `suno-prompt.json` (Zod) et affiche l’assembly à partir de `sunoPromptV2` **ou** du markdown parsé. Toujours livrer **les deux** :

1. **`suno-prompt.json`** — JSON strict, pas de fences Markdown. `schemaVersion: 1` obligatoire.
2. **`suno-prompt.md`** — miroir lisible ; respecter le gabarit `references/suno-music-prompt-template.md` (sections `##` de niveau 2 pour les cinq champs Suno).

### Forme JSON (`suno-prompt.json`)

Les chaînes dans `fields` doivent être **identiques** au contenu prêt à coller dans Suno (après remplacement des placeholders du template) :

```json
{
  "schemaVersion": 1,
  "status": {
    "recipeName": "string",
    "goal": "Full song 2–3 min for streaming; 45–90s excerpt for vertical edit",
    "model": "Suno 5.5 Advanced / Custom Mode",
    "targetDuration": "2–3 minutes (full); excerpt for short video"
  },
  "fields": {
    "styleOfMusic": "…",
    "excludeStyles": "…",
    "title": "…",
    "autoLyricsPrompt": "…",
    "shortVersionPlan": "…"
  },
  "instructions": {
    "voice": "optional — rappels voix / persona Suno",
    "structure": "optional — rappels longueur / hook",
    "workflowNotes": "optional — notes opérateur"
  },
  "qualityChecks": ["…"]
}
```

- `fields.styleOfMusic` ↔ corps du bloc **Style of Music** (contenu du fence ```text uniquement, sans consignes lyriques).
- `fields.excludeStyles` ↔ **Exclude Styles**.
- `fields.title` ↔ **Title**.
- `fields.autoLyricsPrompt` ↔ contenu **Auto Lyrics Prompt** (le texte à coller dans le champ lyrics auto, moins de 3000 caractères).
- `fields.shortVersionPlan` ↔ **Short Version To Extract Later** (plan de montage / extrait).

## Sources à lire (dans l’ordre)

1. `recipe-analysis.json`
2. `logical-scenes.json`
3. `seedance-segments.json`
4. `decisions.md` si besoin de contexte produit
5. `suno-prompt.md` et `suno-prompt.json` existants avant modification

## Workflow

1. Identifier les arcs culinaires, le hook visuel, les money shots et le hero final (depuis scènes / segments).
2. Extraire des mots-images chantables : ingrédients signatures, textures, couleurs, gestes sensoriels.
3. Rédiger avec le template `references/suno-music-prompt-template.md` : **Status**, **Intent**, **Session notes**, puis les cinq champs Suno.
4. Remplir `suno-prompt.json` avec les mêmes contenus finaux dans `fields` + métadonnées cohérentes dans `status` / `instructions` / `qualityChecks`.
5. Ne pas écrire les paroles finales dans le livrable sauf demande explicite de l’utilisateur — seulement le **prompt** qui demande à Suno de générer des paroles.

## Règles Suno (alignées repo `videos`)

- Par défaut, prompts copiables en **anglais** ; paroles demandées en **anglais**.
- Ne pas mélanger style musical et lyrics : **`Auto Lyrics Prompt`** ne contient pas genre, production, instruments, mix ni direction vocale textuelle.
- Le style musical va uniquement dans **Style of Music** (`fields.styleOfMusic`).
- Le prompt lyrics demande des paroles **originales**, pas une copie de paroles complètes rédigées à la main.
- Demander des lignes courtes, chantables, répétables, avec hook découpable en version courte ; **section tags** (`[Verse 1]`, etc.) comme dans le template.
- Garder **autoLyricsPrompt** sous **3000 caractères**, avec marge.
- Pour l’identité vocale : recommander **Voices** / persona Suno quand disponible (cf. section Session notes du template).
- Ne jamais demander d’imiter un artiste réel, une voix protégée, une marque ou un style nommé par artiste.
- Éviter les lyrics tutoriel : pas de quantités, pas d’étapes numérotées, pas de mode d’emploi culinaire.
- Transformer la recette en images chantées : matière, couleur, texture, émotion, geste simple.
- Cohérence vidéo : même recette, mêmes payoffs sensoriels, même final satisfait.
- Suno reste **manuel** côté utilisateur : pas d’appel API depuis l’agent.

## Style musical par défaut

Si l’utilisateur ne fournit pas de style, partir sur ce bloc (à adapter à la recette) :

```text
K-pop electronic pop with crisp four-on-the-floor kicks, rubbery synth bass, and playful staccato percussion; verse keeps it nimble with clipped phrasing and little vocal chops, pre-chorus opens into stacked harmonies and a rising synth sweep, chorus hits bright and glossy with gang vocals and a candy-sweet hook. Add sparkle FX, reversed bell swells, and a tiny glitch fill before each drop. Clean, punchy mix with wide neon sheen and close-mic lead vocals., k-pop, pop, electronic
```

## Validation avant livraison

- `Style of Music` est séparé de `Auto Lyrics Prompt` (dans le `.md` **et** dans `fields`).
- `Auto Lyrics Prompt` : anglais, pas de consignes musicales, moins de 3000 caractères.
- `Exclude Styles` : interdits clairs (genres parasites, artistes réels, marques, lyrics non souhaités, tutoriel recette).
- Chanson pensée **2 à 3 minutes** en version longue ; refrain / hook **réexploitable** pour une vidéo **45–90 s** (voir Short Version).
- Les sections clés du template sont remplies (Intent, imagery, structure lyrics).
- `suno-prompt.json` est **valide JSON** et **strictement** conforme au schéma attendu par Recipe2Video.
- Mettre à jour `changelog.md` avec la raison du changement Suno.

## Référence

Le fichier `references/suno-music-prompt-template.md` est la **source créative** (niveau repo `videos`) ; le JSON est la **source structurée** pour l’app. Les deux doivent rester synchronisés après édition.
