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

## Prompt Skeleton

```text
Use @... for [role]. Use @... only as [role]. [Reference priority if needed].

Generate exactly N short shots with hard cuts, total duration X seconds, no slow motion, no soft transitions, no extra shots. TikTok/Reels food ASMR style, no text on screen.

Integrated audio: no speech, no voiceover, no music. Only close-up kitchen ASMR sounds synchronized with the cuts and food actions.

Mandatory timing:
- 0.0-...s: ...

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

## Validation

Before marking a segment ready:

- references <= 9;
- global kitchen reference present;
- roles explicit;
- timing explicit;
- hard cuts present;
- ASMR audio only;
- no speech, no voiceover, no music;
- fragile geometry handled with state references or strong negatives;
- visible hands for human actions.
