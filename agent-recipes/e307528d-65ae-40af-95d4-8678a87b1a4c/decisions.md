# Decisions - Lemon Butter Orecchiette with Burrata and Roasted Pistachios

## Source and adaptation

- Source URL: https://www.delscookingtwist.com/lemon-butter-pasta-with-burrata-cheese/
- Source recipe: Lemon Butter Pasta with Burrata Cheese by Del's Cooking Twist.
- Required adaptation: use orecchiette for the pasta shape throughout, replacing spaghetti or generic pasta options.
- Required adaptation: add roasted pistachios as a supplemental crunchy topping and show their dry-roast step.
- Direction: make the video sensual, glossy, food-porn, and ASMR-forward while keeping the culinary actions readable and clean.

## Editorial choices

- Opening uses a final-state burrata rupture over glossy orecchiette, then immediately pays it off with pistachio and caper crumb crunch before cutting back to the pistachio prep step.
- The storyboard uses 36 logical scenes: mostly macro/detail shots, with only a few kitchen/context beats for orientation.
- The Seedance plan uses 8 References-mode segments for seedance2 at 1080:1920 vertical.
- The supplemental pistachio step is both an early hook and a final texture payoff.

## Reference policy

- No generated recipe-specific intermediate image references are planned at ingest.
- Reason: the creator explicitly asked to avoid generated intermediate references unless indispensable, and this dish uses visually common states that can be controlled by prompt locks: orecchiette cup shape, burrata cream, brown butter, crumb topping, pistachio shards, and final fork lift.
- If later validation shows Seedance cannot preserve orecchiette or burrata geometry, the first fallback should be a single final hero state reference, not a full set of micro-scene frames.

## Scale and quantity locks

- Orecchiette: 2-3 cm ear-shaped cups, not spaghetti, penne, giant shells, or miniature grains.
- Pistachios: rough 3-6 mm roasted shards, one-to-two tablespoon sprinkle per plate, not powder and not oversized chunks.
- Burrata: one palm-sized ball or two small balls for the serving, visibly torn open with thick white cream.
- Basil: 6-8 small torn pieces per hero plate, not a salad pile.
- Caper breadcrumbs: about two spoonfuls per plate, dry and sandy, not a wet paste.

## Open questions

None blocking. The source recipe and creator instructions provide enough information for all required planning artifacts.

## 2026-05-18 main sync review

- Pulled and merged `origin/main` to use the updated Recipe2Video skills and asset-reference guidance.
- Updated the logical scene mix to 28 detail scenes and 8 context scenes (about 78/22), matching the refreshed TikTok food-direction target while keeping the same 36-scene storyboard.
- Kept the no-generated-recipe-state-reference decision: the updated audit noted a final hero reference could reduce risk, but the creator explicitly asked to avoid generated intermediate references unless indispensable, and current prompt locks remain adequate for orecchiette, burrata, and pistachio geometry.
- Removed final vocalization-risk wording from Seedance audio cues; final satisfaction now uses silent posture plus kitchen room tone, not breath or speech.

## 2026-05-18 Seedance duration correction

- Pulled and merged the latest `origin/main` updates, which make the Seedance 2 minimum duration explicit: every segment `durationTarget` must be an integer from 5 to 15 seconds.
- Corrected `segment-02` from 4 seconds to 5 seconds and retimed its prompt / `promptInitial` / timing bullets to end at 5.0s.
- Adjusted logical scenes `scene-07` to `scene-09` so the orecchiette cooking beat supports the 5-second segment without changing the storyboard mapping.
- No recipe-specific generated reference was added; the no-generated-reference decision remains intentional because the creator asked to avoid intermediate references unless indispensable.
