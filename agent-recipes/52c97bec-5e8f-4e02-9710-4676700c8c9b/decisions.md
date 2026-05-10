# Decisions - Recipe Ingest

Video ID: `52c97bec-5e8f-4e02-9710-4676700c8c9b`

## Source

- Source type: URL
- Recipe URL: https://www.gimmesomeoven.com/best-chicken-enchiladas-ever/
- Linked sauce URL used for the sauce sub-recipe: https://www.gimmesomeoven.com/red-enchilada-sauce/

## Production defaults applied

- Target duration: 60 seconds
- Style preset: `asmr_food`
- Video model: `seedance2`
- Reference image model for planned state references: `gpt_image_2`
- TTS model noted from request: `eleven_multilingual_v2`
- SFX model noted from request: `eleven_text_to_sound_v2`
- Seedance workflow: References mode, vertical 1080:1920, no first/last keyframe production pattern.

## Editorial decisions

- Selected the glossy red enchilada sauce smear as the opening hook because it is texture-first and immediately clarifies the recipe's signature sauce.
- Preserved the source recipe default of large flour tortillas and black beans.
- Included the linked homemade red enchilada sauce as a sub-recipe because the source identifies it as the main flavor differentiator.
- Compressed the 1-hour cooking process into 36 logical scenes and 8 Seedance segments totaling 60 seconds.
- Kept the final cheese pull and Licorn hero plate for the ending rather than the opening, avoiding a final-dish hook.
- Planned generated recipe-state references for sauce texture, unbaked row geometry, baked cheese blister state, and final plated state. These are references only; no paid generation was launched.

## Remaining gaps

- No blocking gaps. The source recipe provides enough ingredients, steps, timing, and serving cues for planning.
- Optional variations from the source, such as corn tortillas, green sauce, vegetarian filling, or alternate proteins, were not used.

## Artifact readiness

- `recipe-analysis.json`: ready
- `logical-scenes.json`: ready
- `seedance-segments.json`: ready
- `reference-plan.json`: ready
- `suno-prompt.md`: ready for manual Suno workflow
- `changelog.md`: ready
- `checkpoint-manifest.json`: ready; this retry uses the checkpoint contract that commits and pushes the recipe artifacts on the project branch.
