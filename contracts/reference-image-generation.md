# Reference Image Generation Policy

Reference image generation is allowed and important, but only for Seedance reference planning.

## Allowed Uses

Generate or request images for states Seedance is likely to misread:

- raw state;
- baked state;
- filled state;
- cut state;
- glazed state;
- broken or brittle state;
- final hero state;
- non-standard topology.

Examples:

- `RawChouxCrownFrame`
- `BakedChouxCrownFrame`
- `FilledCrownFrame`
- `FinishedParisBrestFrame`

## Not Allowed

Do not revive the old production path where every micro-scene first gets an image and then image-to-video.

Do not create first/last frames for Kling-style interpolation.

Do not create image prompts for every logical scene unless the image is explicitly needed as a reusable Seedance reference.

## Required Metadata

Every generated reference plan entry should specify:

- `canonicalName`
- `type`
- `role`
- `priority`
- `source: "generated_reference_needed"`
- `prompt`
- `usedInSegmentIds`
- `status: "planned"`
- `conditioningReferences` (see below)

The Recipe2Video app will create, store, approve, and upload these references before video generation.

## Conditioning Anchors

Recipe-specific reference images are produced by GPT-Image 2 inside the Recipe2Video app. Without anchors the model invents the kitchen and pan from scratch and breaks continuity with the Seedance segments that consume the reference.

`conditioningReferences` is an ordered list of `@Tag` library canonical names (kitchen, cookware, utensils only) that the app forwards to GPT-Image 2 as `referenceImages[]`. The names are the same ones used in Seedance prompts; the app derives the Runway tag (≤ 16 alphanumeric chars) and the signed URL automatically. Up to 16 anchors are accepted; 2-4 well-chosen ones are typically enough.

### Allowed categories

- `kitchen` (e.g. `KitchenIslandDefault`, `KitchenIslandOverhead`, `InductionWide`, `OvenWide`)
- `utensil` (e.g. `baking_dish`, `SaucepanLarge`, `TurningSpatula`, `Whisk`)

### Forbidden categories

Never declare character-class anchors in `conditioningReferences`:

- `character` (`@CharacterSheet`) — 2D illustrated identity still, not a 3D model
- `character_pose` (`@PoseFront`, `@PoseTopDown`, `@PoseThreeQuarterLeft`, `@PoseThreeQuarterRight`) — pre-drawn **2D views**, not a 3D rig
- `character_expression` (`@CharacterExpressions`)

Recipe2Video drops them at generation time anyway — the mascot adds noise to dish frames and the kitchen anchor alone carries the Licorn visual identity for recipe-state images. Listing them only wastes a planning slot. Dish-state prompts must not describe a 3D mascot in frame.

### Minimum coverage

For a `recipe_state` anchor, include at least:

- the active kitchen view used by the segments that consume it;
- the cookware that holds the dish;
- the dominant utensil when it appears in the anchor.

### `FinalDishVisual` exception (outro + image gen)

`FinalDishVisual` uses the same `prompt` field for GPT-Image 2 **and** for the dish clause embedded in the standardized Licorn outro at sync. **Start** the prompt with one short dish-only sentence (≤ 280 characters, no "Generate one vertical-reference still…" lead-in) that names the finished dish on the counter. You may append GPT-Image detail after that sentence for reference generation. Full rules: `.cursor/rules/seedance-outro.mdc`.

### Self-reference prohibition

Never list the recipe-specific entry's own `canonicalName` inside its `conditioningReferences`. The app resolves names against the global library only.

### Worked example

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
