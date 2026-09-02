# Kenney Nature Kit 2.1

This directory is the complete 329-model GLB bank imported from the CC0
[Kenney Nature Kit](https://kenney.nl/assets/nature-kit). `asset-library.json`
is the stable discovery manifest. ICEWAY intentionally activates only a
curated subset through `world-asset-overrides.json`; loading all models during
startup would defeat streaming and make the editor/runtime unnecessarily
heavy.

Re-import from an unpacked source package with:

```sh
node tools/world-compiler/import-kenney-nature-kit.mjs /path/to/kenney_nature-kit
```

The original license is retained as `LICENSE.txt`.
