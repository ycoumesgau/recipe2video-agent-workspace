# Decisions - Spicy Strawberry Salsa with Whipped Feta

## Source and completeness

- Source URL was readable and contained the full recipe: ingredients, prep steps, timing, servings, and serving suggestions.
- No clarifying questions are required for this ingest; `recipe-analysis.json` includes an empty `clarifyingQuestions` array.

## Creative direction

- The creator asked for the recipe to feel "really sexy and food porn." This is interpreted as sensual macro food texture: glossy strawberries, lime droplets, chili dust, honey ribbons, thick whipped feta swirls, crunchy bread scrape, and messy loaded bites.
- The character is never sexualized. Luma supports the cooking action and appears satisfied in the final kitchen context while the food remains the hero.
- The opening is texture-first: a toasted baguette scoop through the finished red-white dip. Scene 2 immediately clarifies the bite contents.

## Reference strategy

- The creator-provided image is planned as `DesiredFinalDishVisual` and used only as a final plating/styling reference for Seedance References mode.
- No intermediate recipe-specific generated references are planned. The recipe has simple readable states, and the creator explicitly asked to avoid intermediate reference images unless indispensable.
- Existing kitchen, character, pose, spoon, and blender references are used wherever they materially reduce drift.
- Each Seedance segment includes `@KitchenLayoutContextWide` plus a shot-specific kitchen view.

## Scale and continuity locks

- Strawberry salsa remains chunky: diced pieces are locked at about 0.8-1.2 cm, not puree.
- The salsa mound covers roughly one third of the whipped feta surface: generous, centered, not a tiny garnish, not full-bowl coverage.
- Whipped feta is thick, smooth, satiny, and spreadable, with soft peaks and spoon ridges that hold.
- Bread slices are palm-width, about 7-10 cm long, and must visibly scrape through and carry both feta and salsa.

## Artifact readiness

- `recipe-analysis.json`, `logical-scenes.json`, `seedance-segments.json`, `reference-plan.json`, `suno-prompt.json`, `suno-prompt.md`, `decisions.md`, and `changelog.md` are ready for Recipe2Video validation.
- Follow-up request on 2026-05-18 confirmed the artifacts already exist and are still ready; no creative artifact rewrite was needed.
- `checkpoint-manifest.json` was realigned to the latest already-pushed checkpoint SHA available at the start of the follow-up: `ad2d843a2f1fd9632100110f8472e2ae7048e4dd`.

## 2026-05-18 strict format refresh

- Pulled `origin/main` into the working branch and reapplied the current asset/Seedance/Suno skills.
- Removed non-contract metadata from `recipe-analysis.json` to avoid strict Zod rejection. The removed metadata remains preserved here as decisions: desired final visual URL `https://cdn.sanity.io/images/fl949yr7/production/ff687323573ae76187cc7d4e48e699d980e490e1-1024x1365.png?q=85&fit=clip&auto=format`, style preset `asmr_food`, and production defaults `seedance2`, `gpt_image_2`, `eleven_multilingual_v2`, `eleven_text_to_sound_v2`.
- Removed the non-contract `kitchenContinuityPairPresent` key from each segment `qaChecklist`; the actual kitchen continuity pair remains present in every segment reference list and is validated separately.
