# Suno Prompt — [Recipe Name]

> **Recipe2Video:** The app parses Suno Custom Mode content from these level-2 sections: `## Title`, `## Style of Music`, `## Exclude Styles`, `## Auto Lyrics Prompt`, and `## Short Version To Extract Later`. Recommended order (matches typical Suno workflow) is **title first**, then style, excludes, auto lyrics, short-edit plan. Earlier sections (`Status`, `Intent`, session notes, operator full song) are operator context only; you can also mirror them in `suno-prompt.json` under `status` / `instructions`. Full contract: `contracts/suno-music.md`.

## Status

- Recipe: [Recipe Name]
- Goal: operator generates a **2–3 minute** full song in Suno, then cuts a **45–90 s** excerpt for the vertical video.
- Target model: Suno 5.5 in Advanced / Custom Mode.
- Video use: TikTok, YouTube Shorts, Instagram Reels.

## Intent

[One short paragraph explaining how the song echoes the video, the recipe arc, the key textures, and the final hero shot.]

## Session notes (voice, length, hook)

Use these as operator notes before generating. They are not pasted into a single Suno text field as-is; align actions with Suno’s UI (Voices, Advanced settings).

**Voice**

- Select the character voice or vocal persona in Suno before generating.
- If `Voices` is available, use it instead of only describing the voice in text.
- Keep `Audio Influence` fairly high if Suno offers that setting to strengthen the selected voice.
- Do not ask Suno to imitate a real singer, an existing artist, or any protected voice.

**Structure**

- The agent ships a **baseline** Auto Lyrics Prompt (hook-friendly, excerpt-ready). The operator applies **three fixed edits** (see **Operator full song**) before generating the **2–3 minute** master.
- Append **`2-3 minutes song.`** to **Style of Music** for full generation only (see operator section).
- After the long master exists, use **Short Version To Extract Later** to cut **45–90 s** for the video.

## Title

English track name — set this **first** in Suno so the project is named before pasting style and lyrics.

```text
[English song title]
```

## Style of Music

Style prompt to use as a separate Suno field (genre, rhythm, production, instruments, vocal treatment, mix only — no lyric instructions here). **Agent baseline:** do **not** include `2-3 minutes song.` — the operator appends it before full generation (see **Operator full song**).

```text
[Style prompt only: genre, rhythm, production, instruments, vocal treatment, mix feel.]
```

## Exclude Styles

```text
No aggressive rap, no metal, no heavy rock, no children's choir, no advertising-style spoken voice, no voice-over narration, no real artist reference, no brand names, no French lyrics except recipe names that must stay French, no recipe tutorial lyrics, no ingredient counting.
```

## Auto Lyrics Prompt

Paste this into Suno’s automatic lyrics prompt field **after** applying **Operator full song** edits for a 2–3 minute generation. The block below is the **agent baseline** (before operator edits). It must stay under 3000 characters and keep musical style out of the lyrics prompt.

```text
Write original English song lyrics about [short character + recipe premise]. Use only lyrics and section tags; do not explain the prompt. Do not include genre, production, instrument, mix, or vocal-style instructions. Do not write a recipe tutorial, quantities, numbered steps, brand names, software names, or social media references.

Mood: [3 to 6 emotional words], food-video ASMR energy, but not childish.

Lyric style: short singable lines, clipped phrasing, catchy repetitions, call-and-response energy, simple hooks, occasional parenthetical echoes like "([recipe name])". Keep the chorus reusable for a 45-90 second video edit.

Story and imagery to weave in naturally:
- [opening texture hook]
- [sub-recipe or first major transformation]
- [second texture / contrast]
- [baking / cooking transformation]
- [cream / sauce / filling / topping]
- [final garnish]
- [hero shot and satisfied character]

Must include naturally: [recipe name], [3-8 keywords], [final hook phrase].

Structure:
[Verse 1]
[Opening arc images.]

[Pre-Chorus]
[Build anticipation.]

[Chorus]
Big chantable hook around [recipe name] + [character] + [core payoff]. Repeat the recipe name as a hook.

[Verse 2]
[Middle recipe arc and visual transformations.]

[Bridge]
Softer moment: [filling / cream / sauce / final sensory detail].

[Final Chorus]
Repeat the chorus with extra energy and a proud final image.
```

## Operator full song (manual)

Apply **in Suno** before generating the long track. Do not change the agent artifacts on disk unless you are intentionally revising the recipe checkpoint.

**Style of Music** — append to the end of the agent style prompt:

```text
2-3 minutes song.
```

**Auto Lyrics Prompt** — three replacements on the agent baseline:

| # | Find (agent baseline) | Replace with (operator paste) |
| --- | --- | --- |
| 1 | `Write original English song lyrics about` | `Write original 2-3 minutes English song lyrics about` |
| 2 | `Keep the chorus reusable for a 45-90 second video edit.` | `Keep the chorus reusable for a 45-90 second video edit, but make a 2-3 minutes song.` |
| 3 | `Structure:` | `Extend this structure to fit a 2-3 minutes song:` |

## Short Version To Extract Later

For a 45 to 90 second video, aim for a music edit based on:

1. Very short `[Intro]` if generated.
2. Beginning of `[Verse 1]` over the opening food hook.
3. `[Pre-Chorus]` if the build works.
4. Full `[Chorus]`.
5. A piece of `[Bridge]` if it matches the filling or creamy payoff.
6. `[Final Chorus]` or the end of the chorus over the hero shot.

The chorus should ideally land on the strongest visual payoff shots.
