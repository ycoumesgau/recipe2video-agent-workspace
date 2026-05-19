# Character 2D Guardrails

The Licorn mascot is a **flat 2D illustrated character**, not a 3D model.

## What the library provides

All character inputs under `assets/character/` are **2D reference stills** (PNG) or one **2D motion reference** (`LicornOutroVideo.mp4`):

- `@CharacterSheet` — identity, proportions, line weight, colors
- `@CharacterExpressions` — expression variants on the same flat style
- `@PoseFront`, `@PoseTopDown`, `@PoseThreeQuarterLeft`, `@PoseThreeQuarterRight` — pre-drawn **2D views** of the same character (not a 3D rig or camera orbit)

`PoseThreeQuarter*` names describe **illustration angle**, not a 3D turn-table. Seedance must match the flat art in the attached stills.

## Seedance segments that show the character

Whenever `@CharacterSheet`, a pose, or `@CharacterExpressions` is attached:

1. State each character reference role as **2D illustrated identity / pose / hands** (never "3D model", "CGI character", or "realistic mascot render").
2. Add a **character style lock** in the prompt body, for example:
   - `Character style lock: flat 2D illustrated Licorn mascot exactly matching @CharacterSheet and pose references; same line weight and colors; not a 3D model.`
3. Add to **global negatives** when the character is visible:
   - `no 3D character, no CGI mascot, no clay or plastic figurine, no realistic 3D render, no volumetric lighting on the character`

Hands-only segments may use `@CharacterSheet` + `@PoseTopDown` (or another pose) with the same 2D lock; do not ask for "realistic human hands" that override the illustrated style.

## Outro

`@CharacterSheet` locks **2D identity** alongside `@LicornOutroVideo` (2D celebration motion). The app injects the canonical outro prompt; agents still declare reference roles that imply 2D art, not 3D.

## Recipe-specific reference images (GPT-Image 2)

Do **not** pass character anchors in `conditioningReferences` (app drops them). Dish-state images must never invent a 3D mascot in the frame — kitchen anchors only.

## Forbidden prompt language

Avoid wording that invites 3D reinterpretation:

- "3D mascot", "CGI unicorn", "Pixar-style character", "clay figure", "vinyl toy", "Unreal render"
- "orbit camera around the character", "360° character", "depth-mapped character"
- "make the character more realistic" (for the mascot body — food realism is separate)

Food and kitchen may be photorealistic; the **Licorn character must stay flat 2D** whenever it appears.
