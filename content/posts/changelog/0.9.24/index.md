---
draft: false
showDate: true
date: 2023-12-19T09:13:45+00:00
title: 0.9.24 Changelog
---

Hey all!

Just a note about updates, we're hard at work on 0.10.0 currently and rarely pushing out 0.9.X updates due to that.

In the meantime, here's some minor fixes and goodies that have been done by other developers working on their Strata games:

### Added (2)

- Added support for Ogg and FLAC audio files via libsndfile
- Added support for continuing demos recordings after disconnect (Requires `demo_autorecord 1`)
### Fixed (10)

- Faceposer no longer crashes when right-clicking in the Phoneme Editor
- Fixed 'black' shader not respecting fog like it should
- Fixed Hammer 3D Shaded Textured Polygons View looking blown out
- Fixed a case where the uphill slope fix could incorrectly stop the player's movement
- Fixed displacement carve normal direction combobox not having expected entries
- Fixed models in hammer getting randomly colored when the entity didn't have rendercolor kv
- Fixed nodraw button disabling some helpers
- Fixed nodraw button in hammer not hiding all non-default nodraw faces
- Fixed occasional materialsystem deadlock when loading maps
- Unhid some cvars related to bloom (mat_bloomscale, mat_bloom_scalefactor_scalar)
### Improved (11)

- Added on/off parameter to god, notarget, and buddha commands to match noclip behavior
- Allow fgd flags key type to have long name and a description
- Creating displacement from brush entities will now move the solid to world
- Hammer entity properties dialog should now set origin when creating brush entities
- Improved compile times on models with large amounts of flexes
- Improved support for Mp3 audio files by replacing minimp3 with libsndfile
- Improved texture browser responsiveness
- Made KZ gamemode cvars more reasonable
- SAPI phonemeextractor now can actually extract phonemes
- Texturebrowser now stores state of its filters
- The game will now only fail to launch if the same Strata-based game is already running (instead of general Source games)
