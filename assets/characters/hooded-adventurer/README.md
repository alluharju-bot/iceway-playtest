# Hooded adventurer candidate

Source candidate extracted from the imported Tripo model and Mixamo farming
animation pack on 2026-08-24.

- Model: one skinned mesh, one material, 9,499 triangles, 33 Mixamo bones.
- Texture: 512 × 512 base-colour atlas; the rigged FBX also embeds its source.
- Animation library: 32 usable motion-only FBX clips, all targeting the same
  28 animated bones on the model's 33-bone skeleton.
- Runtime movement: X/Z root translation must be locked. Vertical hips motion
  stays available for jumping, kneeling and tool actions.
- Axis handling: the model bind pose is Z-up but the animation poses are Y-up.
  The runtime library samples `WALK_STANDARD` as an upright initial pose; rotating
  the whole model would put every actual animation on its back.
- Streaming: load locomotion first and contextual farming/prop clips on demand.
- Quarantine: `cow-milking-loader-incompatible.fbx` needs a Blender re-export.
- Missing source: request a relaxed, hands-free idle before the character is
  considered final. A frozen normal-walk frame is only a temporary pose.
- `CARRY_WALK` is the source file originally named `Walking.fbx`. Its hands are
  held around a large object, so it must only run during physical item carry.
- `DEEP_SNOW_RUN` comes from `Dribble.fbx`; normal `RUN` remains the shallow-
  snow run. `TWO_HAND_IDLE` and `HEAVY_TOOL_SWING` are shared tool poses for
  axes, mining tools, ice breaking and future post-driving interactions.

Stable semantic ids live in
`src/characters/HoodedAdventurerAnimationCatalog.ts`. Ambiguous source suffixes
such as `(2)` intentionally became A/B until an in-engine prop-contact review
identifies their exact role.
