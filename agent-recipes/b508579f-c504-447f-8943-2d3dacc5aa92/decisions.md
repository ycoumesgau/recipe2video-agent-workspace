# Decisions - Sushi Bowl

## Source and scope

- Recipe source: Love and Lemons sushi bowl URL, plus linked Love and Lemons pages for baked tofu, spicy mayo, and quick pickled radishes because the main recipe references those components by name.
- Production style: `asmr_food`.
- Video generation path: Seedance 2 References mode only. No Runway, Suno, Supabase, Mux, Remotion, or paid generation was launched.

## Creative structure

- Opening uses a spicy mayo ribbon as the texture-first hook instead of ingredient mise en place or final-dish slicing.
- Scene 2 immediately clarifies the hook by anchoring the sauce beside warm rice on the Licorn kitchen island.
- Logical scene count is 36 to satisfy the 30-48 scene contract.
- Seedance segment count is 8 to satisfy the 5-10 segment contract while keeping each prompt short and action-focused.
- Detail/context balance is planned around mostly macro food texture, with context shots only when they anchor a transformation or final hero.

## Food and scale assumptions

- Optional pickled radishes are included because their pink color, brine pour, and crisp slices materially strengthen the edit.
- Spicy mayo is treated as regular mayonnaise unless the operator later chooses the vegan mayo variation.
- One visible serving bowl is used for assembly and final hero; the source makes 4 servings, but the video focuses on one 16 to 18 cm bowl.
- Rice fills the bottom third of the bowl.
- Baked tofu is locked as 1-inch or 2.5 cm cubes, about 8 to 10 visible cubes per bowl.
- Fresh toppings are locked as about half an avocado, half a mango, and half a Persian cucumber per bowl.
- Pickled radish quantity is locked as six to eight thin slices per bowl.
- Nori is locked as 2 to 4 mm strips, not whole sheets or sushi roll wrappers.
- Spicy mayo garnish is locked as 1 to 2 tablespoons, not a flood.

## References and generation readiness

- Global kitchen continuity pair is present in every Seedance segment: `@KitchenLayoutContextWide` plus a shot-specific kitchen view.
- Existing asset references are limited to real files or documented aliases from the asset reference skill.
- After pulling `origin/main`, the spatula-family guidance was refreshed: tofu coating now uses `@SiliconeSpatula` explicitly instead of the legacy `@Spatula` alias.
- Recipe-specific state references are planned for sauce, tofu, rice, fresh toppings, pickled radishes, nori strips, assembly, and final hero.
- These recipe-specific references are marked `generated_reference_needed` in `reference-plan.json`; no image generation was run in this workspace.

## Open clarifications

- Confirm whether optional pickled radishes should stay in the production version.
- Confirm whether spicy mayo should be regular mayo or vegan mayo.

These clarifications are not blockers for planning because the current assumptions are explicit in `recipe-analysis.json`, `reference-plan.json`, and `seedance-segments.json`.
