# Decisions — TikTok Wrap Hack (Crunchwrap Supreme)

## Source

- **URL:** https://iamafoodblog.com/tiktok-wrap-hack/
- **Edition:** Crunchwrap supreme (seasoned ground beef, lettuce, tomato, sour cream, chips, cheese, grill).
- **Stage:** `recipe_ingest` — full artifact baseline for Recipe2Video sync.

## Accepted assumptions

| Topic | Decision | Rationale |
| --- | --- | --- |
| Tortilla | Large flour ~25 cm (10 in) | Source prefers flour for fold integrity; stable scale lock. |
| Hero scope | Single wrap on island | Vertical video; avoids batch-of-six drift. |
| Grill surface | Induction skillet (`@InductionWide` / `@InductionCloseup`) | Source allows pan or panini press; skillet matches Licorn assets and avoids cloth-in-hand press risk. |
| Opening | Radial cut texture-first (scenes 1–2) | Pays off TikTok hack geometry immediately; avoids mise en place and final-dish slicing. |
| Destructive beats | Press, flip, cheese ooze only — no slice or bite on hero | Segment N-1 and `FinalDishVisual` must stay intact for standardized outro. |
| Clarifying questions | None at ingest | Source is complete for storyboard, references, and durations. |

## Production defaults (from ingest)

- Style preset: `asmr_food`
- Video model: `seedance2`
- Reference images: `gpt_image_2`
- TTS: `eleven_multilingual_v2`
- SFX: `eleven_text_to_sound_v2`

## Segment map

| Segment | Arc | Duration | Logical scenes |
| --- | --- | --- | --- |
| segment-01 | wrap_geometry_hook | 5s | 01–05 |
| segment-02 | taco_beef | 6s | 06–11 |
| segment-03 | wrap_fill | 7s | 12–18 |
| segment-04 | wrap_fold | 8s | 19–26 |
| segment-05 | grill_finish | 7s | 27–32 |
| segment-06 | hero_handoff | 5s | 33–38 |
| segment-outro | licorn_celebration_outro | 5s | app-controlled |

## Reference generation notes

Five recipe-specific GPT-Image 2 anchors: `TortillaRadialCut`, `WrapQuadrantsFilled`, `WrapFoldedTriangleRaw`, `WrapGrilledGolden`, `FinalDishVisual`. No character tags in `conditioningReferences`.

## Deferred / operator

- Suno full song: operator applies `fullSongOperatorEdits` in Suno UI before 2–3 min generation.
- Paid generation (Runway, Suno API, etc.) remains in Recipe2Video app only.
