# Paris-Brest Example

This example captures the modern Recipe2Video workflow:

- logical scenes for editorial quality;
- Seedance 2 References segments for generation;
- recipe-specific state references for fragile pastry geometry;
- Suno prompt separated from video generation.

The historical text-to-image then image-to-video workflow is intentionally not included as a production path.

Key lesson: the Paris-Brest crown is a non-standard repeated structure. Seedance should not invent its topology from text alone. Use state references such as:

- `@RawChouxCrownFrame`
- `@BakedChouxCrownFrame`
- `@PralineCreamFrame`
- `@FilledCrownFrame`
- `@FinishedParisBrestFrame`
