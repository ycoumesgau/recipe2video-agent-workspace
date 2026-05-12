# Suno Prompt — [Recipe Name]

> **Recipe2Video:** les champs Suno Custom Mode pour l’app sont les sections `## Style of Music`, `## Exclude Styles`, `## Title`, `## Auto Lyrics Prompt` et `## Short Version To Extract Later` (titres de niveau 2 obligatoires pour le parsing). Les sections précédentes (`Status`, `Intent`, notes de session) restent du contexte opérationnel ; elles peuvent aussi être reprises dans `suno-prompt.json` sous `status` / `instructions`.

## Status

- Recipe: [Recipe Name]
- Goal: generate a long song that can be used as a full version, then edited into a shorter version for the vertical video.
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

- Generate the long version first, aiming for 2 to 3 minutes.
- Make the chorus reusable for a 45 to 90 second video edit.
- Keep lines short, singable, repeated, and image-driven.

## Style of Music

Style prompt to use as a separate Suno field (genre, rhythm, production, instruments, vocal treatment, mix only — no lyric instructions here):

```text
[Style prompt only: genre, rhythm, production, instruments, vocal treatment, mix feel.]
```

## Exclude Styles

```text
No aggressive rap, no metal, no heavy rock, no children's choir, no advertising-style spoken voice, no voice-over narration, no real artist reference, no brand names, no French lyrics except recipe names that must stay French, no recipe tutorial lyrics, no ingredient counting.
```

## Title

```text
[English song title]
```

## Auto Lyrics Prompt

Paste this into Suno’s automatic lyrics prompt field. It must stay under 3000 characters and keep musical style out of the lyrics prompt.

```text
Write original English song lyrics about [short character + recipe premise]. Use only lyrics and section tags; do not explain the prompt. Do not include genre, production, instrument, mix, or vocal-style instructions. Do not write a recipe tutorial, quantities, numbered steps, brand names, software names, or social media references.

Mood: [3 to 6 emotional words], food-video ASMR energy, but not childish.

Lyric style: short singable lines, clipped phrasing, catchy repetitions, call-and-response energy, simple hooks, occasional parenthetical echoes like "([recipe name])". Keep the chorus very reusable for a 45-90 second video edit.

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

[Pre-Chorus]
[Final assembly gets closer.]

[Chorus]
Repeat the same chorus or a very close variation.

[Bridge]
Softer moment: [filling / cream / sauce / final sensory detail].

[Final Chorus]
Repeat the chorus with extra energy and a proud final image.
```

## Short Version To Extract Later

For a 45 to 90 second video, aim for a music edit based on:

1. Very short `[Intro]` if generated.
2. Beginning of `[Verse 1]` over the opening food hook.
3. `[Pre-Chorus]` if the build works.
4. Full `[Chorus]`.
5. A piece of `[Bridge]` if it matches the filling or creamy payoff.
6. `[Final Chorus]` or the end of the chorus over the hero shot.

The chorus should ideally land on the strongest visual payoff shots.
