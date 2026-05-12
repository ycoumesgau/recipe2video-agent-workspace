---
name: food-physics-reference
description: Add precise culinary physics for texture, color, viscosity, browning, steam, structure, and failure states.
---

# Food Physics Reference

Use whenever a recipe step or prompt needs more physical precision.

## Describe Visible Evidence

Prefer concrete material evidence:

- color;
- surface;
- moisture;
- viscosity;
- density;
- shine;
- steam;
- crispness;
- cracks;
- crumbs;
- flow;
- elasticity.

Avoid generic adjectives alone. Use `smooth glossy cream with soft peaks`, not `beautiful cream`.

## Scale and Proportion Guardrails

When a shape can be misread, always lock scale explicitly:

- give a target size range in real units when possible (`3-4 cm`, `20 cm diameter`, `2 cm thick`);
- anchor object scale to known kitchen references (`relative to a palm`, `fits on one tablespoon`, `smaller than a ladle bowl`);
- name expected count when topology is repetitive (`12 small arancini balls`, `8 choux domes`);
- state what it is not (`not soccer-ball sized`, `not giant single dome`);
- carry the same scale anchor across all related segments in `continuity` and `risk`.

If exact size is unknown, ask a clarifying question before locking prompts.

## Transformation Families

Look for:

- caramelization: amber, glassy, brittle, cracks, shards;
- emulsions/ganaches: glossy, thick, elastic, split risk;
- creams: dense to airy, satin peaks, ribbon, pipeable;
- choux: paste ribbon, puffed shell, cracked crust, hollow interior;
- dough: matte, elastic, laminated, risen, browned;
- glaze: flowing, reflective, set, dripping edge;
- frying/browning: blistered, golden, crisp, oil sheen;
- reductions/syrups: viscosity, thread, nappage, stickiness.

## Failure States To Prevent

When relevant, state what must not happen:

- caramel bends like syrup when it should crack;
- choux becomes a smooth ring instead of separate domes;
- cream becomes liquid or grainy;
- glaze becomes opaque paste;
- floating tools or ingredients appear without visible hands;
- induction shows flame or glow.

## Reference Images

If text cannot reliably preserve geometry, propose a recipe-specific reference image: raw, baked, filled, cut, glazed, broken, or final.

## References

- `quick-reference/scale-and-proportion-guardrails.md`
- `reference-detail/portion-and-scale-examples.md`
- `reference-detail/failure-states.md`
