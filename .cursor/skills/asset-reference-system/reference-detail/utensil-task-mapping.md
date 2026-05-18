# Utensil Task Mapping

Use this mapping to avoid near-miss utensil choices.

## Spatula family (do not interchange)

- **`@SiliconeSpatula`** (French *maryse*, rubber/silicone flexible blade): folding batters, scraping the sides of a mixing bowl, stand-mixer bowl, or saucepan; not for sliding under a baked dish to extract a slice.
- **`@TurningSpatula`** (rigid turner / fish spatula): slide under lasagna, gratin, sheet cake, fish, etc.; lift a portion while supporting it from below.
- **`@OffsetSpatula`** (offset pastry spatula / cranked blade): pastry transfer — under tart shells, cookies, or layered entremets; delicate lifts, often two spatulas for tall items.

Legacy alias `@Spatula` still resolves to the same library row as `@SiliconeSpatula`; **prefer `@SiliconeSpatula` in new prompts** so the model does not pick it for “lift a slice” actions.

## Deep-fry retrieval

- preferred: `@SpiderSkimmer`
- acceptable fallback: `@Tongs` (only if scene remains simple)
- avoid: `@SiliconeSpatula` (or `@Spatula`) for lifting from hot oil

## Gentle transfer to plate

- preferred: `@Spoon` or `@Tongs` depending on food structure
- for a firm slice from a baking dish: `@TurningSpatula`, not `@SiliconeSpatula`
- avoid cloth-in-hand transfer prompts (high hand/cloth fusion risk)

## Batter / mixture handling

- `@Whisk` for emulsifying and mixing liquids
- `@SiliconeSpatula` for folding and scraping bowls (not deep-fry lifting, not rigid portion lifting from a dish)

## Hot handling policy

- If food is too hot, use utensil-first actions.
- If bare-hand placement is required for aesthetics, stage it as post-cooling.
- Do not introduce towel wrapped around hand while handling hero food in close-up.
