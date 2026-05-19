# Suno Prompt — Vanilla Layer Cake with Rose Buttercream

> Operator: apply **Operator full song (manual)** edits in Suno before generating the 2–3 minute master. Contract: `contracts/suno-music.md`.

## Status

- Recipe: Vanilla Layer Cake with Rose Buttercream
- Goal: Full song 2–3 min (operator-tuned); 45–90 s vertical excerpt
- Model: Suno 5.5 Advanced / Custom Mode

## Intent

Pastel electropop bed for blush rose milk spiral, glossy batter ribbon, golden layer bake, buttercream peaks, stack and rosette — aligned with Seedance beats, no tutorial lyrics.

## Title

Blush Spiral Sky

## Style of Music

Dreamy electropop baking pop with soft sidechain pads, twinkling music-box bells, and a bouncy four-on-the-floor kick; verses stay airy and intimate with close-mic whisper-sung lines, pre-chorus adds stacked harmonies and a rose-glass synth swell, chorus blooms cotton-candy bright with finger snaps and a sing-along hook. Subtle ASMR ear candy: powder puff, whisk tick, wire scrape, frosting pip squeak. Clean pastel mix, wide daylight sheen, no aggressive drops., pop, electronic, indie pop

## Exclude Styles

No aggressive rap, no metal, no heavy rock, no children's choir, no advertising voice-over, no real artist imitation, no brand names, no recipe-tutorial lyrics, no ingredient counting, no software names.

## Auto Lyrics Prompt

Agent baseline — paste into Suno **after** applying the three operator edits in **Operator full song (manual)** for a 2–3 minute generation.

```text
Write original English song lyrics about a playful unicorn chef making a vanilla layer cake with rose buttercream in the Licorn kitchen. Use only lyrics and section tags; do not explain the prompt. Do not include genre, production, instrument, mix, or vocal-style instructions. Do not write a recipe tutorial, quantities, numbered steps, brand names, or social media references.

Mood: romantic, pastel, floral-soft, cozy baking glow, food-video ASMR energy, celebratory but gentle.

Lyric style: short singable lines, clipped phrasing, catchy repetitions, call-and-response energy, simple hooks, occasional parenthetical echoes like "(blush spiral)" or "(rose cream)". Keep the chorus reusable for a 45-90 second video edit.

Story and imagery to weave in naturally:
- rose powder blush spiral in milk, vanilla fleck streak
- butter cubes in flour cloud, glossy batter ribbon
- golden dome bake, wire leveler crumb curl
- pale butter whip to blush satin peaks
- layer stack squeeze, mirror coat, rosette kiss
- wedge slice four-layer reveal, then still intact cake on stand
- final motionless hero cake in the Licorn kitchen, satisfied glow

Must include naturally: vanilla cake, rose buttercream, blush spiral, golden layers, rosette border, cake stand, unicorn, Licorn kitchen.

Structure:
[Verse 1]
Blush spiral dreams in a glass moon bowl.

[Pre-Chorus]
Ribbons fall; the tower starts to grow.

[Chorus]
Chantable hook around blush spiral, rose cream clouds, golden layers, birthday glow.

[Verse 2]
Wire scrape curl, mirror coat shine, rosette crown.

[Bridge]
Softer breath: four layers whisper, still cake on the stand.

[Final Chorus]
Repeat chorus with richer harmony and intact hero cake image.
```

## Short Version To Extract Later

Open on Verse 1 rose milk images synced to segment-01, pre-chorus into batter and bake textures (segments 02-04), chorus over buttercream whip and stack coat (segments 05-06), tag the motionless intact hero from segment-07 for the vertical outro handoff. Keep chorus hook under 15 seconds for TikTok/Reels.

## Operator full song (manual)

Before generating the **full 2–3 minute** master in Suno:

1. **Style of Music:** append `2-3 minutes song.` at the end.
2. **Auto Lyrics Prompt — three edits:**

| # | Find (agent baseline) | Replace with (operator paste) |
| --- | --- | --- |
| 1 | `Write original English song lyrics about` | `Write original 2-3 minutes English song lyrics about` |
| 2 | `Keep the chorus reusable for a 45-90 second video edit.` | `Keep the chorus reusable for a 45-90 second video edit, but make a 2-3 minutes song.` |
| 3 | `Structure:` | `Extend this structure to fit a 2-3 minutes song:` |
