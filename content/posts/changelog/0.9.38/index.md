---
draft: false
showDate: true
date: 2024-12-31T01:06:15+00:00
title: 0.9.38 Changelog
---

Hi all! This update is mostly engine stability improvements, and may be our last 0.9.x release before 0.10.0.

If you'd like to test out the upcoming 0.10 changes check out the `0.10.0pre` branch on Steam, though be aware it's still quite buggy, and lacking in maps.

### Added (4)

- Added Blender-style middle mouse camera control to Hammer's 3D viewport. Middle mouse now rotates the view, and holding shift pans the view
- Added command `jpeg360` for capturing 360 screenshots
- Added cvar_dump command to dump cvars and commands to a JSON file
- Added soundscape parent file field in Hammer Soundscape Browser
### Fixed (10)

- Added aliases `snd_musicvolume` and `snd_menumusic_volume` for new the ConVars `snd_volume_music` and `snd_volume_menumusic` for backwards compat with old sound scripts
- Fixed Hammer Soundscape Browser filtering not selecting the right item
- Fixed a Hammer crash when reading malformed textures
- Fixed ambient sounds and music being spatialized in the Hammer Sound Browser
- Fixed crash when a `func_clip_vphysics` fails to create its vphysics object
- Fixed player endlessly spinning after turning camera
- Fixed regression where certain soundscapes would not play
- Fixed some maps with displacements not having collision
- Player entity endlessly spinning when looking around ([game/issues/2218](https://github.com/momentum-mod/game/issues/2218))
- Reading certain textures fails after latest update ([game/issues/2223](https://github.com/momentum-mod/game/issues/2223))
### Improved (4)

- Hammer Go To dialog now handles inputs with commas and tabs
- Hammer Run Map Expert dialog internal content can now be resized
- Reverted change making Tools Mode UI not appear on first open
- Reverted change removing Hammer Remote Shell (backend functionality for `map_edit`)
