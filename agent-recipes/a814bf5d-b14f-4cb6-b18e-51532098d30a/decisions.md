# Decisions — Chicken Enchiladas

## Source and scope

- Recipe source: Gimme Some Oven, "Chicken Enchiladas", URL recipe card and article content.
- Source type: `url`.
- Video ID: `a814bf5d-b14f-4cb6-b18e-51532098d30a`.
- Target duration: 60 seconds.
- Style preset: `asmr_food`.
- Video generation model planned: `seedance2`.
- Reference image model planned: `gpt_image_2`.
- TTS model default recorded: `eleven_multilingual_v2`.
- SFX model default recorded: `eleven_text_to_sound_v2`.

## Editorial decisions

- Open on a macro sauce-and-cheese hook: glossy red enchilada sauce pouring over rolled tortillas, followed immediately by cheese rain.
- Clarify the hook within the first 7 seconds by cutting back to sauced tortilla filling and rolling, so the viewer understands the dish is chicken enchiladas rather than a generic casserole.
- Use 36 logical scenes for editorial reasoning and 8 Seedance segments for production generation.
- Keep the visual balance mostly detail/macro shots, with short context resets before assembly, baking, garnish, and final hero.
- End with the finished enchilada tray in the Licorn kitchen context and the character visible and satisfied.

## Culinary assumptions

- Flour tortillas are the default because the source recipe uses 8 large flour tortillas and they roll cleanly for generation.
- Black beans are the default bean because they are listed in the recipe card.
- The homemade red enchilada sauce is represented as a compact visual sub-recipe because the source identifies it as the flavor anchor.
- Optional toppings are selected for color and texture: sour cream, cotija, cilantro, red onion, and avocado.
- The video should show food physics and transformations, not tutorial quantities or procedural narration.

## Seedance reference decisions

- Use Seedance References mode rather than first/last keyframes.
- Use global kitchen and character references in every segment where they stabilize identity.
- Use recipe-specific state references for fragile or easily misread states:
  - `SauceTextureFrame`
  - `CookedChickenFillingFrame`
  - `RolledEnchiladasRawFrame`
  - `BakedBubblingEnchiladasFrame`
  - `FinishedChickenEnchiladasFrame`
- Preserve rolled enchilada topology with hard cuts and references; do not ask the model to morph raw rolls into a baked tray in one continuous shot.
- All Seedance prompts specify hard cuts, mandatory timing, ASMR kitchen audio only, no speech, no voiceover, no music, no text on screen, and no extra shots.

## Suno decision

- Suno is a separate manual workflow. The prompt in `suno-prompt.md` is copy-ready and does not imply any API call.
- Lyrics prompt uses food imagery and emotion, not recipe steps, quantities, protected voices, brands, or artist imitation.

## Generation boundary

- No Runway, Suno, Supabase, Mux, Remotion, OpenAI, or paid generation service was launched.
- All recipe-specific images remain planned references for Recipe2Video to validate, generate, approve, and execute later.

## Artifact readiness

- `recipe-analysis.json`: ready.
- `logical-scenes.json`: ready.
- `seedance-segments.json`: ready.
- `reference-plan.json`: ready.
- `suno-prompt.md`: ready.
- `decisions.md`: ready.
- `changelog.md`: ready.
