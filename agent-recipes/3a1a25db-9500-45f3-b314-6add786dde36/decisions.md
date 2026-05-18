# Decisions - Inside-Out Crispy Rice Paper Rolls

Video ID: `3a1a25db-9500-45f3-b314-6add786dde36`
Source: https://toprecipesfood.com/inside-out-crispy-rice-paper-rolls/
Stage: recipe_ingest

## Creative direction

- Interpreted the creator note "really sexy and food porn" as sensual macro food photography: crackly shell, glossy peanut-lime sauce, bright cut-face color, close ASMR, and appetite-first pacing.
- Kept the tone food-centered and non-explicit; no body-focused imagery or mouth close-up is required.
- Opened on a crack-and-dip texture hook, then immediately clarified the inside-out rice-paper geometry so the viewer understands the trick.

## Reference strategy

- Honored the instruction to avoid generated intermediate reference images unless indispensable.
- Planned only existing global references: kitchen continuity, Licorn character, poses, expressions, tongs, whisk, and spoon.
- Deferred recipe-specific generated food-state references. If Seedance validation later shows geometry drift, the minimal fallback is one final cooked-and-cut roll reference only.

## Scale and continuity locks

- Working assumption: standard rice-paper wrappers make small cooked rolls about 10-12 cm long and 3-4 cm diameter.
- Prompts explicitly say not oversized, not burrito-sized, and not miniature.
- Pan-frying is shallow on a nonstick skillet over the induction plate: no flame, no deep frying, no cloth-in-hand hot handling.
- Garnish is capped at two mint leaves and a few green onion slices to avoid garnish drift.

## Remaining questions

1. Confirm whether standard roll scale is correct or if a smaller party-bite format is preferred.
2. Confirm whether optional red pepper flakes should be visible in the peanut-lime sauce or kept visually subtle.

## Artifact readiness

- `recipe-analysis.json`: ready with clarifying questions.
- `logical-scenes.json`: ready with 36 scenes.
- `seedance-segments.json`: ready with 8 Seedance 2 References segments.
- `reference-plan.json`: ready; uses existing assets and no generated food-state references at this stage.
- `suno-prompt.json` and `suno-prompt.md`: ready for manual Suno workflow.
