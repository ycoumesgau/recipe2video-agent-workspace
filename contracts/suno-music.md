# Suno Music Contract (Recipe2Video Agent)

Suno generation stays **manual** in the Suno UI. The agent ships copy-ready fields in `suno-prompt.md` and `suno-prompt.json`. The operator pastes them into Suno Custom Mode and applies a small, fixed set of edits for the **full 2–3 minute** song before generating.

## Two layers

| Layer | Who | Purpose |
| --- | --- | --- |
| **Agent baseline** | Cursor agent | Lyrics prompt optimized for structure, hooks, and a **45–90 s** vertical excerpt plan. Does **not** ask Suno for 2–3 minutes in the lyrics opener. |
| **Operator full song** | Human in Suno | Same prompt, with **three lyrics edits** and **one style suffix** so Suno targets a **2–3 minute** master. The short video still uses the excerpt plan in **Short Version To Extract Later**. |

The agent must **not** bake the operator full-song edits into `fields.autoLyricsPrompt` or `fields.styleOfMusic` by default. Document the operator steps in `instructions.fullSongOperatorEdits` (JSON) and **Operator full song (manual)** (markdown).

## Parsed Suno fields (app)

Recipe2Video parses these level-2 sections from `suno-prompt.md` (and mirrors them in `suno-prompt.json` → `fields`):

1. `## Title`
2. `## Style of Music`
3. `## Exclude Styles`
4. `## Auto Lyrics Prompt`
5. `## Short Version To Extract Later`

Sections **Status**, **Intent**, **Session notes**, and **Operator full song (manual)** are operator context only (also mirrored under `status` / `instructions` in JSON).

Recommended paste order in Suno: **Title → Style → Excludes → Auto lyrics** (after operator edits) → generate → later edit to **45–90 s** using **Short Version To Extract Later**.

## `suno-prompt.json` (schemaVersion 1)

Strict JSON. Required top-level keys: `schemaVersion`, `status`, `fields`, `instructions`, `qualityChecks`.

```json
{
  "schemaVersion": 1,
  "status": {
    "recipeName": "string",
    "goal": "Full song 2–3 min for streaming; 45–90 s excerpt for vertical edit",
    "model": "Suno 5.5 Advanced / Custom Mode",
    "targetDuration": "2–3 minutes (full, operator-tuned); excerpt for short video"
  },
  "fields": {
    "title": "string",
    "styleOfMusic": "string — agent baseline; operator appends full-song suffix in Suno",
    "excludeStyles": "string",
    "autoLyricsPrompt": "string — agent baseline only; under 3000 characters",
    "shortVersionPlan": "string"
  },
  "instructions": {
    "voice": "optional",
    "structure": "optional",
    "workflowNotes": "optional",
    "fullSongOperatorEdits": {
      "styleOfMusicSuffix": "2-3 minutes song.",
      "autoLyricsPrompt": [
        "Opening line: change \"Write original English song lyrics\" to \"Write original 2-3 minutes English song lyrics\".",
        "Lyric style line: after \"Keep the chorus reusable for a 45-90 second video edit\", add \", but make a 2-3 minutes song\".",
        "Structure header: change \"Structure:\" to \"Extend this structure to fit a 2-3 minutes song:\""
      ]
    }
  },
  "qualityChecks": ["string"]
}
```

## Agent baseline — Auto Lyrics Prompt

The agent **opens** with:

```text
Write original English song lyrics about …
```

The agent **does not** include `2-3 minutes` in that opening line.

The **Lyric style** line ends with:

```text
…Keep the chorus reusable for a 45-90 second video edit.
```

(without `, but make a 2-3 minutes song`.)

The scaffold header is:

```text
Structure:
```

(not `Extend this structure…`.)

Everything else in the lyrics prompt (mood, imagery, must-include words, section scaffolding) stays the same between baseline and full song.

## Operator full song — lyrics (three edits)

Apply in Suno’s **Auto Lyrics Prompt** field **before** generating the long master:

1. **Opening duration** — replace  
   `Write original English song lyrics about`  
   with  
   `Write original 2-3 minutes English song lyrics about`

2. **Lyric style duration** — replace  
   `Keep the chorus reusable for a 45-90 second video edit.`  
   with  
   `Keep the chorus reusable for a 45-90 second video edit, but make a 2-3 minutes song.`

3. **Structure header** — replace  
   `Structure:`  
   with  
   `Extend this structure to fit a 2-3 minutes song:`

No other mandatory edits. Suno may add extra sections or repeats to reach 2–3 minutes; the scaffold sections stay as written.

### Worked example (orecchiette)

**Agent baseline (excerpt):**

```text
Write original English song lyrics about a playful unicorn chef making lemon butter orecchiette…
…Keep the chorus reusable for a 45-90 second video edit.
…
Structure:
[Verse 1]
…
```

**Operator paste (excerpt after three edits):**

```text
Write original 2-3 minutes English song lyrics about a playful unicorn chef making lemon butter orecchiette…
…Keep the chorus reusable for a 45-90 second video edit, but make a 2-3 minutes song.
…
Extend this structure to fit a 2-3 minutes song:
[Verse 1]
…
```

## Operator full song — Style of Music

The agent writes **Style of Music** without a duration clause.

Before generating the long track, the operator **appends** to the end of the style prompt (same line or new sentence):

```text
2-3 minutes song.
```

Example: if the agent style ends with `…close-mic lead vocals., k-pop, pop, electronic`, the operator paste becomes `…electronic, 2-3 minutes song.` or `…electronic. 2-3 minutes song.` — keep it on the style field only, never in the lyrics prompt.

## Short version (unchanged role)

**Short Version To Extract Later** describes how to cut the **generated** 2–3 minute master down to **45–90 s** for the vertical recipe video. It is not a second lyrics prompt.

## Separation rules (unchanged)

- **Style of Music**: genre, rhythm, production, instruments, vocal treatment, mix — plus operator suffix `2-3 minutes song.` for full generation only.
- **Auto Lyrics Prompt**: lyrics and section tags only — no genre, production, instrument, mix, or in-text vocal-style instructions.
- Default lyrics language: **English**.
- Do not imitate real artists, protected voices, brands, or recipe-tutorial lyrics.
- Video generation prompts must not request music.

## Agent checklist

- Ship `autoLyricsPrompt` as the **baseline** (no 2–3 minute opener, no “but make a 2-3 minutes song”, header `Structure:`).
- Ship `styleOfMusic` **without** `2-3 minutes song.`
- Fill `instructions.fullSongOperatorEdits` with the three lyrics bullets and `styleOfMusicSuffix`.
- Mirror operator steps in `suno-prompt.md` under **Operator full song (manual)**.
- Keep **Short Version To Extract Later** aligned with the 45–90 s vertical edit.
