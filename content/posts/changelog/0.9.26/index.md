---
draft: false
showDate: true
date: 2024-02-07T03:39:37+00:00
title: 0.9.26 Changelog
---

Hi all! As before, most of our current work is happening on a separate 0.10.0 branch, which we aim to get out on Steam in the nearish future.

Most noticable thing in this update is a fix to Defrag movement (thanks Lumia), as well as a significant improvement to map loading times, thanks to some filesystem optimizations by OzxyBox.

### Added (3)

- Added 'enable' key to mounts.kv, to allow entries to be selectively disabled
- Added a status indicator for validity of autosave paths in the Hammer options dialog
- Running in tools mode will now display `[Tools Mode]` in the window title
### Fixed (8)

- Fixed CSM fading out unintentionally on PBR brushes
- Fixed incorrect lighting on PBR shader in some cases
- Fixed lightmappedreflective combo error
- Fixed particle editor crash when adding a new operator
- Fixed tools mode closing/swapping input when scrolling with the mouse
- In Hammer, use non-native file selector for instances when running under WINE
- Use the Strata icon for the engine instead of the old Chaos icon
- mom_mv_df_physics resets all relevant cvars
### Improved (3)

- HLMV now uses the same audio system as the game. This allows sound operators and more to function correctly.
- Improved loading times for when using many search paths
- Load dsp_presets.txt from MOD path
### Other (1)

- Fixed dialog variable strings in top right of leaderboards component
