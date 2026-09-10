# Construction and fire recordings — R19 / R21

These are real recordings, not generated tones. All sources are **CC0 1.0**:
https://creativecommons.org/publicdomain/zero/1.0/

| Local files | Recording / author | Public source preview |
| --- | --- | --- |
| wood-step-1…6.wav | [Walking On A Wooden Floor — ralph.whitehead](https://freesound.org/people/ralph.whitehead/sounds/331452/) | https://cdn.freesound.org/previews/331/331452_1971023-hq.mp3 |
| hammer-1…3.wav | [Hammering.wav — Dvideoguy](https://freesound.org/people/Dvideoguy/sounds/207782/) | https://cdn.freesound.org/previews/207/207782_2046066-hq.mp3 |
| ceramic-break.wav | [Breaking pot short — anna_bliss](https://freesound.org/people/anna_bliss/sounds/810043/) | https://cdn.freesound.org/previews/810/810043_17435303-hq.mp3 |
| fire-ignite.wav | [fire-whoosh.wav — hnhnh](https://freesound.org/people/hnhnh/sounds/244926/) | https://cdn.freesound.org/previews/244/244926_3983630-hq.mp3 |
| bottle-swish.wav | [Whoosh - Long Bamboo stick - OS ST 13 — Sadiquecat](https://freesound.org/people/Sadiquecat/sounds/855844/) | https://cdn.freesound.org/previews/855/855844_5287430-hq.mp3 |

License verified from each author page on 2026-09-10. Imported from the publicly
offered high-quality MP3 previews, not the login-only original downloads.
The footstep recording provides six separate footfalls; stair contact uses the
same timber bank. Hammer clips are three separate strikes. Throw, ceramic impact
and ignition are distinct gameplay events; normal structural ignition is much
quieter than an accelerant spill. Existing stone/metal foley is unchanged.

Edits: mono downmix, short cue selection, rumble/DC high-pass, short click-free
fades, conservative peak normalization and resampling to 32 kHz PCM16 WAV.
The complete reproducible cue sheet is in
`tools/audio/prepare-construction-foley.mjs`. Decode previews to mono PCM16 WAV
(`wood-decoded.wav`, `hammer-decoded.wav`, `ceramic-decoded.wav`,
`ignite-decoded.wav`, `throw-decoded.wav`) then run that script with the directory
as its argument. No source recordings or processing code run in the game.

Runtime registry: `src/audio/WildernessRecordedActions.ts`. Eighteen short files,
decoded once and shared by repeated events. No per-step fetches. Existing one-shot
voice cap applies.

## R21 — timber-family foley and wick flame

Verified 2026-09-11, CC0; downloaded the public HQ MP3 previews.

- `mallet-1…3.wav`: [Wooden Mallet — leo153](https://freesound.org/people/leo153/sounds/535629/).
  Three separate strikes, used for wooden uprights/walls/beams.
- `saw-1…3.wav`: [Hand Saw — deleted_user_7146007](https://freesound.org/people/deleted_user_7146007/sounds/383725/).
  Three short cues, used for timber roof work. Floors/stairs retain nail strikes.
- `../fire/wick-flame-loop.wav`: [Fire Crackle and Flames 002 — TheWoodlandNomad / FractalStudios](https://freesound.org/people/TheWoodlandNomad/sounds/363092/).
  Adapted wood-fire recording, **not a recording of an actual hand torch**.
  A quieter flame bed replaces the welding-like loop on mounted/carried torches.
  The old loop is retained for other fuel effects.

Processing: `tools/audio/prepare-torch-build-foley.mjs` decodes in offline Chrome,
downmixes to mono, resamples to 32 kHz, filters rumble, applies cue fades and peak
normalization. The 11.6 s flame loop has a 400 ms seam crossfade. Source preview
filenames in the preparation directory: `flame.mp3`, `mallet.mp3`, `saw.mp3`.
No offline processing script is shipped in the gameplay bundle.
