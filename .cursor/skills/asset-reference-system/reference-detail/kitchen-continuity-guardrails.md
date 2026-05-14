# Kitchen Continuity Guardrails

Use this checklist whenever Seedance segments may drift on kitchen identity.

## Always-on kitchen anchor pack

Each segment should include:

1. `@KitchenLayoutContextWide` — structural context of the full kitchen layout.
2. one shot-specific kitchen view (`@KitchenIslandDefault`, `@KitchenIslandOverhead`, `@InductionWide`, `@OvenWide`, etc.).

`@KitchenIslandDefault` is not mandatory on every segment; use it when it matches the active shot or when explicit terrazzo lock is needed.

## Non-negotiable invariants

- countertop remains the same light terrazzo surface across segments;
- induction remains the same black flush plate geometry;
- cabinet style and relative layout remain consistent;
- no invented alternate kitchen style unless explicitly requested.

## Prompt phrasing pattern

`Kitchen continuity: keep the same Licorn kitchen layout and materials as references. Countertop stays light terrazzo, induction stays the same flush black plate.`

## Anti-drift negatives

- `do not switch to wood countertop`
- `do not invent a new stovetop design`
- `do not redesign the kitchen layout`

## Important

`@KitchenLayoutContextWide` is a context lock, not a camera order. Keep shot framing driven by the storyboard.
