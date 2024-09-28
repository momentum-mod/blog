---
draft: false
showDate: true
date: 2024-09-28T18:20:42+00:00
title: 0.9.35 Changelog
---

### Added (8)

- Added Hammer commands `hammer_history_list`, `hammer_history_undo`, and `hammer_history_redo`
- Added `$ParallaxDither` parameter to PBR shader to enable/disable dithering
- Added `$ParallaxScale` parameter to scale the number of PBR parallax steps. This can be expensive if you're not careful!
- Added a Find All button and Results list to Hammer's Find and Replace dialog
- Added automatic mount reordering based on the assets the current map references. Use `host_map_mount_order_detection` to enable/disable.
- Added support for Hammer Qt themes via the `-theme` launch argument. (See `hammer/resource/themes/dark.kv` for an example)
- Print sound's active channel when snd_report_start_sound is enabled
- Replaced Hammer's Message Window with a new Qt Console window that can run commands and set convars
### Fixed (11)

- Fixed brush entities not rendering correctly on defrag ports
- Fixed Hammer Go To dialog ignoring angle arguments and not allowing angle only movements
- Fixed Hammer maps loaded as autosaves or via `-map` showing black viewports until reloaded
- Fixed Hammer's game config selector not adhering to the active Qt style
- Fixed a bug where a VMF could be opened before Hammer was done loading
- Fixed a few Particle Editor crashes
- Fixed a rare crash related to sound loading
- Fixed crash-on-exit in Hammer when running it in wine
- Fixed matrials with missing texture not reloading properly in hammer
- Fixed some entity output delays firing one tick earlier than in other games
- Fixed some similarly delayed entity outputs not firing in the expected order
### Improved (7)

- Added support for JavaScript module loading in Panorama
- Allowed the commands `path`, `path_file`, `fs_printopenfiles`, and `fs_warning_level` to be run from Hammer's Console
- Improved hammer's Qt console
- Improved performance of VGUI text overlays
- Panorama can consume typescript files directly
- Ported the Hammer Search Replace dialog to Qt
- Updated V8 to 12.9
