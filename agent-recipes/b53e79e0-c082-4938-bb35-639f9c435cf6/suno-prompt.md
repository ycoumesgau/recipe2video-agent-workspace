# Suno — Fold the Crunch

## Status

- **Recipe:** TikTok Wrap Hack — Crunchwrap Supreme Edition
- **Goal:** Full song 2–3 min for streaming; 45–90 s excerpt for vertical edit
- **Model:** Suno 5.5 Advanced / Custom Mode
- **Target duration:** 2–3 minutes (full, operator-tuned); excerpt for short video

## Intent

Nu-disco pop track that mirrors the video arc: radial slit → spice beef → four-quadrant color block → fold cascade → grill crisp → intact golden triangle hero. Lyrics stay sensory and visual, never tutorial.

## Session notes

- Paste fields in Suno order: Title → Style → Excludes → Auto lyrics (after operator edits).
- Voices / persona: playful talk-sung lead, gang chorus.
- Align chorus downbeats to fold montage and grill flip in assembly.

## Title

Fold the Crunch

## Style of Music

Funky nu-disco pop with tight slap bass, crisp handclaps on two and four, and bright brass stabs; verses stay playful and talk-sung with dry close vocals, pre-chorus adds filtered guitar chops and a rising talkbox swell, chorus bursts wide with stacked harmonies and a sticky four-word hook. Sprinkle vinyl crackle, triangle bells, and a short breakbeat fill before each chorus drop. Punchy modern mix with warm saturation and glossy top-end sheen., funk, pop, disco

## Exclude Styles

mumble rap, death metal, lo-fi bedroom, EDM big-room drop, sad piano ballad, country twang, reggaeton dembow, bossa nova, tutorial jingle, artist imitation

## Auto Lyrics Prompt

Write original English song lyrics about a viral tortilla wrap hack turned crunchwrap supreme: a radial cut, four colorful quadrants, a folding cascade, sizzling taco beef, sour cream silk against crunchy chips, melted cheese, and a golden grilled triangle that steams on the counter.

Lyric style: short singable lines; vivid food textures and colors; playful confidence; no quantities or numbered steps; no recipe instructions; sensory verbs (sizzle, fold, crackle, ooze); keep the hook physical and visual. Keep the chorus reusable for a 45-90 second video edit.

Structure:
[Verse 1] — discovery: flat circle, one brave slit, four corners waiting
[Pre-Chorus] — spice dust on heat, colors landing like a tiny flag
[Chorus] — chantable hook about folding the crunch; mention golden triangle and cheese peek
[Verse 2] — fold travel: lift, cross, tuck; layers hiding then hugging
[Pre-Chorus 2] — pan hiss, press, flip once, steam rising
[Chorus] — repeat hook with one new image (crackle / steam / shine)
[Bridge] — half-time swagger: crunch vs cream contrast, hands off the plate
[Final Chorus] — biggest gang vocals; end on satisfied held note over implied kitchen glow

## Short Version To Extract Later

Target 52–68s vertical excerpt after full master exists. Open on instrumental pre-chorus swell (4 bars) under radial-cut B-roll, hard-cut to Chorus 1 from first hook line through end of chorus (bars 1–16). Verse 2 bars 1–8 over quadrant-fill montage, jump to Chorus 2 full, then 4-bar instrumental tag on final hook syllable with grilled-triangle hero held silent for last 2 bars. Fade under kitchen ASMR tail; no new lyrics after final chorus.

## Operator full song (manual)

Before generating the **full 2–3 minute** song in Suno, apply these edits to the baseline above (do not commit these into `suno-prompt.json` `fields`):

1. **Auto Lyrics opening:** `Write original English song lyrics` → `Write original 2-3 minutes English song lyrics`
2. **Lyric style line:** after `Keep the chorus reusable for a 45-90 second video edit.` add `, but make a 2-3 minutes song`
3. **Structure header:** `Structure:` → `Extend this structure to fit a 2-3 minutes song:`
4. **Style of Music:** append `2-3 minutes song.` at the end of the style prompt
