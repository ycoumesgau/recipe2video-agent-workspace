# Decisions — Crookie (Croissant Cookie)

## Source and references

- **Primary source (crookie assembly):** [Aux délices du palais — Crookie le fameux croissant cookie](https://www.auxdelicesdupalais.net/crookie-le-fameux-croissant-cookie.html) (URL ingest).
- **Croissant sub-recipe (creator-mandated):** [L'Atelier des Chefs — Pâte levée feuilletée, les croissants](https://www.atelierdeschefs.fr/recettes/32139/pate-levee-feuilletee-les-croissants/) — 1 tour simple + 1 tour double, repos 25 min au froid, cuisson ~15 min à 180°C, sirop sucre/eau à la sortie.
- **Creator instruction (explicit):** ne pas utiliser de croissants du commerce ; montrer la réalisation maison du croissant avant le crookie.
- **Tone:** `asmr_food` — ouverture texture-first sur le pli feuilleté (scène 1), payé en scène 2 par les strates visibles.

## Assumptions accepted

- **Yield vidéo:** 8 crookies cités sur la source blog ; production verrouille **3 crookies héros** à l’îlot + 1 plan solo pour `FinalDishVisual` (échelle 14–16 cm par pièce).
- **Viennoiserie:** croissants uniquement (pas de pain au chocolat dans le montage principal — option blog écartée).
- **Compression narrative:** repos longs et batch de 20 croissants (recette ADC) compressés par hard cuts + références d’état ; pas de timeline calendaire à l’écran.
- **Food-porn destructif:** cassure centre fondant limitée au **segment-05** ; **segment-06** et outro : crookie intact et immobile.

## Storyboard structure

- **36 logical scenes** sur 6 blocs créatifs + placeholder outro.
- **7 segments Seedance** (34 s contenu + 5 s outro) : lamination → cuisson croissant → cookie → garniture → révélation fondante → hero lock → outro Licorn.
- Scène 2 paye la scène 1 (strates feuilletées après le premier pli).

## Reference images (GPT-Image 2)

États fragiles : `LaminatedDoughLayersFrame`, `RawCroissantCrescentsFrame`, `BakedCroissantGoldenFrame`, `CookieDoughBallsFrame`, `CrookiePreBakeFrame`, `CrossSectionCrookieGooeyFrame`, `FinalDishVisual`.

`FinalDishVisual` — phrase courte outro (≤ 280 car.) : crookie doré intact, pécan et pépites, sur îlot terrazzo, 14–16 cm.

## Outro contract

- `segment-outro` : `<APP_OVERRIDE>`, cinq références canoniques, `logicalSceneIds: ["scene-outro"]`.
- Segment N-1 (`segment-06`) : plat final intact, sans contact personnage/nourriture.

## Production defaults captured

| Setting | Value |
| --- | --- |
| Style preset | asmr_food |
| Video model | seedance2 |
| Reference images | gpt_image_2 |
| TTS | eleven_multilingual_v2 |
| SFX | eleven_text_to_sound_v2 |
| Cursor agent | composer-2.5 (fast mode) |

## Clarifying questions

Aucune — la consigne croissant maison + les deux URLs suffisent pour verrouiller géométrie, références et storyboard.
