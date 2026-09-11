# PolyOne Studio — Free Pack - Tree (local import trial)

Source: https://www.fab.com/listings/97b20cea-a7e6-4104-a884-0ece175b707d

User-provided files: `free_pack_tree.zip` and `texture_basecolor_v02.zip`.
Neither supplied ZIP contains a license file. No license is inferred from the
word "free"; retain/verify the acquisition terms before public distribution.
Original downloads are preserved outside `public/`, under `assets/source/`.

## Runtime layout

- `models/free-trees.glb`: eight independent, ground-centred meshes in metres.
  The replacement manifest's `modelNode` selects exactly one tree from the pack.
- `textures/basecolor.png`: unchanged shared 4096×4096 atlas. The separately
  uploaded texture has identical pixels, so it is not duplicated at runtime.
- `asset-audit.json`: per-tree triangles, dimensions, source hashes and pivots.

| Tree | Triangles | Height (m) |
| --- | ---: | ---: |
| 01 | 736 | 6.807 |
| 02 | 740 | 10.228 |
| 03 | 749 | 4.546 |
| 04 | 716 | 12.275 |
| 05 | 1,212 | 8.045 |
| 06 | 1,365 | 9.412 |
| 07 | 742 | 8.106 |
| 08 | 993 | 2.941 |

One opaque mesh/material per tree. The pack loads once, and all eight runtime
definitions share the same texture object. Small material states are cloned
per selected part so different tree heights/wind weights do not overwrite
one another's WebGL uniforms. Snow uses the existing separate mesh-shaped
receiver and is an additional draw/geometry pass.

These are additive catalog entries (`POLYONE_FREE_TREE_01` … `08`) in the
conifer category. They have wind, snow and trunk-sized editor collision.
This pass does not alter forest generation, introduce LODs, or certify the
gameplay chopping/burning/regrowth path for these editor-placed assets.

Rebuild from preserved sources: `npm run assets:import-polyone-trees`.
The importer corrects centimetres to metres, centres each trunk's bottom ring
and flips UV V for glTF; it does not change the source atlas or triangle count.

Browser verification: `npx playwright test tests/polyone-trees.spec.ts`.
Screenshots: `local/previews/polyone-trees-dry.png` and
`local/previews/polyone-trees-snow.png`. The isolated 800-tree check uses eight
base-mesh draw calls; this excludes snow/shadow passes and is not a game FPS claim.
