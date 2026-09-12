# Replaceable winter torch

`held-winter-torch-01.glb` and `wall-winter-torch-01.glb` derive from the
user-supplied `assets/source/props/wooden-club/wooden-club-original.glb`. The source geometry and
texture are retained; this import does not claim a new third-party license.
The user plans to replace the source with a lower-poly model later.

Build script: `tools/prepare-winter-torch.mjs`. Stable asset bank IDs:
`SURVIVAL_HELD_TORCH_01`, `SURVIVAL_BUILD_WALL_TORCH_01`.
The wall bracket is project-authored geometry. The held wick attachment node
(no visible mesh) is named `survival-held-torch-fire-anchor`; the mounted wick matches the catalog
fire anchor `(0, .62, .27)`. Replacing art must preserve these attachment points.
Flame presentation starts 14 cm below the wick tip to cover the cloth, while
smoke and ignition still use the actual tip. The hand grip is 15 cm above the
shaft origin; the carried shaft is upright, not in the generic bundle lean.
