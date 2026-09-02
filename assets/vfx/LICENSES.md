# Runtime VFX sources

## Volumetric campfire density

- `fire-volumetric-density.png` is the grayscale density texture distributed
  with `@wolffo/three-fire` / THREE.Fire.
- Source: https://github.com/typeWolffo/THREE.Fire
- License: MIT
- Copyright (c) 2015 typeWolffo

The runtime uses the modern vanilla GLSL implementation through the published
`@wolffo/three-fire` package. ICEWAY limits it to the two nearest campfires at
12 ray-march iterations and two noise octaves; pooled billboard fire remains
the low-cost fallback for distant fires and texture-load failure.
