# Reference Image Generation Policy

Reference image generation is allowed and important, but only for Seedance reference planning.

## Allowed Uses

Generate or request images for states Seedance is likely to misread:

- raw state;
- baked state;
- filled state;
- cut state;
- glazed state;
- broken or brittle state;
- final hero state;
- non-standard topology.

Examples:

- `RawChouxCrownFrame`
- `BakedChouxCrownFrame`
- `FilledCrownFrame`
- `FinishedParisBrestFrame`

## Not Allowed

Do not revive the old production path where every micro-scene first gets an image and then image-to-video.

Do not create first/last frames for Kling-style interpolation.

Do not create image prompts for every logical scene unless the image is explicitly needed as a reusable Seedance reference.

## Required Metadata

Every generated reference plan entry should specify:

- `canonicalName`
- `type`
- `role`
- `priority`
- `source: "generated_reference_needed"`
- `prompt`
- `usedInSegmentIds`
- `status: "planned"`

The Recipe2Video app will create, store, approve, and upload these references before video generation.
