# Decisions — Bibimbap coréen

## Source status

- Primary source: https://www.atelierdeschefs.fr/recettes/13601/bibimbap-coreen/
- Direct fetch of the slash-final URL timed out and then returned a Vercel 429 checkpoint.
- A specialized recipe research pass extracted the source content from the URL without the trailing slash.
- The extracted recipe is sufficient to produce the complete Recipe2Video planning artifact set, with the caveats below.

## Culinary assumptions

- The source displays `Rumsteck 2 g`, which is not plausible for 6 servings. Planning keeps the source value visible in `recipe-analysis.json` but treats it as an anomaly. Visual prompts avoid exact text quantities and lock the beef visually as thin strips, 0.5-1 cm wide and 4-6 cm long.
- The recipe says to place an egg in the center but does not specify the egg cooking method. Planning uses a fried egg with set white and intact runny yolk because it is a strong bibimbap visual hook and a clear ASMR payoff.
- The source names `sauce piment chili`, not gochujang. Prompts call it chili-sesame sauce and explicitly avoid forcing gochujang unless the user confirms.
- The final video uses one hero bowl rather than six bowls. The six-serving recipe context remains implicit.

## Geometry and scale locks

- Hero bowl: 16-18 cm diameter.
- Bowl topology: rice base with 5-6 distinct topping zones, one central normal-sized fried egg, and controlled sauce quantity.
- Sauce: about one tablespoon per bowl, never flooding the radial arrangement.
- Beef: thin strips, not minced, not steak chunks.
- Carrot: fine julienne, not rounds.
- Vegetables stay separated until assembly; only one spoon-sized area is mixed in the final payoff.

## Story and pacing decisions

- The opening is texture-first: the finished yolk breaks immediately, then the bowl geometry is clarified in scene 2 before the edit jumps back to preparation.
- Utility steps are compressed; visual time goes to rice steam, marinade gloss, beef sizzle, sesame, sauce, yolk, and final spoon lift.
- The storyboard uses 36 logical scenes and 8 Seedance segments, matching the required 30-48 scene and 5-10 segment ranges.
- The ending keeps the finished bowl as the hero while the Licorn character appears satisfied in the stable kitchen context.

## Reference strategy

- Every Seedance segment uses `@KitchenLayoutContextWide` plus one shot-specific kitchen view.
- Recipe-specific state references are planned for final bowl topology, fried egg/yolk break, marinated beef strips, seared beef strips, separated vegetables, and steamed rice.
- Existing assets are used for kitchen, character, poses, and utensils; no paid generation is launched from this workspace.

## Open clarifications

- Confirm the real rumsteck quantity behind the source's `2 g` display.
- Confirm fried egg with runny yolk versus another egg presentation.
- Confirm whether the chili sauce should be treated as gochujang.
- Confirm one hero bowl versus showing six portions.
