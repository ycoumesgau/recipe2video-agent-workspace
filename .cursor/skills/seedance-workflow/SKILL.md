---
name: seedance-workflow
description: Build Seedance 2 References segments and prompts for short vertical food videos.
---

# Seedance Workflow

Use when converting logical scenes into generated video segments.

## Principles

- Default model: `seedance2`.
- Default output: `1080:1920`, 9:16 vertical 1080p.
- Default cost estimate in Recipe2Video: 40 credits per second.
- Default mode: References.
- Do not use the old first-frame/last-frame production pipeline.
- Up to 9 image inputs per segment.
- Prompt language: English.
- Keep prompts under about 3,500 characters.
- Use 5-10 Seedance segments for a 30-48 logical-scene storyboard.
- Store logical scene IDs on every segment.
- Lock object scale for ambiguous shapes (diameter/thickness/count + relative kitchen anchor).
- Preserve scale continuity across adjacent segments when the same food state continues.
- Preserve kitchen identity continuity across adjacent segments (countertop material, induction geometry, cabinet layout).

## Segment Fields

Each `seedance-segments.json` segment should include:

- `id`
- `position`
- `title`
- `arc`
- `mode: "References"`
- `logicalSceneIds`
- `description`
- `prompt`
- `promptInitial`
- `references`
- `beats`
- `timing`
- `continuity`
- `risk`
- `audioPrompt`
- `negatives`
- `qaChecklist`
- `durationTarget`
- `status`

Use `continuity` and `risk` to track proportion locks, for example:

- continuity: `Arancini diameter remains 3-4 cm as in segment-02.`
- risk: `Scale drift risk if ball size is not restated.`
- continuity: `Countertop remains the same light terrazzo surface; induction remains the same flush black plate from prior segment.`
- risk: `Model may invent wood countertop if kitchen anchors are incomplete.`

## Prompt Skeleton

```text
Use @... for [role]. Use @... only as [role]. [Reference priority if needed].

Kitchen continuity lock:
- Use `@KitchenLayoutContextWide` as structural kitchen context (not as camera framing requirement).
- Add one shot-specific kitchen view (`@KitchenIslandDefault` or another relevant kitchen angle).
- Keep induction design consistent with kitchen references (no invented stovetop geometry).

Generate exactly N short shots with hard cuts, total duration X seconds, no slow motion, no soft transitions, no extra shots. TikTok/Reels food ASMR style, no text on screen.

Integrated audio: no speech, no voiceover, no music. Only close-up kitchen ASMR sounds synchronized with the cuts and food actions.

Mandatory timing:
- 0.0-...s: ...

Scale lock:
- object size: ...
- relative anchor: ...
- negative size constraint: ...

Utensil lock:
- required utensil: ...
- avoid near-miss substitutions: ...
- hot handling policy: tool-first, no cloth fused with hand.

Plating quantity lock:
- side amount: ...
- visual target: ...
- continuity note if side bowl appears earlier: ...

Global negatives: ...

Mandatory audio: ...
```

## Reference Planning

References are not optional notes. They are Seedance generation inputs.

Always create or update `reference-plan.json` alongside `seedance-segments.json`.

Keep references separated into:

- global references: kitchen, character, expressions, poses, utensils;
- recipe-specific references: raw, baked, filled, cut, glazed, broken, final states.

## Reference Image Generation

Image generation is allowed only to produce Seedance state references.

Use it when the model is likely to misread:

- non-standard dish geometry;
- baked/final state;
- filled state;
- cut state;
- brittle or broken state;
- repeated topology such as domes, rosettes, braids, layers.

Do not use generated images as the old production path for every micro-scene.

Generation is performed by GPT-Image 2 inside the Recipe2Video app. Every recipe-specific entry in `reference-plan.json` (`source: "generated_reference_needed"`) MUST declare a `conditioningReferences` array — the library `@Tag` names the app forwards to GPT-Image 2 as `referenceImages[]`. Without anchors the model invents the kitchen and pan from scratch and breaks continuity with the Seedance segments that consume the anchor.

Minimum coverage:

- one kitchen view (`KitchenIslandDefault` or the appropriate overhead/induction/oven variant);
- the cookware that holds the dish (`baking_dish`, `SaucepanLarge`, …);
- the dominant utensil when it appears in the anchor.

NEVER include character-class anchors (`@CharacterSheet`, character poses, `@CharacterExpressions`) in `conditioningReferences`. The app filters them out; they only waste a planning slot. The kitchen anchor alone carries the Licorn visual identity for recipe-state images.

See `contracts/reference-image-generation.md` for the full policy and `.cursor/skills/asset-reference-system/SKILL.md` for a worked example.

## Validation

Before marking a segment ready:

- references <= 9;
- global kitchen reference present;
- kitchen continuity pair present (`@KitchenLayoutContextWide` + one shot-specific kitchen view);
- roles explicit;
- timing explicit;
- hard cuts present;
- ASMR audio only;
- no speech, no voiceover, no music;
- fragile geometry handled with state references or strong negatives;
- visible hands for human actions;
- scale lock present for risky objects;
- utensil choice matches action physics (e.g. deep-fry lift uses spider skimmer);
- no cloth-in-hand hot transfer shots;
- plating side quantities are explicit when present;
- continuity mentions preserved proportions when reusing the same object across segments.
- every recipe-specific reference plan entry declares `conditioningReferences` covering kitchen + cookware (+ utensil when visible), with no character-class anchors.
