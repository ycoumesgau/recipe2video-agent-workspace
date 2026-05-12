---
name: suno-music-generation
description: Produce Suno prompts as JSON + markdown for Recipe2Video — full-length streaming track plus short vertical excerpt; creative quality from the historical videos repo; strict application contract.
---

# Suno music generation (Recipe2Video)

## When to use

- The user asks for music, a song, a soundtrack, or a Suno prompt for a recipe video.
- You need to create or update **`suno-prompt.json`** and **`suno-prompt.md`** under `agent-recipes/<videoId>/`.
- You are turning a creative plan (storyboard, Seedance segments, recipe analysis) into a Suno **Custom Mode** brief operators can paste.
- Target a long-form version for distribution (e.g. Spotify) and a short lift for TikTok / Shorts / Reels.

## Required outputs (Recipe2Video contract)

The app validates `suno-prompt.json` (Zod) and renders assembly from `sunoPromptV2` **or** parsed markdown. Always ship **both**:

1. **`suno-prompt.json`** — strict JSON, no Markdown fences. **`schemaVersion: 1` required.**
2. **`suno-prompt.md`** — readable mirror; follow `references/suno-music-prompt-template.md` (level-2 `##` headings for the five Suno fields, **in order: Title → Style → Excludes → Auto lyrics → Short version**).

### JSON shape (`suno-prompt.json`)

Strings in `fields` must match what you paste into Suno after replacing placeholders in the template:

```json
{
  "schemaVersion": 1,
  "status": {
    "recipeName": "string",
    "goal": "Full song 2–3 min for streaming; 45–90s excerpt for vertical edit",
    "model": "Suno 5.5 Advanced / Custom Mode",
    "targetDuration": "2–3 minutes (full); excerpt for short video"
  },
  "fields": {
    "title": "…",
    "styleOfMusic": "…",
    "excludeStyles": "…",
    "autoLyricsPrompt": "…",
    "shortVersionPlan": "…"
  },
  "instructions": {
    "voice": "optional — voice / Suno persona notes",
    "structure": "optional — length / hook reminders",
    "workflowNotes": "optional — operator notes"
  },
  "qualityChecks": ["…"]
}
```

- `fields.title` ↔ **Title** (track name in Suno — first, same order as the UI).
- `fields.styleOfMusic` ↔ **Style of Music** body (only the ```text fence contents — no lyric instructions).
- `fields.excludeStyles` ↔ **Exclude Styles**.
- `fields.autoLyricsPrompt` ↔ **Auto Lyrics Prompt** (paste into Suno’s auto-lyrics field; keep under **3000 characters**).
- `fields.shortVersionPlan` ↔ **Short Version To Extract Later** (edit plan / excerpt).

## Sources to read (in order)

1. `recipe-analysis.json`
2. `logical-scenes.json`
3. `seedance-segments.json`
4. `decisions.md` if you need product context
5. Existing `suno-prompt.md` and `suno-prompt.json` before editing

## Workflow

1. Identify culinary arcs, the visual hook, money shots, and the final hero (from scenes / segments).
2. Extract singable image-words: signature ingredients, textures, colors, sensory gestures.
3. Draft with `references/suno-music-prompt-template.md`: **Status**, **Intent**, **Session notes**, then the five Suno fields in order **Title → Style → Excludes → Auto lyrics → Short version**.
4. Fill `suno-prompt.json` with the same final text in `fields` plus consistent `status` / `instructions` / `qualityChecks`.
5. **Do not** write finished lyrics in the deliverable unless the user explicitly asks — only the **prompt** that tells Suno to generate lyrics.

## Suno rules (aligned with the historical `videos` repo)

- By default, copy-ready prompts in **English**; ask for lyrics in **English**.
- Do not mix musical style and lyrics: **`Auto Lyrics Prompt`** must not include genre, production, instruments, mix, or in-text vocal direction.
- Musical style belongs only in **Style of Music** (`fields.styleOfMusic`).
- The lyrics prompt must ask for **original** generated lyrics, not hand-written full lyrics.
- Ask for short, singable, repeatable lines with a hook that survives a short cut; use **section tags** (`[Verse 1]`, etc.) as in the template.
- Keep **`autoLyricsPrompt`** under **3000 characters** with headroom.
- For vocal identity, steer toward **Voices** / Suno persona when available (see Session notes in the template).
- Never ask to imitate a real artist, protected voice, brand, or artist-named style.
- Avoid tutorial lyrics: no quantities, numbered steps, or recipe-instruction wording.
- Turn the recipe into sung imagery: matter, color, texture, emotion, simple gesture.
- Stay consistent with the video: same recipe, same sensory payoffs, same satisfying ending.
- Suno execution stays **manual** for the user — do not call a Suno API from the agent.

## Default musical style

If the user gives no style direction, start from this block (adapt to the recipe):

```text
K-pop electronic pop with crisp four-on-the-floor kicks, rubbery synth bass, and playful staccato percussion; verse keeps it nimble with clipped phrasing and little vocal chops, pre-chorus opens into stacked harmonies and a rising synth sweep, chorus hits bright and glossy with gang vocals and a candy-sweet hook. Add sparkle FX, reversed bell swells, and a tiny glitch fill before each drop. Clean, punchy mix with wide neon sheen and close-mic lead vocals., k-pop, pop, electronic
```

## Pre-delivery checklist

- **Title** is the first Suno field in the `.md` and the logical first key in `fields` JSON.
- **Style of Music** stays separate from **Auto Lyrics Prompt** in both `.md` and `fields`.
- **Auto Lyrics Prompt**: English, no music-direction leakage, under 3000 characters.
- **Exclude Styles**: clear guardrails (unwanted genres, real artists, brands, bad lyric modes, recipe-tutorial wording).
- Song designed for **2–3 minutes** in long form; chorus / hook **reusable** for a **45–90 s** video cut (see Short Version).
- Key template sections are filled (Intent, imagery, lyric scaffolding).
- `suno-prompt.json` is valid JSON and matches Recipe2Video’s schema.
- Update `changelog.md` with why the Suno artifacts changed.

## Reference

`references/suno-music-prompt-template.md` is the **creative source** (videos-repo quality); JSON is the **structured source** for the app. Keep them in sync after every edit.
