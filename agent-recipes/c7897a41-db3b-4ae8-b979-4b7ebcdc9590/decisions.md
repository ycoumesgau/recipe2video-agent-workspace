# Decisions — Chicken Enchiladas

## Source and scope

- Ingested the main recipe from `https://www.gimmesomeoven.com/best-chicken-enchiladas-ever/`.
- Also ingested the linked homemade red enchilada sauce from `https://www.gimmesomeoven.com/red-enchilada-sauce/` because the source identifies the sauce as the key flavor and visual binder.
- No blocking clarifying questions remain; `recipe-analysis.json` records an empty `clarifyingQuestions` array.

## Production defaults applied

- Style preset: `asmr_food`
- Video model: `seedance2`
- Seedance workflow: References mode, 1080:1920 vertical assumptions, no first/last keyframe production pattern.
- Image model for planned food-state references: `gpt_image_2`
- TTS model noted from request: `eleven_multilingual_v2`
- SFX model noted from request: `eleven_text_to_sound_v2`
- Cursor agent model noted from request: `gpt-5.5`, high reasoning, fast mode disabled.

## Creative/story decisions

- Opening hook starts on a texture-first future payoff: glossy red enchilada sauce pouring over parallel tortilla rolls.
- Scene 2 immediately clarifies the hook by cutting back to the chili roux and homemade red sauce process.
- The storyboard uses 36 logical scenes mapped into 8 Seedance segments, keeping the app-required 30-48 logical scene range and 5-10 Seedance segment range.
- Repetitive rolling is compressed: one tortilla is assembled and rolled, then a hard cut reveals the full pan.
- Final sequence ends in the Licorn kitchen context with the character visible and satisfied, while the food remains the foreground hero.

## Culinary and generation risk decisions

- Flour tortillas are used because they are the source default and create clearer rolling geometry for video.
- The red sauce receives a dedicated generated state reference because thickness and chile color are fragile; it must not look like tomato soup.
- Chicken cooking uses a hard cut from raw/early pan action to a cooked filling state to avoid unreliable continuous raw-to-cooked transformation.
- Parallel roll geometry, pre-bake pan, baked pan, final topped pan and served interior each receive planned recipe-state references.
- Tiny garnish drift is reduced by limiting toppings to bold, readable source options: cilantro, avocado, red onion, crema and cotija.

## Artifact readiness

- `recipe-analysis.json`: ready.
- `logical-scenes.json`: ready.
- `seedance-segments.json`: ready for Recipe2Video validation and later Seedance execution.
- `reference-plan.json`: ready; generated references are planned only and not created in this workspace.
- `suno-prompt.md`: ready for manual Suno use; no Suno API call was made.
- `changelog.md`: ready.
