---
name: asset-reference-system
description: Select and name real character, kitchen, pose, expression, and utensil references from `assets/`.
---

# Asset Reference System

Use whenever a scene, segment, or reference plan mentions kitchen, character, pose, expression, or utensils.

## Rules

- Use only real files from `assets/`.
- Do not invent canonical reference names.
- A canonical asset name is the file name without extension.
- Global references cover kitchen, character, poses, expressions, and common utensils.
- Recipe-specific references cover food states Seedance may misread.
- Do not re-describe the Licorn character from scratch. Refer to character references and specify only pose, expression, action, and visible hands.
- For every reference in a Seedance prompt, state exactly what role it plays.

## Common Global References

Kitchen:

- `@KitchenIslandDefault` from `assets/kitchen/island_default.png`
- `@KitchenIslandOverhead` from `assets/kitchen/island_overhead.png`
- `@KitchenIslandWide` from `assets/kitchen/island_overview_wide.png`
- `@InductionCloseup` from `assets/kitchen/induction_left_closeup.png`
- `@InductionWide` from `assets/kitchen/induction_wide.png`
- `@OvenWide` from `assets/kitchen/oven_opened_wide.png`
- `@OvenCloseup` from `assets/kitchen/oven_opened_closeup.png`

Character:

- `@CharacterSheet`
- `@CharacterExpressions`
- `@PoseFront`
- `@PoseTopDown`
- `@PoseThreeQuarterLeft`
- `@PoseThreeQuarterRight`

Utensils:

- `@BakingMat`
- `@RollingPin`
- `@Blender`
- `@StandMixer`
- `@SaucepanLarge`
- `@Whisk`
- `@ImmersionBlender`
- `@Spatula`
- `@Spoon`
- `@Sieve`

If an object does not exist as an asset, describe it in the prompt but do not list it as a reference.
