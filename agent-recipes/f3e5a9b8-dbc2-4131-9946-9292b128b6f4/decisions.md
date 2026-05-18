# Decisions - Lasagne dumpling

## Source and scope

- Video ID: `f3e5a9b8-dbc2-4131-9946-9292b128b6f4`
- Source type: URL
- Source URL: https://bonpourtoi.ca/recettes/lasagne-dumpling/
- Stage: `recipe_ingest`
- Required artifacts are ready because the source recipe includes ingredients, timing, method, pan size, yield and serving guidance.

## Creative direction honored

- The creator asked to make the lasagne dumpling "really sexy and food porn"; the storyboard opens on the finished soy-gloss surface and immediately pays it off with a layered turning-spatula lift.
- The edit avoids neutral mise en place. Utility steps are compressed into tactile ASMR beats: sticky filling, wrapper slap, water beads, steam burst, soy drizzle, sesame rain and layered cutaway.
- The final shot keeps the Licorn character visible and satisfied, but food stays dominant.

## Reference strategy

- Existing assets carry nearly all production references: kitchen continuity, overhead island, induction, character, poses and utensils.
- Only one recipe-specific generated reference is planned: `@FinishedDumplingLasagnaCutaway`.
- Reason for this exception: "lasagne" strongly risks model drift toward tomato sauce, cheese pull and long noodles, while "dumpling" risks folded individual dumplings. A final top/cutaway state reference is the minimum useful safeguard for the most important food-porn hook and payoff.
- No intermediate generated references are planned for raw filling, wrapper layering, hydration or steam cooking; these are handled through prompt physics and existing kitchen/utensil assets.

## Scale and geometry locks

- Pan: 8 in / 20 cm square pan for 4 portions.
- Final slab: compact, about 3-5 cm tall.
- Dumpling wrappers: flat palm-size wrappers, approximately 8-10 cm wide, arranged side by side with minimal overlap and trimmed/tucked as needed.
- Filling layers: thin, about 3-5 mm each.
- Final lifted portion: one quarter of the 20 cm pan, not a giant casserole slice.
- Negative locks: no tomato sauce, no cheese, no cheese pull, no long lasagna noodles, no folded dumplings, no oversized pan, no miniature pan.

## Production defaults

- Style preset: `asmr_food`
- Video model: `seedance2`
- Image model for reference generation: `gpt_image_2`
- TTS model: `eleven_multilingual_v2`
- SFX model: `eleven_text_to_sound_v2`
- Cursor agent model: `gpt-5.5`
- Cursor agent reasoning: `high`
- Cursor agent fast mode: disabled

## Open gaps

- No blocking clarifying questions remain for ingest.
- The exact commercial wrapper shape may vary; the plan assumes flat palm-size wrappers and relies on scale locks instead of asking because the recipe itself notes about 20 wrappers for a 20 cm square pan.

## Main sync update - 2026-05-18

- Pulled `origin/main` into the recipe branch and applied the updated asset-reference skills.
- Replaced legacy generic spatula references with `@SiliconeSpatula` for flexible filling spreading and `@TurningSpatula` for rigid supported portion lifts.
- No new generated recipe-state references were added; the plan still relies on one final cutaway reference only.

## Main sync update - 2026-05-18 11:35 UTC

- Pulled the latest `origin/main` again and applied the refreshed reference-image generation contract.
- Added `conditioningReferences` to `FinishedDumplingLasagnaCutaway`: `KitchenIslandDefault`, `baking_dish`, and `TurningSpatula`.
- Kept character references out of conditioning anchors, per the updated contract.

## Main sync update - 2026-05-18 14:38 UTC

- Pulled the latest `origin/main` and applied the refreshed Seedance duration contract.
- Corrected all Seedance segments so `durationTarget` is an integer from 5 to 15 seconds; no segment remains below 5 seconds.
- Re-timed the 5-second prompt timing bullets for segments 01, 06, 07, and 08 while preserving the same creative beats.
