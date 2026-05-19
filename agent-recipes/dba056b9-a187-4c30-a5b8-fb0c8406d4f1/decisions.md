# Decisions — Lemon Butter Orecchiette with Burrata

## Source and overrides

- Primary source: [Del's Cooking Twist lemon butter pasta with burrata](https://www.delscookingtwist.com/lemon-butter-pasta-with-burrata-cheese/) (URL ingest).
- **Pasta:** orecchiette replaces spaghetti (creator directive) for cup-shaped sauce pockets on camera.
- **Topping:** dry-roasted pistachio rough chop added as supplemental sub-recipe and final crunch layer (creator directive).
- **Tone:** ASMR food-porn / seductive macro pacing (`asmr_food` preset); 75–80% detail, texture-first opening on lemon zest + brown butter foam.

## Assumptions accepted

- Single hero portion in a **24–26 cm** shallow bowl on Licorn terrazzo.
- One **8–10 cm** burrata ball on the hero plate; creamy stracciatella spill on tear.
- Caper crumb portion ~1 loosely packed cup for one shower, not a mountain.

## Outro contract

- `segment-outro` uses `<APP_OVERRIDE>` with five fixed references.
- `segment-07` (N-1) ends with the dish **intact and motionless**; fork twirl and burrata tear live in `segment-06` only.

## Production defaults captured

| Setting | Value |
| --- | --- |
| Style preset | asmr_food |
| Video model | seedance2 |
| Reference images | gpt_image_2 |
| TTS | eleven_multilingual_v2 |
| SFX | eleven_text_to_sound_v2 |

## Clarifying questions

None required for ingest; source plus creator notes are sufficient to lock geometry and storyboard.

## Contract alignment (2026-05-19)

- **`seedance-segments.json`:** `timing` entries use `start-endXs: beat` colons; `promptInitial` immediately follows `prompt`; outro has empty `beats` / `timing` / `negatives` (app-injected) and canonical reference roles.
- **`suno-prompt.json`:** agent baseline lyrics opener, lyric-style 45–90 s clause with period, `Structure:` header, no operator duration baked into `fields`; `instructions.fullSongOperatorEdits` matches `contracts/suno-music.md`.
