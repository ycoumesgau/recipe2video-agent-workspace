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
- The Licorn mascot is a **flat 2D illustrated character** (library PNG poses + sheet), not a 3D model. References are always 2D stills; Seedance must not reinterpret the mascot as CGI, clay, or realistic 3D.
- Do not re-describe the Licorn character from scratch. Refer to character references and specify only pose, expression, action, and visible hands.
- When the character is visible in a segment, add a character style lock and 2D negatives (see `reference-detail/character-2d-guardrails.md`).
- For every reference in a Seedance prompt, state exactly what role it plays.
- For every segment, include a kitchen continuity pair:
  - one structural context reference (`@KitchenLayoutContextWide`);
  - one shot-specific kitchen view (`@KitchenIslandDefault` OR overhead/induction/oven view).
- `@KitchenLayoutContextWide` is a structural context anchor, not a framing instruction. Do NOT force a wide shot unless the storyboard asks for it.
- Do not force `@KitchenIslandDefault` when another kitchen angle is the active shot. Use it when it is the shot view or when explicit terrazzo lock is needed.
- Keep kitchen invariants stable across segments: light terrazzo countertop, black flush induction plate, same cabinet style/layout.
- If the required utensil exists in assets, attach it. Do not use a near-miss utensil (`@SiliconeSpatula` instead of `@SpiderSkimmer`, etc.).
- For hot transfers, avoid cloth-in-hand interactions (high fusion risk with fingers). Prefer utensil handling; if not possible, stage the action after implied cooling.
- For plating sides (salad, garnish, sauces), quantify amounts (`small bed`, `2-3 leaves`, `one spoonful`) to avoid tiny-token results.
- Keep prop continuity: if a bowl/side component is introduced and still relevant, either show it again later or explicitly state it has been set aside.

## Common Global References

Kitchen:

- `@KitchenLayoutContextWide` from `assets/kitchen/kitchen_wide.png` (always-on structural kitchen context, not a mandatory wide camera framing)
- `@KitchenIslandDefault` from `assets/kitchen/island_default.png`
- `@KitchenIslandOverhead` from `assets/kitchen/island_overhead.png`
- `@KitchenIslandWide` from `assets/kitchen/island_overview_wide.png`
- `@InductionCloseup` from `assets/kitchen/induction_left_closeup.png`
- `@InductionWide` from `assets/kitchen/induction_wide.png`
- `@OvenWide` from `assets/kitchen/oven_opened_wide.png`
- `@OvenCloseup` from `assets/kitchen/oven_opened_closeup.png`

Character (all **2D** library stills / motion ref — never treat as a 3D rig):

- `@CharacterSheet` — 2D illustrated identity lock (`assets/character/Character-sheet.png`)
- `@CharacterExpressions` — 2D expression sheet
- `@PoseFront`, `@PoseTopDown`, `@PoseThreeQuarterLeft`, `@PoseThreeQuarterRight` — pre-drawn **2D views** (illustration angles, not 3D camera orbit)
- `@LicornOutroVideo` (kind: video) from `assets/character/outro/LicornOutroVideo.mp4`. Canonical 3s **2D** celebration motion reference. Pass it as a Seedance video reference (`referenceVideos[]`), not an image. Use it ONLY on the last segment (`arc: licorn_celebration_outro`) alongside `@CharacterSheet` for 2D identity lock.

Utensils:

- `@BakingMat`
- `@RollingPin`
- `@Blender`
- `@StandMixer`
- `@SaucepanLarge`
- `@Whisk`
- `@ImmersionBlender`
- `@SiliconeSpatula` (flexible bowl / maryse — folding, scraping bowls and mixer bowls; not for serving lasagna-style portions)
- `@TurningSpatula` (rigid turner — slide under gratin, lasagna, sheet cake, fish; lift a supported portion)
- `@OffsetSpatula` (pastry offset — under tarts, cookies, entremets; fragile layers, sometimes two spatulas)
- `@SpiderSkimmer`
- `@Tongs`
- `@Spoon`
- `@Sieve`

If an object does not exist as an asset, describe it in the prompt but do not list it as a reference.

## Conditioning Recipe-Specific Reference Images

Recipe-specific reference entries (`source: "generated_reference_needed"` in `reference-plan.json`) are produced by GPT-Image 2 inside the Recipe2Video app. Without anchors the model invents the kitchen and pan from scratch and breaks continuity with the Seedance segments that consume the anchor.

For every recipe-specific entry, declare a `conditioningReferences` array of library canonical names (the same `@Tag` form used in Seedance prompts). The app forwards each name to GPT-Image 2 as a `referenceImages[]` entry so the model grounds the dish on real Licorn-kitchen pixels.

Minimum coverage:

- one kitchen view (`KitchenIslandDefault` or the relevant `KitchenIslandOverhead`/`InductionWide`/`OvenWide`/`OvenCloseup` variant);
- the cookware that holds the dish (`baking_dish`, `SaucepanLarge`, …);
- the dominant utensil when it appears in the anchor (`TurningSpatula`, `Spoon`, …).

**Do NOT include character anchors** in `conditioningReferences`:

- `@CharacterSheet`
- `@CharacterExpressions`
- `@PoseFront`, `@PoseTopDown`, `@PoseThreeQuarterLeft`, `@PoseThreeQuarterRight`

The app drops them at generation time. The mascot adds noise to dish frames and the kitchen anchor already carries the Licorn visual identity for recipe-state images. Including them only wastes a planning slot.

Do NOT include the recipe-specific entry's own `canonicalName` in its `conditioningReferences`. Library names only.

Example:

```json
{
  "type": "recipe_state",
  "canonicalName": "FinishedDumplingLasagnaCutaway",
  "role": "finished compact dumpling-lasagna top and cutaway geometry",
  "priority": 1,
  "source": "generated_reference_needed",
  "prompt": "Generate one vertical-reference still of a compact 8 in / 20 cm square steamed dumpling lasagna...",
  "runwayUri": null,
  "mediaAssetId": null,
  "usedInSegmentIds": ["segment-01", "segment-07", "segment-08"],
  "status": "planned",
  "conditioningReferences": ["KitchenIslandDefault", "baking_dish", "TurningSpatula"]
}
```

## References

- `reference-detail/character-2d-guardrails.md`
- `reference-detail/kitchen-continuity-guardrails.md`
- `reference-detail/utensil-task-mapping.md`
