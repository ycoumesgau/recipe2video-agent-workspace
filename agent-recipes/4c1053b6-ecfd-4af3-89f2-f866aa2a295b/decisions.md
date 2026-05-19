# Decisions — Lemon Butter Orecchiette with Burrata

## Source and creator instructions

- Source recipe: Del's Cooking Twist, "Lemon Butter Pasta with Burrata Cheese".
- Pasta decision: override the source's spaghetti suggestion and use **orecchiette** everywhere. Prompts repeatedly lock 2-3 cm ear-shaped cups to prevent spaghetti/penne drift.
- Added creator topping: **roasted pistachios** are treated as a supplemental recipe step and integrated into the crispy caper-panko topping.
- Creative tone: "really sexy and food porn" is expressed through macro burrata cream, crunchy topping showers, lemon-butter gloss and ASMR detail; no paid generation was launched.

## Story and structure decisions

- Opening hook is a texture-first crunch shower over glossy orecchiette and burrata cream, not a neutral mise en place or final slicing shot.
- Scene 2 clarifies the opening immediately by showing the pasta, burrata and crunchy topping together.
- Logical plan contains 36 scenes with a detail-heavy ratio and texture payoffs every 3-5 scenes.
- Seedance plan contains 8 total segments: 7 creative segments plus the standardized Licorn outro.
- The main destructive food-porn beat is the burrata split in `segment-06`; `segment-07` is reserved for the final intact, motionless dish handoff before the app-controlled outro.

## Reference decisions

- Recipe-specific state references are planned for orecchiette shape, crispy pistachio-caper crumb, brown butter lemon sauce, glossy sauced orecchiette, opened burrata and `FinalDishVisual`.
- `FinalDishVisual` is the source of truth for `segment-07` and `segment-outro`.
- Because the asset library has no dedicated skillet asset, `wok` is used only as a broad pan geometry anchor for induction pan actions; prompts explicitly prevent cuisine/style drift.
- Character-class references are not used in recipe-specific `conditioningReferences`.

## Gaps and assumptions

- No clarifying questions are blocking this ingest. The source provides enough ingredients, method and timing; creator overrides are explicit.
- Pistachio quantity is assumed at about 1/3 cup chopped for visual readability.
- Final hero dish is planned as one shallow bowl serving rather than four individual plates.
