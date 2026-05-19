# Suno Prompt — Lemon Butter Orecchiette with Burrata

> **Recipe2Video:** The app parses Suno Custom Mode content from these level-2 sections: `## Title`, `## Style of Music`, `## Exclude Styles`, `## Auto Lyrics Prompt`, and `## Short Version To Extract Later`. Operator applies **Operator full song** edits in Suno before generating the 2-3 minute master. Contract: `contracts/suno-music.md`.

## Status

- Recipe: Lemon Butter Orecchiette with Burrata, Crispy Capers and Roasted Pistachios
- Goal: operator generates a **2-3 minute** full song in Suno, then cuts a **45-90 s** excerpt for the vertical video.
- Target model: Suno 5.5 in Advanced / Custom Mode.
- Video use: TikTok, YouTube Shorts, Instagram Reels.

## Intent

The song mirrors the edit's glossy food-porn arc: pistachio-caper crunch, brown butter and lemon hiss, sauce-catching orecchiette cups, the burrata cream break, and the final satisfied Licorn hero shot.

## Session notes (voice, length, hook)

**Voice**

- Select a bright, close-mic pop vocal persona in Suno if `Voices` is available.
- Do not ask Suno to imitate a real singer, existing artist, or protected voice.

**Structure**

- The chorus should land naturally on the burrata split, crunchy pistachio-caper shower, and final hero bowl.
- The committed prompt is the agent baseline; apply the operator edits below before full-song generation.

## Title

```text
Lemon Butter Afterglow
```

## Style of Music

```text
Glossy K-pop electronic pop with crisp four-on-the-floor kicks, rubbery synth bass, clipped staccato percussion, bright citrusy synth plucks, silky pre-chorus lift, candy-bright chorus, tiny glitch fills before drops, sparkle FX like lemon zest, close-mic lead vocals, stacked harmony hook, clean punchy mix with warm low end and neon sheen., k-pop, pop, electronic
```

## Exclude Styles

```text
No aggressive rap, no metal, no heavy rock, no children's choir, no advertising-style spoken voice, no voice-over narration, no real artist reference, no brand names, no French lyrics except recipe names that must stay French, no recipe tutorial lyrics, no ingredient counting.
```

## Auto Lyrics Prompt

Paste this into Suno's automatic lyrics prompt field **after** applying **Operator full song** edits for a 2-3 minute generation. The block below is the **agent baseline** before operator edits.

```text
Write original English song lyrics about a joyful unicorn kitchen mascot making lemon butter orecchiette with burrata, crispy capers and roasted pistachios. Use only lyrics and section tags; do not explain the prompt. Do not include genre, production, instrument, mix, or vocal-style instructions. Do not write a recipe tutorial, quantities, numbered steps, brand names, software names, or social media references.

Mood: glossy, flirty, citrus-bright, creamy, crunchy, late-night food-video ASMR energy, but not childish.

Lyric style: short singable lines, clipped phrasing, catchy repetitions, call-and-response energy, simple hooks, occasional parenthetical echoes like "(lemon butter)". Keep the chorus reusable for a 45-90 second video edit.

Story and imagery to weave in naturally:
- roasted pistachio sparks and salty caper crunch
- brown butter turning amber, lemon hitting with a hiss
- little orecchiette cups catching glossy sauce
- burrata opening like a soft white moon
- basil, pepper, parmesan and lemon zest falling over cream
- final bowl glowing on the kitchen island with a satisfied unicorn smile

Must include naturally: lemon butter, orecchiette, burrata, pistachio, caper, basil, golden crunch, creamy afterglow.

Structure:
[Verse 1]
Pistachio sparks, caper crackle, lemon bright on the counter.

[Pre-Chorus]
Brown butter glows and the little pasta cups start shining.

[Chorus]
Big chantable hook around lemon butter + orecchiette + burrata cream + golden crunch. Repeat "lemon butter" as the hook.

[Verse 2]
Orecchiette catches sauce; burrata opens; basil and zest fall like light.

[Bridge]
Softer moment: cream, crunch, citrus, one glowing bowl, unicorn smile.

[Final Chorus]
Repeat the chorus with extra energy and a proud final image.
```

## Short Version To Extract Later

```text
For a 45-90 second vertical cut, start with a tight intro or Verse 1 line over the crunch-shower hook, use the pre-chorus under the brown-butter lemon hiss and glossy pasta toss, land the full chorus on burrata opening and pistachio-caper topping rain, then use the final chorus or chorus tag over the motionless hero bowl and Licorn outro.
```

## Operator full song (manual)

Apply **in Suno** before generating the long track. Do not change the agent artifacts on disk unless intentionally revising the recipe checkpoint.

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
