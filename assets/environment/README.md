# Environment asset sources

## `arctic-overcast-sky-2k.jpg`

- Source: [Snow Field (Pure Sky)](https://polyhaven.com/a/snow_field_puresky)
- Authors: Jarod Guest (sky edit), Sergej Majboroda (original)
- License: [CC0](https://polyhaven.com/license)
- ICEWAY derivative: tonemapped source resized to 2048 x 1024 and JPEG-compressed for the browser playtest.

The source is a pure-sky equirectangular panorama. ICEWAY uses it only as a
visual backdrop; the game's existing environment simulation still controls
sun direction, day/night tint, fog, visibility, weather and world lighting.

## Additional sky-story panoramas

- `snowy-field-2k.jpg`: [Snowy Field](https://polyhaven.com/a/snowy_field)
- `evening-field-2k.jpg`: [Evening Field](https://polyhaven.com/a/evening_field)
- `rural-winter-roadside-2k.jpg`: [Rural Winter Roadside](https://polyhaven.com/a/rural_winter_roadside)

These panoramas are also Poly Haven CC0 assets. ICEWAY uses their tonemapped
equirectangular sources, resized to a maximum width of 2048 pixels and JPEG
compressed for browser streaming. They cross-fade underneath the authored
18-day fantasy palette; none of them decides gameplay weather or lighting.

## Celestial reference maps

- `celestial/nasa-lro-moon-color-2k.jpg`: [NASA SVS CGI Moon Kit](https://svs.gsfc.nasa.gov/4720), assembled from Lunar Reconnaissance Orbiter data. Credit: NASA's Scientific Visualization Studio / Ernie Wright (USRA) / Noah Petro (NASA/GSFC).
- `celestial/nasa-sdo-sun-1k.jpg`: [NASA/JPL Solar Dynamics Observatory image PIA26681](https://www.jpl.nasa.gov/images/pia26681-image-of-sun-from-nasas-solar-dynamics-observatory/). Credit: NASA/GSFC/Solar Dynamics Observatory. The browser copy is resized to 1024 px.

The maps contribute surface detail only. ICEWAY's atmosphere shader owns the
apparent disc size, lunar phase, HDR solar core, corona, cloud attenuation and
subtle lens response. This keeps the fantasy palette art-directable without
turning either body into a flat photographic billboard.
