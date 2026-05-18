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
- After pulling `main`, the updated asset skill distinguishes the spatula family. Segment 04 now uses `@SiliconeSpatula` only for flexible pan tossing/scraping and keeps `@Tongs` for hot food movement; rigid portion lifting remains out of scope.
- The updated scene verification pass added visible hand references to vegetable and egg/sauce action segments, moved `@RiceSteamFrame` to the rice-steam segment, and added `@TurningSpatula` for supported fried egg transfer into the bowl.
- Scene 06, scene 25, and scene 29 are now context/re-anchor scenes to bring the storyboard closer to the 20-25% context target without changing the established culinary sequence.

## Où étudier l'analyse et la génération des artefacts

- `recipe-analysis.json` est le point d'entrée pour l'analyse culinaire: source, ingrédients, étapes, timings, transformations critiques, opportunités texture, hooks, hypothèses et questions clarifiantes.
- `decisions.md` explique les choix faits à partir de cette analyse: corrections prudentes, hypothèses, échelle, géométrie, rythme, stratégie de références et limites non résolues.
- `logical-scenes.json` montre comment l'analyse est traduite en 36 scènes éditoriales: progression, cadrages, cues texture/SFX et risques de génération.
- `seedance-segments.json` montre la génération vidéo prévue: 8 segments Seedance 2 References, prompts anglais, timings obligatoires, références, continuités, risques, négatifs et checklist QA.
- `reference-plan.json` liste les références utilisées ou à générer: assets existants de cuisine/personnage/ustensiles et références d'états recette nécessaires.
- `suno-prompt.json` et `suno-prompt.md` couvrent uniquement le brief musical manuel Suno; les prompts vidéo Seedance restent sans musique.
- `changelog.md` retrace ce qui a été produit et pourquoi, utile pour auditer l'évolution du checkpoint.
- `checkpoint-manifest.json` est le résumé machine du checkpoint: branche, SHA poussé, artefacts attendus et état de validation.

## Open clarifications

- Confirm the real rumsteck quantity behind the source's `2 g` display.
- Confirm fried egg with runny yolk versus another egg presentation.
- Confirm whether the chili sauce should be treated as gochujang.
- Confirm one hero bowl versus showing six portions.
