# Decisions — Roasted Strawberries and Cream Popsicles

## Ingest (recipe_ingest)

- **Source:** https://www.forkknifeswoon.com/roasted-strawberries-and-cream-popsicles/ (Fork Knife Swoon).
- **Production preset:** `asmr_food`, model `seedance2`, reference images via `gpt_image_2`.

## Creative direction

- **Opening:** Texture-first macro juice bead on halved strawberry flesh (scene-01), paid off immediately by overhead pan layout (scene-02). No mise en place, no ingredient flatlay, no final-pop hook.
- **Hero format:** Layered strawberry-cream **swirl** pops (not fully blended uniform pops) unless the operator answers `pops-format` clarifying question differently.
- **Scale:** Standard silicone bar mold; pops about 10–12 cm long and 2.5–3 cm wide; ~20–24 roasted halves on a half sheet.
- **Detail/context balance:** 36 logical scenes, ~78% detail / ~22% context.
- **Destructive beats:** Warm-water release and stick pull live in **segment-05** only. **Segment-06** (N-1) ends on motionless intact trio matching `FinalDishVisual`. No bite, no spoon dive, no melt drip on hero.
- **Outro:** Fixed `segment-outro` with `<APP_OVERRIDE>` and five-reference contract.

## Reference strategy

- Five GPT-Image recipe states: `RoastedStrawberriesJammy`, `ChunkyStrawberryPuree`, `CoconutCreamSwirlBase`, `PopsicleMoldLayeredFill`, `FrozenPopsicleStreaked`, plus `FinalDishVisual` (short dish-only lead sentence for outro embed).
- Food processor represented with `@Blender` asset shape (no dedicated processor asset in library).
- Transfer scrape uses `@SiliconeSpatula` as flexible scraper, not hot cloth-in-hand.

## Seedance plan

- **7 segments** (6 creative + 1 outro): 5 + 6 + 7 + 8 + 7 + 6 + 5 = **44 s** creative + 5 s outro.
- Oven tray insert uses already-open `@OvenWide` (no door close).

## Open questions

See `recipe-analysis.json` → `clarifyingQuestions`:

1. Swirled vs blended hero (`pops-format`) — **defaulted to swirled** for this ingest.
2. Mold geometry (`mold-geometry`) — **defaulted to narrow bar molds**.

## Suno

- Track title **Ruby Swirl Freeze**; K-pop electronic pop baseline; operator applies 2–3 min Suno edits per `suno-prompt.json` → `instructions.fullSongOperatorEdits`.
