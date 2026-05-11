# Decisions — `05ea0559-21c9-487c-9bf7-415090f9a5a4`

## Source and scope

- Recipe interpreted from Gimme Some Oven “Chicken Enchiladas” URL; linked homemade red enchilada sauce is treated as a companion preparation (article strongly recommends it) without fully scripting every roux beat until production confirms depth (see `recipe-analysis.json` `clarifyingQuestions.sauce-depth`).
- Visual default follows the article’s stated preference for **large flour tortillas** for easier rolling; corn-tortilla styling remains a documented variation in analysis and is gated behind `clarifyingQuestions.tortilla-style`.

## Editorial

- Opening obeys Recipe2Video core: **texture-first** macro sauce simmer (scenes 1–2) rather than ingredient grid or final slice.
- Detail-heavy board: 38 logical scenes (~context/detail mix per `logical-scenes.json`) mapping to **7** Seedance References segments (within 5–10 guidance).
- Closure includes Licorn character visibility with finished dish (`segment-07`, `scene-38`).

## Fragile states

- **Revision — library-only image inputs:** no standalone `recipe_state` PNGs (`gpt_image_2` or otherwise) for this video. Licorn library assets remain the only Seedance image references; sauce color, casserole grid, bake blistering, and modest cheese pull are spelled out in each segment’s English prompt (explicit negatives, duration blocks, food adjectives). Exec may still use `gpt_image_2` workspace defaults for other tooling, but planning does not allocate custom dish stills analogous to overlapping arancini reference stacks.

## Production defaults (record)

- Style preset: `asmr_food`; video: `seedance2`; workspace default reference image tool remains `gpt_image_2` (not used here for dish-specific uploads); TTS: `eleven_multilingual_v2`; SFX: `eleven_text_to_sound_v2`; ingest agent: Composer fast mode metadata only.

## Risks accepted

- Oven UI / appliance text may appear in wide shots; prompts bias toward macro and negative “no readable UI” but occasional retake risk remains.
- Cheese pull credibility now depends on wording (“few centimeters”, “snap quickly”) versus a capped reference still—retake risk rises slightly if Seedance ignores stretch negatives.
