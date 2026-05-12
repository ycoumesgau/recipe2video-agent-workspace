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

## Markdown Artifacts

- `decisions.md`: user decisions, assumptions, and accepted trade-offs.
- `suno-prompt.md`: copy-ready Suno fields.
- `changelog.md`: concise record of artifact changes and why.
