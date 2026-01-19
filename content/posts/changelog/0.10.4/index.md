---
draft: false
showDate: true
date: 2026-01-19T06:03:17+00:00
title: 0.10.4 Changelog
---

Hey there!

This update adds the CS:GO-based KZ mode, KZT! Maps are currently found in the Beta tab, but give it a shot and let us know what you think!

We've also greatly improved player movement sounds and fixed a lot of common crashes and bugs we've seen recently.

Keep the feedback coming, and enjoy!

### Added (10)

- Added !spawn chat command for mom_respawn
- Added 360 video export to `startmovie`
- Added Defrag flight powerup ([game/issues/2595](https://github.com/momentum-mod/game/issues/2595))
- Added Near Z property slider to clustered light dev ui
- Added `$emissiontransform` to PBR, to apply transform to the emission texture specifically
- Added `sv_reloadmaterialsonmapload` convar that controls material reload behavior when loading map, can improve map load times when disabled
- Added convar `devui_auto_scale` which, when enabled, automatically scales devui to match the reference resolution of 1920x1080, like panorama
- Added nearz property to clustered light entities
- Added various CVars to control SSAO
- Climb (KZT) gamemode
### Fixed (23)

- Fixed ssbump detail textures not working properly for lightmappedgeneric shader
- Disable climb checkpoints when standing on bhop platforms
- Ducking now swims down in Defrag modes
- Fixed !b chat command not switching bonus tracks
- Fixed `mom_official_screenshot` interacting weirdly with water ([game/issues/2246](https://github.com/momentum-mod/game/issues/2246))
- Fixed a crash in hammer when copy-pasting brushes
- Fixed crash with ragdolls
- Fixed crash with the video settings screen when an incorrect panel type is used for the setting dropdowns
- Fixed devui_auto_scale not performing any scaling
- Fixed host_map_mount_order_detection not prioritizing custom asset paths in some cases
- Fixed imgui looking blurry due to autoscaling
- Fixed incorrect output conversion when using bhop trigger fix entity tool
- Fixed lightcache being slow in some cases
- Fixed loading local/online zones
- Fixed rare crash when using `point_template` under some circumstances
- Fixed shadow artifacts when spawning env_cascade_light with the CSM fix entity tool
- Fixed sun specular not blending with lightmaps properly on PBR textures
- Fixed webm video export
- Hooked up jump stats HUD with new timer system
- Rate limited the clustered atlas allocator warning to 1 message per second
- Fixed explosive weapon explosion sounds always playing in-ear ([game/issues/2475](https://github.com/momentum-mod/game/issues/2475))
- Fixed !savestate/!saveloc not opening the savestate menu
- Fixed an issue where the timer would seemingly reset to 0 seconds when entering a new zone ([game/issues/2435](https://github.com/momentum-mod/game/issues/2435))
### Improved (10)

- Added -help/-? to studiomdl
- Updated version info to reflect beta status
- Disable minimum bhop area in surf. Allow bhop zones must be used where bhopping is intended.
- Disable mom_mv_fix_edges on KZ 1.6
- Doubled cookie atlas size, allowing 4 times the texture data to be allocated before exhaustion
- Replaced general clustered light modes with independent lighting component modes
- Shift+F1 keybind will now toggle the devui menu instead of failing to open a nonexistent VGUI window
- devui_auto_scale will now use the smallest window dimension to calculate scale factor
- mom_null_binds 1 now only applies nulls while in the air. mom_null_binds 2 always applies nulls.
- Player movement sounds (footsteps, jump, landing) have been greatly improved, and should now be properly affected by player movement volume slider ([game/issues/2445](https://github.com/momentum-mod/game/issues/2445))
### Other (4)

- -mat_ao_quality: Determines the number of AO samples per depth slice
- -mat_ao_radius: Controls the AO radius (16 by default)
- -mat_ao_width/mat_ao_height: Determines the resolution of the AO
- -mat_ssao: Enables or disables SSAO (enabled by default in revolution)
