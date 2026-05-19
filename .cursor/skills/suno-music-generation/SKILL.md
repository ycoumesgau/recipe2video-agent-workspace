---
name: suno-music-generation
description: Produce Suno prompts as JSON + markdown for Recipe2Video — agent baseline lyrics/style plus operator 2–3 min Suno edits; short vertical excerpt plan; strict app contract.
---

# Suno music generation (Recipe2Video)

## When to use

- The user asks for music, a song, a soundtrack, or a Suno prompt for a recipe video.
- You need to create or update **`suno-prompt.json`** and **`suno-prompt.md`** under `agent-recipes/<videoId>/`.
- You are turning a creative plan (storyboard, Seedance segments, recipe analysis) into a Suno **Custom Mode** brief operators can paste.
- Target a **2–3 minute** full song (operator-tuned in Suno) and a **45–90 s** excerpt for TikTok / Shorts / Reels.

## Agent vs operator (critical)

| Deliverable | Agent ships | Operator adds in Suno before full generation |
| --- | --- | --- |
| **Auto Lyrics Prompt** | Baseline: `Write original English song lyrics…`, chorus reusable for 45–90 s only, header `Structure:` | Three edits → 2–3 min opener, `, but make a 2-3 minutes song`, header `Extend this structure to fit a 2-3 minutes song:` |
| **Style of Music** | Genre / production / mix only | Append `2-3 minutes song.` at the end |
| **Short Version** | Edit plan for the vertical cut | Used after the long master exists |

Full rules and worked example: **`contracts/suno-music.md`**.

## Required outputs (Recipe2Video contract)

The app validates `suno-prompt.json` (Zod) and renders assembly from `sunoPromptV2` **or** parsed markdown. Always ship **both**:

1. **`suno-prompt.json`** — strict JSON, no Markdown fences. **`schemaVersion: 1` required.**
2. **`suno-prompt.md`** — readable mirror; follow `references/suno-music-prompt-template.md` (level-2 `##` headings for the five Suno fields, **in order: Title → Style → Excludes → Auto lyrics → Short version**, plus **Operator full song (manual)**).

### JSON shape (`suno-prompt.json`)

Strings in `fields` must match the **agent baseline** (what operators start from before Suno edits):

```json
{
  "schemaVersion": 1,
  "status": {
    "recipeName": "string",
    "goal": "Full song 2–3 min for streaming; 45–90s excerpt for vertical edit",
    "model": "Suno 5.5 Advanced / Custom Mode",
    "targetDuration": "2–3 minutes (full, operator-tuned); excerpt for short video"
  },
  "fields": {
    "title": "…",
    "styleOfMusic": "… — no 2-3 minutes suffix",
    "excludeStyles": "…",
    "autoLyricsPrompt": "… — baseline only, under 3000 characters",
    "shortVersionPlan": "…"
  },
  "instructions": {
    "voice": "optional — voice / Suno persona notes",
    "structure": "optional — hook / excerpt reminders",
    "workflowNotes": "optional — operator notes",
    "fullSongOperatorEdits": {
      "styleOfMusicSuffix": "2-3 minutes song.",
      "autoLyricsPrompt": [
        "Opening line: Write original English song lyrics → Write original 2-3 minutes English song lyrics",
        "Lyric style: …45-90 second video edit. → …45-90 second video edit, but make a 2-3 minutes song.",
        "Structure: → Extend this structure to fit a 2-3 minutes song:"
      ]
    }
  },
  "qualityChecks": ["…"]
}
```

- `fields.title` ↔ **Title** (track name in Suno — first, same order as the UI).
- `fields.styleOfMusic` ↔ **Style of Music** body (baseline only — operator appends `2-3 minutes song.` in Suno).
- `fields.excludeStyles` ↔ **Exclude Styles**.
- `fields.autoLyricsPrompt` ↔ **Auto Lyrics Prompt** (agent baseline; operator applies three edits before full generation).
- `fields.shortVersionPlan` ↔ **Short Version To Extract Later** (edit plan / excerpt).
- `instructions.fullSongOperatorEdits` ↔ **Operator full song (manual)** in markdown (not parsed as a Suno paste field).

## Sources to read (in order)

1. `contracts/suno-music.md`
2. `recipe-analysis.json`
3. `logical-scenes.json`
4. `seedance-segments.json`
5. `decisions.md` if you need product context
6. Existing `suno-prompt.md` and `suno-prompt.json` before editing

## Workflow

1. Identify culinary arcs, the visual hook, money shots, and the final hero (from scenes / segments).
2. Extract singable image-words: signature ingredients, textures, colors, sensory gestures.
3. Draft with `references/suno-music-prompt-template.md`: **Status**, **Intent**, **Session notes**, five Suno fields, **Operator full song (manual)**.
4. Fill `suno-prompt.json` with baseline text in `fields` and `instructions.fullSongOperatorEdits` matching the contract.
5. **Do not** write finished lyrics in the deliverable unless the user explicitly asks — only the **prompt** that tells Suno to generate lyrics.
6. **Do not** put `2-3 minutes` in `autoLyricsPrompt` or `styleOfMusic` — that is the operator’s Suno paste step.

## Suno rules (aligned with the historical `videos` repo)

- By default, copy-ready prompts in **English**; ask for lyrics in **English**.
- Do not mix musical style and lyrics: **`Auto Lyrics Prompt`** must not include genre, production, instruments, mix, or in-text vocal direction.
- Musical style belongs only in **Style of Music** (`fields.styleOfMusic`), without the `2-3 minutes song.` suffix in agent artifacts.
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

If the user gives no style direction, start from this block (adapt to the recipe). Do **not** append `2-3 minutes song.` in the agent file:

```text
K-pop electronic pop with crisp four-on-the-floor kicks, rubbery synth bass, and playful staccato percussion; verse keeps it nimble with clipped phrasing and little vocal chops, pre-chorus opens into stacked harmonies and a rising synth sweep, chorus hits bright and glossy with gang vocals and a candy-sweet hook. Add sparkle FX, reversed bell swells, and a tiny glitch fill before each drop. Clean, punchy mix with wide neon sheen and close-mic lead vocals., k-pop, pop, electronic
```

## Pre-delivery checklist

- **Title** is the first Suno field in the `.md` and the logical first key in `fields` JSON.
- **Style of Music** stays separate from **Auto Lyrics Prompt**; agent baseline has **no** `2-3 minutes song.` suffix.
- **Auto Lyrics Prompt**: English, no music-direction leakage, under 3000 characters, **baseline** opener (`Write original English song lyrics`), **no** `but make a 2-3 minutes song`, header **`Structure:`**.
- **Operator full song** section and `instructions.fullSongOperatorEdits` list the three lyrics edits and style suffix.
- **Exclude Styles**: clear guardrails (unwanted genres, real artists, brands, bad lyric modes, recipe-tutorial wording).
- **Short Version**: 45–90 s cut plan from the generated long master; chorus lands on hero shots.
- `suno-prompt.json` is valid JSON and matches Recipe2Video’s schema.
- Update `changelog.md` with why the Suno artifacts changed.

## Reference

- `contracts/suno-music.md` — authoritative agent vs operator contract.
- `references/suno-music-prompt-template.md` — creative source (videos-repo quality); keep JSON in sync after every edit.
