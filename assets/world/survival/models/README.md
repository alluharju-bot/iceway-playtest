# Replaceable winter torch

`held-winter-torch-01.glb` and `wall-winter-torch-01.glb` derive from the
user-supplied `public/assets/wooden+club+3d+model.glb`. The source geometry and
texture are retained; this import does not claim a new third-party license.
The user plans to replace the source with a lower-poly model later.

Build script: `tools/prepare-winter-torch.mjs`. Stable asset bank IDs:
`SURVIVAL_HELD_TORCH_01`, `SURVIVAL_BUILD_WALL_TORCH_01`.
Added wick and wall bracket are project-authored geometry. The held wick mesh
is named `survival-held-torch-fire-anchor`; the mounted wick matches the catalog
fire anchor `(0, .62, .27)`. Replacing art must preserve these attachment points.
