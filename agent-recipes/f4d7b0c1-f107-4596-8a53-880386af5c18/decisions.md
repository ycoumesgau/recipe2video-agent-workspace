# Decisions — Fluffy Japanese Soufflé Pancakes

## Source

- **URL:** https://www.justonecookbook.com/souffle-pancake/ (Just One Cookbook, Nami Chen)
- **Ingest stage:** `recipe_ingest`
- **Production defaults:** asmr_food, seedance2, gpt_image_2 references, eleven_multilingual_v2 / eleven_text_to_sound_v2 (app-side; not invoked here)

## Creative direction

| Topic | Decision | Rationale |
| --- | --- | --- |
| Opening | Texture-first stiff meringue peak (scene 1–2 payoff) | Rules forbid ingredient lineup; meringue is the fragile hero transformation |
| Hook alternate (rejected for open) | Steam lid reveal | Strong but deferred; peak fold chain is faster scroll-stop |
| Logical scenes | 36 scenes, ~75% detail | Matches contract band 30–48 and tiktok-food-direction ratio |
| Seedance segments | 6 creative + 1 outro (52s creative + 5s outro) | Covers meringue, batter, fold, steam cook, flip, static hero |
| Pancake count | Exactly 3 per batch in 28–30 cm pan | Source equipment note; prevents model drift |
| Scale | Base 7–8 cm, height 4–6 cm per mound; stack 12–15 cm plated | Explicit positive + negative size locks in prompts |
| Stovetop | @InductionWide + described dark nonstick skillet | No frying-pan asset; induction is Licorn canonical |
| Whipped cream | One quenelle beat on hero; prep compressed | Optional sub-recipe not given its own segment |
| Destructive food porn | None in segment 06 final hold or outro prep | Syrup drizzle and sugar dust only; no fork tear / spoon dive |
| Matcha variant | Not used | Source default is classic vanilla stack |
| Clarifying questions | None | Source measurements and method are complete for storyboard |

## Reference generation

Six recipe-specific GPT-Image 2 states plus `FinalDishVisual`. All use `conditioningReferences` without character anchors. `FinalDishVisual.prompt` leads with a short dish-only sentence for outro embed.

## Assumptions accepted

- 15-minute egg-white freeze shown as brief timer insert, not real-time.
- Cookie scoop approximated as ~4 cm diameter portions in prompts.
- Berries: halved strawberries + whole blueberries in moderate count.

## Out of scope this run

- No Runway/Suno/API generation.
- No matcha or chocolate-chip variation branches.
