# Suno Prompt — Fluffy Japanese Soufflé Pancakes

> Operator: apply **Operator full song** edits in Suno before generating the 2–3 minute master. Contract: `contracts/suno-music.md`.

## Status

- **Recipe:** Fluffy Japanese Soufflé Pancakes (Just One Cookbook)
- **Video ID:** f4d7b0c1-f107-4596-8a53-880386af5c18
- **Goal:** 2–3 min full song (operator-tuned); 45–90 s vertical excerpt

## Intent

Cottony morning joy: meringue peak, airy fold, steam towers, golden flip, berry-and-maple hero. Chorus built around “cloud stack” for TikTok/Reels cuts synced to Seedance segments 01–06.

## Title

```text
Cloud Stack Morning
```

## Style of Music

```text
Kawaii future bass pop with soft sidechain pump, bouncy marimba and glockenspiel hooks, fluffy synth pads, tight punchy kick, light claps, sparkling arpeggios, warm sub, airy female lead vocal, playful Japanese breakfast café energy, glossy mix, sweet but not childish., pop, electronic, kawaii
```

## Exclude Styles

```text
No aggressive rap, no metal, no heavy rock, no lo-fi mud, no children's choir, no advertising voice-over, no spoken recipe steps, no real artist imitation, no brand names, no tutorial counting lyrics.
```

## Auto Lyrics Prompt

Agent baseline — paste into Suno **after** applying the three operator edits in **Operator full song (manual)** for a 2–3 minute generation.

```text
Write original English song lyrics about a joyful unicorn mascot making fluffy Japanese soufflé pancakes in a bright kitchen. Use only lyrics and section tags; do not explain the prompt. Do not include genre, production, instrument, mix, or vocal-style instructions. Do not write a recipe tutorial, quantities, numbered steps, brand names, software names, or social media references.

Mood: playful, cottony, morning-light, magical food-video ASMR energy, gentle triumph.

Lyric style: short singable lines, clipped phrasing, catchy repetitions, simple hooks, occasional parenthetical echoes like "(so fluffy)". Keep the chorus reusable for a 45-90 second video edit.

Story and imagery to weave in naturally:
- glossy meringue peak standing tall, sugar shine
- pale batter fold, air bubbles like little clouds
- tall stack rising in the pan, steam like morning mist
- golden flip, springy jiggle, cotton bite
- berries, cream curl, sugar snow, maple ribbon
- final tower on the island, proud smile, cloud on a plate

Must include naturally: soufflé, pancake, cloud, steam, golden, flip, meringue, berry, maple, unicorn.

Structure:
[Verse 1]
Morning whisk, meringue peak, pale ribbon, sift like snow.

[Pre-Chorus]
Fold it soft, don't break the air; something tall is growing there.

[Chorus]
Big chantable hook around unicorn + soufflé pancakes + cloud stack + golden flip. Repeat "cloud stack" as hook.

[Verse 2]
Low heat patience, lid steam, three towers tremble, golden turn.

[Bridge]
Softer moment: cream and berries, sugar dust, one bite feels like floating.

[Final Chorus]
Return hook with highest joy; end on "cloud stack" repetition.
```

## Short Version To Extract Later

```text
Target 52–68s vertical excerpt. Open on instrumental hook 0–4s. Verse 1 from first whisk image (~4s) through sift line. Pre-chorus into Chorus 1 at first meringue peak / fold montage (~18s). Keep chorus through mound-and-steam segment (~18–38s). Verse 2 or shortened pre-chorus under flip beat (~38–48s). Final chorus hook under plating hero and sugar snow (~48–62s). Fade or hard end on last "cloud stack" before outro SFX. Do not include spoken intro; align downbeats to hard cuts in seedance segments 01–06.
```

## Operator full song (manual)

Before generating the **full 2–3 minute** track in Suno Custom Mode:

1. **Auto Lyrics Prompt** — apply these three edits to the baseline above:
   - Opening: `Write original English song lyrics` → `Write original 2-3 minutes English song lyrics`
   - Lyric style: after `Keep the chorus reusable for a 45-90 second video edit` add `, but make a 2-3 minutes song`
   - Structure header: `Structure:` → `Extend this structure to fit a 2-3 minutes song:`
2. **Style of Music** — append at the end: `2-3 minutes song.`
3. Generate the long master, then use **Short Version To Extract Later** for the vertical assembly.
