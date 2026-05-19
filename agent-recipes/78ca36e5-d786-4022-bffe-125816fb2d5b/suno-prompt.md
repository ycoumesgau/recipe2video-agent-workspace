# Suno Prompt — Small Batch Baked Ube Mochi Donuts

> Operator: apply **Operator full song** edits in Suno before generating the 2–3 minute master. Contract: `contracts/suno-music.md`.

## Title

```text
Lilac Ring Glow
```

## Style of Music

```text
Dreamy K-pop electronic pop with soft four-on-the-floor kick, bouncy rubber synth bass, glittery bell arpeggios, airy pad swells, playful handclaps on offbeats, glossy chorus lift, close intimate lead vocal, subtle vinyl warmth, wide shimmer reverb, tiny glitch fill before chorus drops, clean punchy mix, pastel neon sheen, k-pop, pop, electronic
```

## Exclude Styles

```text
No aggressive rap, no metal, no heavy rock, no children's choir, no advertising spoken voice, no voice-over narration, no real artist imitation, no brand names, no recipe-tutorial counting lyrics, no ingredient measurements in lyrics.
```

## Auto Lyrics Prompt

Agent baseline — paste into Suno **after** applying the three operator edits in **Operator full song (manual)** for a 2–3 minute generation.

```text
Write original English song lyrics about a joyful unicorn pastry mascot making small-batch baked ube mochi donuts in a bright kitchen. Use only lyrics and section tags; do not explain the prompt. Do not include genre, production, instrument, mix, or vocal-style instructions. Do not write a recipe tutorial, quantities, numbered steps, brand names, software names, or social media references.

Mood: playful, glossy, cozy-magical, chewy-crisp ASMR energy, pastel purple joy, not childish.

Lyric style: short singable lines, clipped phrasing, catchy repetitions, call-and-response sparkle, simple hooks, occasional parenthetical echoes like "(lilac ring)". Keep the chorus reusable for a 45-90 second video edit.

Story and imagery to weave in naturally:
- violet batter pour, meniscus shimmer, elastic whisk ribbon
- ube jam marble, lilac color bloom, mochi sweetness
- six rings filled to the brim, flat bake, crispy shell crackle
- oven warmth, springy bounce, steam hush
- lavender glaze dip, upside-down flip, sprinkle rain ticks
- six glazed crowns on a rack, proud unicorn smile, hands stay kind

Must include naturally: ube, mochi, lilac, glaze, sprinkle, unicorn, bake, chewy, crispy crown.

Structure:
[Verse 1]
Violet stream, sugar gleam, whisk ribbon in a lilac dream.

[Pre-Chorus]
Jam swirls in, color blooms, six little rings make room.

[Chorus]
Big chantable hook around unicorn + ube mochi donuts + lilac glaze + chewy crispy crown. Repeat "lilac ring" as a hook.

[Verse 2]
Pan filled high, oven sigh, flat bottoms, tops that spring alive.

[Bridge]
Softer moment: glaze curtain falls, sprinkles dance, the rack recalls.

[Final Chorus]
Repeat chorus with extra energy and a proud still rack image.
```

## Short Version To Extract Later

```text
Target 52–68 s vertical excerpt. Open on chorus hook ("lilac ring" / ube mochi chant). Map cuts: 0–4s chorus hook over batter pour segment; 4–10s pre-chorus color bloom over mix segment; 10–18s verse 2 oven/bake energy over hard-cut bake segment; 18–26s bridge glaze imagery over dip/sprinkle segment; 26–38s final chorus doubled over hero rack + mascot; 38–45s instrumental sparkle tail under Licorn outro sync. Avoid lyric lines about counting ingredients. Keep SFX-forward video dominant; music ducks under ASMR in edit, not in Suno prompt.
```

## Operator full song (manual)

**Style of Music** — append:

```text
2-3 minutes song.
```

**Auto Lyrics Prompt** — three replacements:

| # | Find | Replace with |
| --- | --- | --- |
| 1 | `Write original English song lyrics about` | `Write original 2-3 minutes English song lyrics about` |
| 2 | `Keep the chorus reusable for a 45-90 second video edit.` | `Keep the chorus reusable for a 45-90 second video edit, but make a 2-3 minutes song.` |
| 3 | `Structure:` | `Extend this structure to fit a 2-3 minutes song:` |
