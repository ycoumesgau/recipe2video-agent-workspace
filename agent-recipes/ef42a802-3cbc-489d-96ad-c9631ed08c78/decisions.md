# Decisions — Dubai Chewy Cookie (Du-Jjon-Ku)

## Source and references

- Primary source: [i am a food blog — Dubai Chewy Cookie](https://iamafoodblog.com/dubai-chewy-cookie/) (URL ingest).
- Secondary reference: [Catherine Zhang — Dubai Chewy Cookie viral recipe](https://zhangcatherine.com/dubai-chewy-cookie-viral-recipe/) for troubleshooting notes (sticky dough, chilling filling, cross-section presentation).
- **Tone:** ASMR food-porn / `asmr_food` preset; texture-first opening on kataifi butter sizzle with immediate crunch payoff (scene 2).

## Assumptions accepted

- **Yield:** 6 cookies (primary source); secondary source yields 10 — production locks **6** for scale continuity across references and hero shots.
- **Finished geometry:** 3.5–4 cm domed spheres, matte cocoa-dusted shell; filling balls 2.5–3 cm before wrap.
- **No bake:** marshmallow shell sets at room temperature; stovetop only for kataifi toast and marshmallow melt.
- **Plating:** each cookie in a white cupcake liner on Licorn terrazzo; cookies do not touch.
- **Tahini:** included per primary source (multidimensional note); optional on secondary source.

## Storyboard structure

- **36 logical scenes** across 6 content segments + standardized outro.
- **7 Seedance segments** (39 s content + 5 s outro): kataifi hook → filling → marshmallow shell → wrap → cross-section food porn → hero lock → outro.
- Destructive cross-section (segment-05) stays **before** motionless hero lock (segment-06) per outro contract.

## Reference images (GPT-Image 2)

Recipe-specific state frames: `ToastedKataifiGoldenFrame`, `PistachioFillingBallFrame`, `ChocolateMarshmallowGlossFrame`, `CrossSectionDubaiCookieFrame`, `FinalDishVisual`.

`FinalDishVisual` lead sentence for outro embed: six cocoa-dusted Dubai chewy cookies in cupcake liners, intact on terrazzo.

## Outro contract

- `segment-outro` uses `<APP_OVERRIDE>` with five canonical references and `logicalSceneIds: ["scene-outro"]`.
- `segment-06` (N-1) ends with cookies **intact and motionless**; no slice or bite on hero cookies.

## Production defaults captured

| Setting | Value |
| --- | --- |
| Style preset | asmr_food |
| Video model | seedance2 |
| Reference images | gpt_image_2 |
| TTS | eleven_multilingual_v2 |
| SFX | eleven_text_to_sound_v2 |

## Clarifying questions

None required for ingest; both URLs plus standard Licorn assumptions are sufficient to lock geometry and storyboard.
