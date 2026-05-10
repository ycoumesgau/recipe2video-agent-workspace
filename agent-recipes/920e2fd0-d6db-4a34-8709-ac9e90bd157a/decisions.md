# Decisions — Chicken Enchiladas (920e2fd0-d6db-4a34-8709-ac9e90bd157a)

## Source fidelity

The primary URL documents the casserole-style Tex-Mex chicken enchiladas. The sibling **homemade red enchilada sauce** recipe on Gimme Some Oven was consulted for concrete roux, spice bloom, simmer, and salt beats so the ingest could treat sauce as first-class cinematography rather than implying canned gloss.

## Production defaults baked into planning assumptions

Defaults provided at ingest (`asmr_food`, `seedance2`, GPT Image 2 for fragile reference stills only, Cursor agent metadata) shaped emphasis on tactile ASMR, References mode segmentation, and explicit planned food-state placeholders where Seedance historically misreads layers, strata steam, casserole lattice spacing, cheese blister fields, or roll geometry.

## Editorial locks until clarifications land

Accepted staging defaults with explicit trade-offs documented so execution can proceed without blocking:

1. **Tortillas:** Flour tortillas assumed for roll ergonomics consistent with recipe primary text because corn tortillas would require supplemental flash-fry or warm-sauce-dip choreography and different brittle-risk notes (`clarifyingQuestions.tortilla-choice`).
2. **Cheese read:** Interpreted melting layer as broadly “Mexican blend” shredded stock with Pepper Jack tolerated as tonal variant if production wants bolder stretch sparks (`cheese-brand` question logged).
3. **Hero plating:** Planned garnish-forward closing tableau while keeping intermittent cheese readability; final garnish intensity still awaits explicit hero preference (`toppings-hero`).

## Structural choices

Opening privileges **enchilada sauce physics** rather than refrigerated ingredient vignettes because it delivers immediate chromatic payoff and distinguishes this dish from supermarket shortcut visuals. Scene-two obligation is discharged by blond roux-to-spice cohesion clarifying scene-one heat precursor.

Roughly **sixty-seven percent logical scenes classify as macro detail beats** counting toward TikTok-detail bias; casserole grid and platter reveals supply controlled context breathers.

Eight Seedance segments map overlapping arcs to conserve reference budget (`<=9` per segment) while still isolating bake blister risk, lift stretch ASMR, and Licorn closure satisfaction.

## Reference plan contract repair (general stage)

Recipe2Video rejected the first `reference-plan.json` ingest because it diverged from the **production enum** demonstrated in `examples/paris-brest/reference-plan.json`. Corrections applied:

- Bundled Licorn PNG anchors now use `source: "existing_asset"` plus `status: "planned"` (replacing the non-contract `agent_reference_plan` / `ready_png` pairing).
- Planned GPT Image stills use `type: "recipe_state"` with `source: "generated_reference_needed"` (replacing `food_state` and the incorrect `agent_reference_plan` source).
- Licorn pose PNGs remain listed with `type: "character"` alongside `CharacterSheet` / `CharacterExpressions`, matching the bundled character library rather than inventing a `character_pose` discriminator the validator does not expose in the Paris example.
- `recipe_state.prompt` fields were rewritten as imperative “Generate …” briefs to mirror the Paris-Brest metadata style the app expects prior to reference generation.

## Checkpoint manifests and Git ancestry

Git history uses two pushes: ingest commit **`00ef39a` houses every creative JSON/Markdown payload**, then **`e206b4a`** appends checkpoint manifest bookkeeping so `checkpoint-manifest.commitSha` currently references **`00ef39a`**. Operational sync should still read manifests from the tracked branch HEAD so GitHub ingestion picks up the manifest update while using the pinned hash when a reproducible artifact snapshot identifier is explicitly required elsewhere in Recipe2Video.

## Known gaps deferred to GPT reference pack

Controlled cross-section reveal, casserole lattice uniformity, blister density, garnished tableau palette, and cross-shot cheese tether physics require GPT stills enumerated in `reference-plan.json` before final Seedance lock.
