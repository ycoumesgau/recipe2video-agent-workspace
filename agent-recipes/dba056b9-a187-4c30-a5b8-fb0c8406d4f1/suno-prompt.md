# Suno Prompt — Lemon Butter Orecchiette with Burrata

> Operator: apply **Operator full song (manual)** edits in Suno before generating the 2–3 minute master. Contract: `contracts/suno-music.md`.

## Status

- Recipe: Lemon Butter Orecchiette with Burrata
- Goal: Full song 2–3 min (operator-tuned); 45–90 s vertical excerpt
- Model: Suno 5.5 Advanced / Custom Mode

## Intent

Sensual R&B-pop bed for glossy lemon butter cups, burrata cream spill, caper crisp, and pistachio crunch — aligned with Seedance beats, no tutorial lyrics.

## Title

Golden Cup Sundown

## Style of Music

Slow-burn R&B pop with velvety electric piano, muted disco bass, brushed trap hats, and intimate close-mic vocals; verses stay breathy and tactile, pre-chorus adds stacked harmonies and a glassy synth lift, chorus blooms warm and glossy with finger snaps and a honey-sweet hook. Subtle ASMR ear candy: butter sizzle, soft crunch, cream sigh, lemon zest sparkle. Clean sensual mix, wide midnight sheen, no aggressive drops., r&b, pop, electronic

## Exclude Styles

No aggressive rap, no metal, no heavy rock, no children's choir, no advertising voice-over, no real artist imitation, no brand names, no recipe-tutorial lyrics, no ingredient counting, no software names.

## Auto Lyrics Prompt

Agent baseline — paste into Suno **after** applying the three operator edits in **Operator full song (manual)** for a 2–3 minute generation.

```text
Write original English song lyrics about a playful unicorn chef making lemon butter orecchiette with burrata and roasted pistachio crunch. Use only lyrics and section tags; do not explain the prompt. Do not include genre, production, instrument, mix, or vocal-style instructions. Do not write a recipe tutorial, quantities, numbered steps, brand names, or social media references.

Mood: intimate, luxurious, citrus-bright, creamy, crunchy, food-video ASMR energy, seductive but clean.

Lyric style: short singable lines, clipped phrasing, catchy repetitions, call-and-response energy, simple hooks, occasional parenthetical echoes like "(lemon butter)" or "(orecchiette)". Keep the chorus reusable for a 45-90 second video edit.

Story and imagery to weave in naturally:
- lemon zest curl, amber brown butter foam, garlic gold whisper
- orecchiette cups catching shiny sauce pools
- burrata tear, cream river, white meets gold
- caper crumb rain, pistachio emerald crunch
- basil green fall, steam halo, fork twirl lift
- final still bowl in the Licorn kitchen, satisfied glow

Must include naturally: orecchiette, burrata, lemon butter, brown butter, pistachio crunch, caper crisp, golden cup, cream spill, unicorn, Licorn kitchen.

Structure:
[Verse 1]
Zest falls, butter dreams, midnight pan glow.

[Pre-Chorus]
Cups fill with shine; anticipation builds.

[Chorus]
Chantable hook around golden cups, burrata cream, pistachio rain, lemon butter love.

[Verse 2]
Caper crisp, pistachio snap, basil drift.

[Bridge]
Softer breath: burrata tear, sauce thread, still hero bowl.

[Final Chorus]
Repeat chorus with richer harmony and final still bowl image.
```

## Short Version To Extract Later

Open on Verse 1 zest and butter images synced to segment-01, pre-chorus into pistachio and caper textures (segments 02-03), chorus over toss and burrata tear (segments 05-06), tag the motionless hero frame from segment-07 for the vertical outro handoff. Keep chorus hook under 15 seconds for TikTok/Reels.

## Operator full song (manual)

Before generating the **full 2–3 minute** master in Suno:

1. **Style of Music:** append `2-3 minutes song.` at the end.
2. **Auto Lyrics Prompt — three edits:**

| # | Find (agent baseline) | Replace with (operator paste) |
| --- | --- | --- |
| 1 | `Write original English song lyrics about` | `Write original 2-3 minutes English song lyrics about` |
| 2 | `Keep the chorus reusable for a 45-90 second video edit.` | `Keep the chorus reusable for a 45-90 second video edit, but make a 2-3 minutes song.` |
| 3 | `Structure:` | `Extend this structure to fit a 2-3 minutes song:` |
