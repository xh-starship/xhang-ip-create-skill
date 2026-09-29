# Full-illustration asset-pack contract

Read this reference only after the user has chosen **Full illustration + limited motion** or asks for an equivalent high-fidelity package.

## Delivery shape

Use an explicit version folder such as `full-illustration-v1/`:

```text
<package>/
  README.md
  full-illustration-v1/
    STYLE-LOCK.md
    ASSET-MANIFEST.json
    HYPERFRAMES-执行规范.md
    person/
      base/              # front/side, full/half neutral frames
      actions/           # full illustrated gesture frames
      facial-rig/        # mouth and eye/brow replacement images
    companion/           # optional mascot/animal, same base/actions structure
```

Use `companion/` only when the user has chosen one. The name can be changed to the companion's approved name.

## Minimum person assets

- Front full-body neutral and side full-body neutral
- Front half-body neutral and side half-body neutral
- Full illustrated `point`, `explain`, `think`, and `close/sign-off` frames
- Mouth states: rest/closed, small-open speech, wide-open speech, round-O, and smile
- Eye/brow states: neutral open, blink, happy, and curious/emphasis

For an animal companion, produce at least front/side neutral, point, explain, think, and sign-off. Give it movement cues appropriate to its anatomy, such as ears/tail/tag rather than human arm rotations.

## Prompt invariants

Every generation prompt should state:

- Input image role: identity, style, pose, or supporting reference
- Locked recognition anchors and permanent palette
- Exact intended production model and asset function
- Transparent background/no floor/no text/no watermark constraints
- The rendering detail requirement; avoid “icon”, “flat SVG”, “chibi”, or “simplified mascot” when the approved model is full illustration
- Whether the output is a base frame, an action frame, or a facial replacement layer

Keep base and action images in the same visual family. When a sheet is used to preserve consistency, save both the source sheet and cropped per-action assets; record each in the manifest.

## Animation boundary

Use face replacement and small transforms for micro-performance:

- blink, brow reaction, 1–2% breath, minor head/shoulder tilt
- lip-sync state swaps aligned to audio energy or phoneme timing
- companion tail/ear motion or brief tag light

Use whole illustrated action frames for major changes: pointing, teaching, thinking, waving, sitting, standing, or turning. Crossfade or mask the transition over a few frames; do not stretch/dismember detailed clothing or fur to imitate broad skeletal motion.

## Manifest essentials

The manifest should declare version, default status, production model, asset lists, action meanings, facial state meanings, dimensions where relevant, and source-sheet provenance. It must use paths relative to the version directory.
