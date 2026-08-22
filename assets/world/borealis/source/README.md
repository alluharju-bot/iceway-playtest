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

`elevation.png` is opaque grayscale and aligned to the same pixels. Black is
the current ground terrace and white is 64 metres above it. The runtime
interpolates the raster before adding sparse in-game editor deltas.

`surface-material.png` uses exact opaque colors:

- tundra: `#4d7668`
- rock: `#707875`
- dirt: `#735237`
- road: `#343a3c`
- raised sidewalk: `#737b7e`
- snow exclusion / heated surface: `#e17632`

The in-game world editor saves its changes separately, so these authored PNGs
remain reusable source maps. Export the editor JSON patch before resetting a
browser save.

`npm run world:borealis-coast` regenerates the starter maps and overwrites
these PNGs. Use it only when resetting the prototype source, not after manual
painting.

Future aligned layers can add finer biome and resource data. Sea-resource
placement belongs in the full-world `resources.png`, where a Cozium field can
validate resource-platform and drill construction sites without hardcoded
coordinates.
