---
name: recipe-ingest
description: Analyze a recipe source and create `recipe-analysis.json` plus logical scene candidates.
---

# Recipe Ingest

Use when a recipe URL, text, photo description, or dish name starts a new project.

## Workflow

1. Identify source type and available information.
2. Reconstruct useful cooking structure: ingredients, sub-recipes, real dependencies, timings, and fragile transformations.
3. Convert recipe steps into visible food actions, not tutorial prose.
4. Detect missing or ambiguous information that materially changes the video.
5. Identify visually strong hooks and texture opportunities.
6. Write `recipe-analysis.json`.
7. If decisions were made, update `decisions.md` and `changelog.md`.

## Requirements

- Ask clarifying questions only when the answer changes storyboard, references, duration, geometry, or generation risk.
- Identify sub-recipes before selecting the opening.
- A moved opening block must remain culinarily coherent and must be re-anchored quickly.
- Never open on final-dish slicing or neutral ingredient lineup.
- Prefer desirable, generatable gestures: pouring, glazing, piping, spreading, dusting, sizzling, steaming, cracking, revealing, filling.

## Output

Write strict JSON matching `contracts/artifact-schemas.md`.
