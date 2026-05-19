# Decisions — Small Batch Baked Ube Mochi Donuts

## Production defaults (ingest)

| Field | Value |
| --- | --- |
| Style preset | `asmr_food` |
| Video model | `seedance2` |
| Reference image model | `gpt_image_2` |
| TTS | `eleven_multilingual_v2` |
| SFX | `eleven_text_to_sound_v2` |
| Agent | `composer-2.5` (fast mode) |

## Creative direction

- **Opening:** texture-first macro pour of violet mochi batter into a metal donut cavity; scene 2 pays off with meniscus fill and surface tension at the brim.
- **No** mise-en-place ingredient lineup, **no** final-dish slicing hook.
- **Scale lock:** Wilton-standard rings — outer diameter **3 in / 7.5–8 cm**, center hole **~1 in / 2.5 cm**, **six** cavities, **flat bottom** (minimal rise per source).
- **75–80% detail / 20–25% context** across 42 logical scenes; texture payoff every 3–5 scenes.
- **Destructive food-porn** (glaze dip, sprinkle rain) lives in **segment-06** only; **segment-07** and **segment-outro** keep donuts **intact and motionless** on the counter/rack.
- **Oven:** use `@OvenWide` / `@OvenCloseup` with tray slide only — no oven door hinge action in Seedance prompts.
- **No donut pan library asset:** pan described in prompts; recipe-state references carry ring topology.

## Assumptions accepted

- Six-donut small batch on wire rack for hero and `FinalDishVisual`.
- Deep violet-lilac color from ube jam + extract + purple coloring as in source photos.
- Mixed festive sprinkles until operator answers `sprinkle-palette` clarifying question.

## Reference strategy

- GPT-Image 2 states: liquid batter, batter-filled pan, baked tray, single glazed donut, `FinalDishVisual` hero.
- Hard cut baked reveal (raw filled pan → baked rings) instead of morphing rise.
- `conditioningReferences` use kitchen + cookware/utensil library tags only (no character anchors).

## Pending

- Operator input on sprinkle palette (`recipe-analysis.json` → `clarifyingQuestions[0]`).
