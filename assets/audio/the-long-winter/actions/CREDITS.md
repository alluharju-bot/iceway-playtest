# Construction and fire recordings — R19

These are real recordings, not generated tones. All five sources are **CC0 1.0**:
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

Runtime registry: `src/audio/WildernessRecordedActions.ts`. Twelve files, roughly
450 KiB total on disk; decoded once and shared by repeated events. No per-step
fetches, and no new continuous audio loops. Existing one-shot voice cap applies.
