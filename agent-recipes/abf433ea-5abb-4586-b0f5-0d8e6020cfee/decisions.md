# Decisions — Vanilla Layer Cake with Rose Buttercream

## Source and overrides

- Primary source: [A Classic Twist — Vanilla Layer Cake with Rose Buttercream](https://aclassictwist.com/vanilla-layer-cake-with-rose-buttercream/) (URL ingest).
- **Pan geometry (assumed for ingest):** four **6×2 inch (15×5 cm)** round layers for a tall 9:16 stack, per the source’s four-pan option (not two 8-inch layers).
- **Decoration (assumed):** smooth pale blush buttercream finish with a simple piped rosette border; no extra petals or macarons unless clarified later.
- **Tone:** ASMR food macro pacing (`asmr_food` preset); texture-first opening on rose powder + blush milk spiral; no ingredient lineup; no final-dish slice as hook.

## Assumptions accepted

- Hero cake on a **white cake stand** (~18–20 cm plate) on Licorn terrazzo: **15 cm** diameter, **four layers**, **12–14 cm** total height with frosting.
- Rose buttercream stays **pale blush**, not hot magenta.
- Bake segment uses **already-open** `@OvenWide` / `@OvenCloseup`; no oven-door choreography.
- **Destructive wedge slice** only in `segment-06`; `segment-07` (N-1) restores **fully intact** cake per `FinalDishVisual` for the standardized outro.

## Outro contract

- `segment-outro` uses `<APP_OVERRIDE>` with five fixed references and `logicalSceneIds: ["scene-outro"]`.
- `FinalDishVisual.prompt` leads with a short intact-cake sentence for outro embed, then GPT-Image detail.

## Production defaults captured

| Setting | Value |
| --- | --- |
| Style preset | asmr_food |
| Video model | seedance2 |
| Reference images | gpt_image_2 |
| TTS | eleven_multilingual_v2 |
| SFX | eleven_text_to_sound_v2 |

## Clarifying questions

Recorded in `recipe-analysis.json` (pan geometry and decoration style). Ingest artifacts use the assumptions above so production can proceed; update references and segment scale locks if answers change.

## Contract alignment (2026-05-19)

- **`recipe-analysis.json`:** `criticalTransformations`, `visualTextureOpportunities`, `possibleHooks`, and `promptPolicySources` are string arrays; `recipe.timing` uses `prep` / `cook` / `total`.
- **`logical-scenes.json`:** 37 scenes, texture-first hook with scene-02 payoff; ~78% detail.
- **`seedance-segments.json`:** 7 creative segments + standardized outro; integer `durationTarget` 5–15s; N-1 intact hero lock.
- **`suno-prompt.json`:** agent baseline per `contracts/suno-music.md`; operator 2–3 min edits documented in markdown.
