# Borealis prototype coast source

These aligned PNG files are loaded directly by the current browser prototype.
They are intentionally small and local to Borealis; the full-world compiled
raster dataset remains a separate later integration.

## Shared layout

- size: `384 x 256 px`
- scale: `0.5 m / px`
- local X: `-128 ... 64 m`, increasing right/east
- local Z: `-64 ... 64 m`, increasing down/south
- never resize or offset only one layer
- use lossless PNG with opaque pixels

`terrain.png` uses exact colors:

- water: `#104568`
- shore: `#7bbcb6`
- land: `#4d7668`

Paint a continuous mainland connected to the left/west edge. Shore counts as
drivable land and its easternmost pixel becomes the physical coastline. Hard
pixel brushes are correct; the runtime interpolates the derived contour along
Z so the rendered shore does not become a staircase.

`bathymetry.png` is opaque grayscale:

- black: land or extremely shallow water
- dark gray: shallow, sheltered coastal water
- light gray: deeper water
- white: maximum normalized prototype depth

The game uses this layer for water color and wave exposure. Painting darker
water along a beach makes the sea lighter and calmer there. Keep intentional
harbor channels lighter than the surrounding shelf.

`npm run world:borealis-coast` regenerates the starter maps and overwrites
these PNGs. Use it only when resetting the prototype source, not after manual
painting.

Future aligned layers can add `surface-material.png` for road, grass, sand,
rock and soil under the deformable snow. Sea-resource placement belongs in the
full-world `resources.png`, where a Cozium field can validate resource-platform
and drill construction sites without hardcoded coordinates.
