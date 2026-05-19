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

Character style lock (when @CharacterSheet / pose / expression references are used):
- flat 2D illustrated Licorn mascot matching references; not a 3D model or CGI render.

Global negatives: ...
- if character visible: no 3D character, no CGI mascot, no clay figurine, no realistic 3D render on the character.

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

## Outro segment

The last segment in `seedance-segments.json` is reserved for the
standardized Licorn celebration outro. Do NOT write a custom prompt for
it. Emit it with:

- `arc: "licorn_celebration_outro"`;
- `id: "segment-outro"` (or any stable id ending in `-outro`);
- `durationTarget: 5`;
- `logicalSceneIds`: at least one placeholder id such as `["scene-outro"]` (never `[]` — sync validation requires ≥1 id even though the outro is app-injected, not scene-compressed);
- `prompt: "<APP_OVERRIDE>"` and `promptInitial: "<APP_OVERRIDE>"`;
- exactly 5 references in this order: `KitchenLayoutContextWide`,
  `KitchenIslandDefault`, `LicornOutroVideo`, `CharacterSheet`,
  `FinalDishVisual` (recipe-specific, listed in `reference-plan.json`).

In `reference-plan.json`, `FinalDishVisual.prompt` must **begin** with a short dish-only sentence (≤ 280 chars) for the outro embed; longer GPT-Image detail may follow for reference generation.

The full contract lives in `.cursor/rules/seedance-outro.mdc`.

The segment immediately before the outro (position N-1) must end with
the dish intact and motionless. Any destructive food-porn beat (spoon
dive, slice, drip) must happen in segments 1..N-2.

The 5-10 segment count cap includes this fixed outro segment; plan
4-9 creative segments + 1 outro.

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
- when character references are attached: 2D style lock and anti-3D negatives present (see `asset-reference-system/reference-detail/character-2d-guardrails.md`).
