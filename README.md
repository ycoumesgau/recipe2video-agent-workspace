Copyright (c) 2026 Yoann Coumes-Gauchet

This repository is publicly visible for evaluation purposes only. No permission is granted to use, copy, modify, distribute, or commercialize this code. All rights reserved.

# Recipe2Video Agent Workspace

This repository is the focused Cursor workspace for Recipe2Video creative planning.

Recipe2Video itself remains the production app: authentication, Supabase state,
Runway generation, Mux playback, Remotion assembly, costs, and UI live there.
This workspace exists so one persistent Cursor agent per recipe can reason in a
small, high-signal environment and maintain planning artifacts.

## Agent Scope

The agent works inside:

```txt
agent-recipes/{videoId}/
```

Required artifacts:

```txt
recipe-analysis.json
decisions.md
logical-scenes.json
seedance-segments.json
reference-plan.json
suno-prompt.md
changelog.md
```

Daily generated recipe artifacts are ignored by Git. Recipe2Video retrieves them
through the Cursor SDK, validates them, and syncs valid content into Supabase.

## What Belongs Here

- Cursor rules, skills, and agents for recipe-to-video planning.
- Canonical assets used as Seedance references.
- Curated examples and production patterns.
- Artifact contracts shared with the app.

## What Does Not Belong Here

- App source code.
- Supabase, Mux, Remotion, Vercel, or Runway credentials.
- Runway task execution.
- Daily recipe artifacts committed as production history.
- The old text-to-image then image-to-video pipeline as a production path.

## Current Production Path

1. Understand the recipe and cooking physics.
2. Produce 30-48 logical scenes for editorial quality.
3. Compress scenes into 5-10 Seedance 2 segments.
4. Plan global and recipe-specific references for Seedance.
5. Generate copy-ready Seedance prompts with explicit reference roles.
6. Generate a copy-ready Suno prompt (agent baseline + operator 2–3 min edits documented in `contracts/suno-music.md`).
7. Let Recipe2Video validate, persist, approve, and execute.

Image generation remains useful only for creating **reference images** needed by
Seedance, such as raw, baked, filled, cut, glazed, broken, or final food states.
