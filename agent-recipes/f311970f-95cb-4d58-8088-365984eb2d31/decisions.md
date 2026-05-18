# Decisions — `f311970f-95cb-4d58-8088-365984eb2d31`

## Production defaults locked for Recipe2Video

- **Creative style preset:** `asmr_food`.
- **Video generation model:** `seedance2`, References workflow, implicit `1080:1920` vertical unless assembly overrides explicitly.
- **Reference image authoring model (offline elsewhere):** `gpt_image_2` for quadrant + cross-section guardians listed in `reference-plan.json`.
- **Speech stack (outside this workspace execution):** `eleven_multilingual_v2`.
- **SFX stack (outside):** `eleven_text_to_sound_v2`.
- **Cursor authoring model note:** Composer family with fast-mode preference per ingest ticket (no runtime coupling here).

## Editorial interpretation of the recipe URL

- Primary on-camera narrative follows the authored **Crunchwrap Supreme quadrant map** surfaced in the canonical ingredients card on [iamafoodblog.com/tiktok-wrap-hack](https://iamafoodblog.com/tiktok-wrap-hack/).
- Alternate blog tangents (**sushi nori edition**, freestyle pizza/breakfast musings) are explicitly excluded from visuals and Seedance negatives to constrain drift.
- **Serves-six** informs prop depth (blur-second wedge) but hero scale remains singular wedge focus for clarity.

## Accepted technical trade-offs

- Quadrant chirality (which rim receives the hinge cut) can vary between cooks; we stage the radial cut toward the **bottom-of-frame rim** for consistent fold readability, pending operator confirmation in `recipe-analysis.json` clarifying questions.
- Skillet finish condenses the blog’s “3–4 minutes per side” real timeline into **condensed cinematic beats** while preserving texture language (leopard blister, cheese ooze) without on-screen numeric timers.
- Generated recipe-state PNGs are **mandatory risk mitigators** for hinge geometry, quadrant colorblocking, grilled skin, and cross-section strata; live-only prompting proved too unstable in prior Licorn projects.

## Outstanding clarifications (tracked in `recipe-analysis.json`)

- Flour vs corn tortilla hero selection.
- Exact board orientation vs blog diagram for quadrant-to-filling mapping confirmation.

## Policy compliance

- No Runway, Suno, Supabase, Mux, Remotion, or other paid generation executed inside this planning repository; operators run those services downstream in Recipe2Video.

## Checkpoint manifest semantics

- `checkpoint-manifest.json` records `checkpointCommitSha` as **`4330e2ba7596412e582a4cdfe4e1029df89bba86`**, the revision that contains the full Recipe2Video JSON/Markdown artifact bundle. Later housekeeping commits only adjust tracking metadata; Recipe2Video ingestion should treat that SHA as the canonical recipe snapshot while still merging the latest branch head for incidental doc tweaks.
