# ICEWAY world prop catalog

`procedural-world-assets.json` is the saved, expanded representation of every
code-generated prototype prop. Regenerate it with
`npm run world:export-procedural-assets` after changing the TypeScript source
catalog.

Every placed prop stores a stable catalog `id`, never a generated mesh name.
This allows a procedural placeholder to be replaced without rebuilding the
map.

## Replacing a placeholder with a SketchUp model

1. Export the SketchUp asset as GLB. Keep its origin at ground level and use
   metres.
2. Put it below `public/assets/world/props/models/`.
3. Add an entry to `world-asset-overrides.json`:

```json
{
  "id": "CONIFER_SPRUCE_01",
  "modelUrl": "assets/world/props/models/my-spruce.glb",
  "scale": 1,
  "rotationYDegrees": 0,
  "xOffset": 0,
  "yOffset": 0,
  "zOffset": 0,
  "windWeight": 0
}
```

`xOffset`, `yOffset` and `zOffset` are optional final asset-local metre
corrections for exports whose origin is not at the intended placement pivot.
`windWeight` is optional (`0..1`) and lets a combined foliage or cloth mesh
participate in forecast wind even when its exported mesh name carries no
semantic `leaf`, `branch`, `flag` or `cloth` hint.

The runtime loads and instances the GLB mesh parts under the same catalog ID.
All existing placements, transforms, smart connections and collision settings
remain intact. Keep the entry absent while using the procedural fallback.
