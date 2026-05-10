---
name: suno-music-generation
description: Build copy-ready Suno prompts for recipe video music, separate from Runway generation.
---

# Suno Music Generation

Use when creating or revising `suno-prompt.md`.

## Sources

Read available artifacts in this order:

1. `recipe-analysis.json`
2. `logical-scenes.json`
3. `seedance-segments.json`
4. existing `suno-prompt.md`

## Workflow

1. Identify culinary arcs, hook, money shots, and final hero shot.
2. Extract image-driven words: materials, textures, colors, gestures, emotions.
3. Produce separate Suno fields:
   - `Style of Music`
   - `Exclude Styles`
   - `Title`
   - `Auto Lyrics Prompt`
   - `Short Version To Extract Later`
4. Keep `Auto Lyrics Prompt` under 3000 characters.
5. Do not write complete lyrics unless explicitly requested.

## Rules

- Default prompt language: English.
- Do not include music instructions inside `Auto Lyrics Prompt`.
- Do not imitate real artists, protected voices, brands, or copyrighted character voices.
- Avoid tutorial lyrics: no quantities, numbered steps, or recipe instructions.
- Ask for short singable lines, reusable hook, and section tags.
- Align chorus/payoff moments with strongest video textures.
- Suno is manual; no API integration is implied.

## Default Style

```text
K-pop electronic pop with crisp four-on-the-floor kicks, rubbery synth bass, and playful staccato percussion; verse keeps it nimble with clipped phrasing and little vocal chops, pre-chorus opens into stacked harmonies and a rising synth sweep, chorus hits bright and glossy with gang vocals and a candy-sweet hook. Add sparkle FX, reversed bell swells, and a tiny glitch fill before each drop. Clean, punchy mix with wide neon sheen and close-mic lead vocals., k-pop, pop, electronic
```
