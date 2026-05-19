# Recipe2Video Agent Artifact Contract

Recipe2Video reads files from `agent-recipes/{videoId}/`, validates them, and syncs valid artifacts into Supabase.

All JSON files must be strict JSON. No comments. No Markdown fences.

## `recipe-analysis.json`

```json
{
  "recipe": {
    "title": "Paris-Brest",
    "sourceType": "text",
    "sourceUrl": null,
    "ingredients": [{ "name": "hazelnuts", "quantity": null, "note": null }],
    "steps": [
      {
        "position": 1,
        "text": "Make praline",
        "timing": null,
        "visualCue": "amber caramel and hazelnut shards",
        "block": "praline",
        "textureCue": "brittle caramel to glossy praline ribbon",
        "runwayRisk": "rolling pin motion ambiguity"
      }
    ],
    "subRecipes": ["praline", "crumble", "choux", "cream", "assembly"],
    "assumptions": [],
    "timing": null,
    "criticalTransformations": [],
    "visualTextureOpportunities": [],
    "possibleHooks": [],
    "promptPolicySources": []
  },
  "clarifyingQuestions": [
    {
      "id": "dish-geometry",
      "question": "Does the final dish have a specific shape that must be preserved?",
      "reason": "Non-standard geometry changes reference planning."
    }
  ]
}
```

## `logical-scenes.json`

```json
{
  "logicalScenes": [
    {
      "id": "scene-01",
      "videoId": "video-id",
      "segmentId": null,
      "position": 1,
      "sceneType": "detail",
      "arc": "praline hook",
      "description": "Amber caramel starts pouring onto the baking mat.",
      "bg": "island_overhead",
      "zoom": "extreme macro",
      "durationTarget": 1.2,
      "note": "Texture-first opening.",
      "textureCue": "glossy amber caramel",
      "sfxCue": "thick caramel pour",
      "satisfactionBeat": true,
      "runwaySafeScore": {
        "stillImageReadable": true,
        "singleMainMotion": true,
        "dominantSound": true,
        "visuallyDesirable": true,
        "textureContrast": true,
        "notes": []
      }
    }
  ]
}
```

The app requires 30-48 logical scenes.

Scale guidance for `logical-scenes.json`:

- use `description` and `note` to lock risky proportions when needed;
- prefer explicit ranges (`3-4 cm balls`) over vague labels (`small`);
- if scale is uncertain, push a clarifying question in `recipe-analysis.json`.

## `seedance-segments.json`

```json
{
  "seedanceSegments": [
    {
      "id": "segment-01",
      "videoId": "video-id",
      "position": 1,
      "title": "Hook praline",
      "arc": "praline hook",
      "mode": "References",
      "logicalSceneIds": ["scene-01", "scene-02"],
      "description": "Caramel pour, crack, blender, praline ribbon.",
      "prompt": "Use @KitchenIslandDefault for global kitchen identity...",
      "promptInitial": "Use @KitchenIslandDefault for global kitchen identity...",
      "references": [
        {
          "role": "global Licorn kitchen environment",
          "name": "KitchenIslandDefault",
          "label": "KitchenIslandDefault",
          "runwayUri": null,
          "mediaAssetId": null,
          "required": true
        }
      ],
      "beats": ["caramel pour", "brittle crack"],
      "timing": ["0.0-0.7s: caramel pour"],
      "continuity": "Opening segment.",
      "risk": "Rolling pin motion can be misread.",
      "audioPrompt": "hot caramel pour; brittle crack",
      "negatives": ["no text", "no music"],
      "qaChecklist": {
        "referencesWithinLimit": true,
        "globalKitchenReferencePresent": true,
        "referenceRolesExplicit": true,
        "promptWithinPracticalLimit": true,
        "hardCutsSpecified": true,
        "mandatoryTimingSpecified": true,
        "noSpeechVoiceoverOrMusic": true,
        "fragileFoodPhysicsHandled": true,
        "nonStandardGeometryHandled": true,
        "sourcePoliciesApplied": []
      },
      "durationTarget": 5,
      "status": "ready"
    }
  ]
}
```

The app requires 5-10 Seedance segments.

Scale guidance for `seedance-segments.json`:

- put size/proportion continuity in `continuity`;
- put potential size drift in `risk`;
- include scale lock lines in `prompt` and `promptInitial` for ambiguous objects.

## `reference-plan.json`

```json
{
  "references": [
    {
      "type": "kitchen",
      "canonicalName": "KitchenIslandDefault",
      "role": "global kitchen identity",
      "priority": 1,
      "source": "agent_reference_plan",
      "prompt": "Use only to preserve kitchen surfaces, lighting, and island context.",
      "runwayUri": null,
      "mediaAssetId": null,
      "usedInSegmentIds": ["segment-01"],
      "status": "planned"
    }
  ]
}
```

References are Seedance inputs. They must be planned before video generation.

## Outro Segment Contract

The last segment of `seedance-segments.json` (highest `position`) is the
standardized Licorn celebration outro. It MUST satisfy:

- `arc: "licorn_celebration_outro"`;
- `durationTarget: 5` (Seedance 2 minimum, hard requirement);
- `mode: "References"`;
- `logicalSceneIds`: at least one placeholder id (e.g. `["scene-outro"]`). No matching row in `logical-scenes.json` is required, but an empty array fails sync validation;
- `prompt: "<APP_OVERRIDE>"` and `promptInitial: "<APP_OVERRIDE>"` — Recipe2Video rewrites both at sync time with the canonical outro template; any other value is rejected;
- references in this exact order:
  1. `KitchenLayoutContextWide` (kind: image)
  2. `KitchenIslandDefault` (kind: image)
  3. `LicornOutroVideo` (kind: video, library asset)
  4. `CharacterSheet` (kind: image, 2D illustrated identity lock — not a 3D model)
  5. `FinalDishVisual` (kind: image, recipe-specific entry in `reference-plan.json`).

### `FinalDishVisual.prompt` (dual use)

The `prompt` on the recipe-specific `FinalDishVisual` entry is used both for GPT-Image 2 reference generation and as the dish identity clause injected into the canonical outro at sync time.

- **Outro embed:** one short dish-only sentence, **≤ 280 characters**, neutral, no character, no action, no image-generation boilerplate ("Generate one vertical-reference still…"). Example: `a shallow hero bowl of lemon butter orecchiette with torn burrata, pistachio crunch and basil, intact on the countertop`.
- **Image generation:** you may add kitchen or GPT-Image detail after that lead sentence, or in separate recipe_state entries; declare `conditioningReferences` per `contracts/reference-image-generation.md`.

Recipe2Video can derive a short clause from a long GPT-Image prompt, but leading with the compact sentence is the reliable contract.

The segment immediately before the outro (position N-1) MUST end with
the dish in its final visible state, intact and motionless. Destructive
food-porn beats belong in segments 1..N-2.

Full rules: `.cursor/rules/seedance-outro.mdc`.

## `suno-prompt.json`

Strict JSON. Required: `schemaVersion` (must be `1`), `status`, `fields`, `instructions`, `qualityChecks`.

- **`fields.autoLyricsPrompt`**: agent **baseline** only — opening `Write original English song lyrics`, no `2-3 minutes` duration in the opener, lyric style ends with `Keep the chorus reusable for a 45-90 second video edit.` (no `but make a 2-3 minutes song`), scaffold header `Structure:`.
- **`fields.styleOfMusic`**: genre / production / mix only — **no** `2-3 minutes song.` suffix in committed artifacts.
- **`instructions.fullSongOperatorEdits`**: required object documenting what the operator adds in Suno before full generation (three lyrics replacements + `styleOfMusicSuffix: "2-3 minutes song."`).

Full Suno policy, worked example, and operator table: **`contracts/suno-music.md`**.

## Markdown Artifacts

- `decisions.md`: user decisions, assumptions, and accepted trade-offs.
- `suno-prompt.md`: copy-ready Suno fields (five parsed sections) plus operator context (`Status`, `Intent`, **Operator full song (manual)**).
- `changelog.md`: concise record of artifact changes and why.
