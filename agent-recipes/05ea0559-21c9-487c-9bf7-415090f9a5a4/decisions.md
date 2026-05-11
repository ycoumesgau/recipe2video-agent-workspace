# Decisions — `05ea0559-21c9-487c-9bf7-415090f9a5a4`

## Source and scope

- Recipe interpreted from Gimme Some Oven “Chicken Enchiladas” URL; linked homemade red enchilada sauce is treated as a companion preparation (article strongly recommends it) without fully scripting every roux beat until production confirms depth (see `recipe-analysis.json` `clarifyingQuestions.sauce-depth`).
- Visual default follows the article’s stated preference for **large flour tortillas** for easier rolling; corn-tortilla styling remains a documented variation in analysis and is gated behind `clarifyingQuestions.tortilla-style`.

## Editorial

- Opening obeys Recipe2Video core: **texture-first** macro sauce simmer (scenes 1–2) rather than ingredient grid or final slice.
- Detail-heavy board: 38 logical scenes (~context/detail mix per `logical-scenes.json`) mapping to **7** Seedance References segments (within 5–10 guidance).
- Closure includes Licorn character visibility with finished dish (`segment-07`, `scene-38`).

## Fragile states

- Generated references (`gpt_image_2` per production defaults) planned for: simmering sauce skin, unbaked casserole geometry, blistered bake surface, modest cross-section cheese pull. No paid generation executed in this workspace run.

## Production defaults (record)

- Style preset: `asmr_food`; video: `seedance2`; reference images: `gpt_image_2`; TTS: `eleven_multilingual_v2`; SFX: `eleven_text_to_sound_v2`; ingest agent: Composer 2 fast mode enabled (metadata only here).

## Risks accepted

- Oven UI / appliance text may appear in wide shots; prompts bias toward macro and negative “no readable UI” but occasional retake risk remains.
- Cheese pull segments intentionally cap elasticity via `EnchiladaCrossSectionPull` reference to avoid CGI rubber.
