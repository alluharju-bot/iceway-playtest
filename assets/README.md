# Runtime assets

Only assets loaded by the browser belong here. Keep stable, lowercase,
URL-safe paths; update the owning catalog whenever moving a runtime file.

| Directory | Contents |
| --- | --- |
| `characters/hooded-adventurer/` | Player model, existing animations and reviewed `animations/action-pass/` clips |
| `characters/mekanos/` | Mekanos skin and its own skeleton/walk |
| `world/props/` | World asset catalog, replacement manifest and project-specific props |
| `world/survival/` | Runtime survival models, including adapted held/wall torches |
| `vendor/` | Third-party runtime models grouped by publisher/pack, with provenance/license notes |
| `construction/` | Construction asset manifest and runtime data |
| `environment/` | Sky and celestial textures |
| `vfx/` | Fire/smoke/effect textures and attribution |
| `audio/`, `music/` | Sound effects and music |
| `models/` | Existing general runtime models |

Original ZIPs, unused authoring files and import-only source models belong in
`assets/source/` at the repository root, outside Vite's public directory.
Do not upload commercial source packages to a public repository just because
their runtime derivatives are used in a game.

## 2026-09-11 organisation

- Moved 17 loose player action FBXs to
  `characters/hooded-adventurer/animations/action-pass/`; updated the semantic
  animation catalog and offline audit. Older animation variants are preserved.
- Moved `Walking kopio.fbx` to `characters/mekanos/model-and-walk.fbx`.
- Moved the original wooden club GLB and dagger ZIP to `assets/source/props/`.
  Adapted runtime torches remain under `world/survival/models/`.
- Preserved both PolyOne ZIPs under `assets/source/`. Their two 4096×4096
  textures have identical decoded pixels, so only the tree pack's atlas is
  used at runtime. The separate texture archive is not a second required map.
- Existing organised asset families and their URLs were left in place.

PolyOne trial trees are available in World Builder → conifers as
`PolyOne · Tree 01` through `PolyOne · Tree 08`. They do not replace existing
forest trees or change saved placements/world generation.
