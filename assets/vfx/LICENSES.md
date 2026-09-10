# Runtime VFX sources

## Particle fire

- Atlas and layout/lifetime equations: https://github.com/yomotsu/three-particle-fire
- Copyright (c) 2017 @yomotsu. MIT.
- The atlas is embedded in `src/survival/vfx/ParticleFireSprite.ts`.
- Full notice: `three-particle-fire.LICENSE.txt` (also shipped in the build)
  and `src/survival/vfx/THREE_PARTICLE_FIRE_LICENSE.md`.
- ICEWAY adapts the effect with a blue/orange/yellow height gradient, local
  wind, perspective/orthographic sizing, density LOD and glow blending that
  preserves colour over snow. The shared distant flame cards remain the LOD
  and loading fallback. Smoke, light budgets and combustion are independent.

## Volumetric campfire density

- `fire-volumetric-density.png` is the grayscale density texture distributed
  with `@wolffo/three-fire` / THREE.Fire.
- Source: https://github.com/typeWolffo/THREE.Fire
- License: MIT
- Copyright (c) 2015 typeWolffo

Retained as a reference asset. The survival presenter now uses particle fire,
not the `@wolffo/three-fire` ray-marching shader.
