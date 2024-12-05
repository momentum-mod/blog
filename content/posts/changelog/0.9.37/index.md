---
draft: false
showDate: true
date: 2024-12-05T07:04:34+00:00
title: 0.9.37 Changelog
---

### Added (6)

- Added Hammer command `hammer_history_clear`
- Added Panorama `CUiComponent_SteamOverlay` functions `OpenGameOverlayAchievements`, `OpenGameOverlayCommunity`, `OpenGameOverlayFriends`, `OpenGameOverlayOfficialGameGroup`, `OpenGameOverlayPlayers`, `OpenGameOverlaySettings`, `OpenGameOverlayStats`, and `OpenGameOverlayStore` (upstream from Revolution)
- Added support for ZSTD compression to VTF v7.6
- Added support for browsing Soundscapes in Hammer
- Added support for new lines and tabs to `point_worldtext`
- Added volume slider to Hammer Sound Browser
### Fixed (18)

- Compressed VTFs will now load correctly if they have less than the maximum amount of mip levels
- Fix parsing `semi-bold` font weights
- Fixed Hammer autosave error dialog showing up multiple times
- Fixed Hammer truncating long file names when reporting file parsing errors
- Fixed a rare Hammer crash when reading VMFs that have a key or value that sits on a file read chunk border
- Fixed audio being spatialized in the Hammer Sound Browser when it shouldn't be
- Fixed crash in Hammer when viewing a material using solid energy refract
- Fixed crash on exit in bspzip
- Fixed crash on some older maps with displacements
- Fixed cursor being recentered even when the game isn't focused on Linux
- Fixed exclusive fullscreen mode not entering fullscreen in some cases
- Fixed hammer pinning one thread to 100%
- Fixed occasional Faceposer crash when selecting an invalid file
- Fixed occasional Hammer crashes related to undo and redo in the Face Edit dialog
- Game failing to detect monitor refreshrate ([game/issues/1790](https://github.com/momentum-mod/game/issues/1790))
- Malformed VTF compression info resources (AXC) will no longer potentially crash the game on load
- PBR and PaintBlob shader now respect configured texture in env_projectedtexture
- surf_illusion stage 4 buffer overflow in heap block crash ([game/issues/2213](https://github.com/momentum-mod/game/issues/2213))
### Improved (10)

- HLMV will now always show both regular File Open and Steam File Open regardless of if `-OldDialogs` is used
- Improved docdump output
- Material browser now does not squish tall textures
- The Hammer Console now handles end lines and other non-standard content a little better
- The Hammer Console now uses a monospaced font for all text
- The commands `cl_soundscape_flush`, `playsoundscape`, `stopsoundscape`, `cl_soundscape_printdebuginfo`, and `cl_ss_origin` can now be ran from the Hammer Console
- The commands `echo`, `cache_print`, `cache_print_lru`, `cache_print_summary`, `sv_soundemitter_filecheck`, `sv_findsoundname`, and `sv_soundemitter_spew` can now be ran from the Hammer Console
- The commands `mat_configcurrent`, `memory`, and `stat_memory` can now be run from the Hammer Console
- Updated dxvk to v2.4.1
- Viewmodel lag now works properly with world mirroring
