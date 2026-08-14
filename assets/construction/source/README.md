# Authored construction assets

Export a SketchUp component as Collada (`.dae`) into a module folder here and
copy `../examples/generator-set.construction.json.example` beside it as
`<name>.construction.json`.

Keep the component origin at the intended construction pivot. Name helper
groups consistently:

- `MODEL__LOD0` for visible geometry
- `COLLIDER__<id>` for collision proxies
- `SOCKET__<id>` for every socket in the module catalog
- `ANIM__<id>` for an animated group
- `DECAL__<slot-id>` for a decal anchor

Run `npm run construction:validate`, then
`npm run construction:manifest`. The editor loads the generated manifest and
replaces only the matching procedural fallback. A bad or missing DAE never
removes the fallback.
