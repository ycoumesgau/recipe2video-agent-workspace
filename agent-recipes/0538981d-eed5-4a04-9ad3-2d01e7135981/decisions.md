# Decisions — Chicken Enchiladas

## Project

- Video ID: `0538981d-eed5-4a04-9ad3-2d01e7135981`
- Source type: URL
- Source URL: `https://www.gimmesomeoven.com/best-chicken-enchiladas-ever/`
- Target duration: 60 seconds
- Style preset: `asmr_food`
- Video model: `seedance2`
- Image model for reference generation: `gpt_image_2`
- TTS model: `eleven_multilingual_v2`
- SFX model: `eleven_text_to_sound_v2`

## Creative decisions

- Use the source recipe's flour-tortilla Tex-Mex version as the primary story path.
- Open texture-first on glossy red enchilada sauce over rolled tortillas, then immediately clarify sauce viscosity with a spoon-coating shot.
- Compress the linked homemade red enchilada sauce into visual sauce states instead of expanding the full linked sauce recipe.
- Use 30 logical scenes for editorial reasoning and 8 Seedance 2 References segments for generation.
- Keep the video mostly detail-driven, with context shots only to clarify assembly, oven transition, and final hero.
- End on a saucy cheese-pull serving beat followed by the finished pan in the Licorn kitchen with the character visible and satisfied.

## Reference decisions

- Plan recipe-specific state references for: red sauce viscosity, cooked chicken filling, rolled unbaked pan, sauced-and-cheesed unbaked pan, baked pan, garnished pan, and served cheese pull.
- Use the common global references named in the workspace skill: `@KitchenIslandDefault`, `@KitchenIslandOverhead`, `@InductionCloseup`, `@OvenWide`, `@OvenCloseup`, `@CharacterSheet`, `@CharacterExpressions`, `@PoseTopDown`, `@PoseFront`, `@Spoon`, and `@Spatula`.
- The repository checkout does not include an `assets/` directory despite the workspace documentation mentioning it; reference names therefore follow the canonical names published in `.cursor/skills/asset-reference-system/SKILL.md` and existing example patterns.

## Assumptions and trade-offs

- Exact count of eight tortillas is less important than stable readable geometry: parallel rolled cylinders in a rectangular baking dish.
- Corn tortilla variation, green sauce variation, and alternate proteins are excluded from the main storyboard to keep the 60-second video coherent.
- The chicken cooking step is shown with hard cuts rather than a long raw-to-cooked transformation.
- Garnishes are treated as optional source toppings but included for color, freshness, and final contrast.
- No Runway, Suno, Supabase, Mux, Remotion, OpenAI, or other paid generation service was launched. Suno content is a copy-ready manual prompt only.

## Not ready / follow-up

- Validation after hardening updated `recipe-analysis.json` as strict JSON before the GitHub checkpoint; all required planning artifacts remain ready for Recipe2Video validation.
- Recipe-specific image references are only planned; the production app must generate, review, store, and attach those references before Seedance execution.
