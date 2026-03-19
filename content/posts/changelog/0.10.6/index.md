---
draft: false
showDate: true
date: 2026-03-19T20:45:44+00:00
title: 0.10.6 Changelog
---

Hello all! We're got some exiting updates for you.

This update change how CS:GO is mounted, so make sure to install CS:GO from the standalone app that Valve added, found at https://store.steampowered.com/app/4465480/CounterStrike_Global_Offensive/ ! Your CS:2 installation is no longer required, so feel free to opt-out of the csgo_legacy branch, or uninstall it completely to free up some space.

This update also adds the initial system for Run Styles! On modes like surf and bhop, you can change the style of run you're doing via the in-game leaderboard dropdown, or use the newly added "mom_style" command! We have plans to add more styles like backwards and low-grav in a future update, but try it out for now and let us know how you like it!

### Added (12)

- Added "empty" weapon
- Added Run Styles
- Added "Meet Your Maker" achievement unlock logic
- Added -EnvCubemapNotForcedForPBR parameter to vbsp, for mappers that need PBR materials with handmade envmaps
- Added -nowinerenderfix to disable rerendering Hammer views on each frame in WINE
- Added a `sound` KV to env_spark to change the spark sound
- Added support for Hammer++ rectangle map hotspot definitions
- Added texture flag to fully ignore mat_picmip (NOLOD only ignores mat_picmip when convar is positive) at 2^18
- Added trigger_momentum_disallowcheckpoint for preventing setting checkpoints in climb modes
- Added vtex config flag "ignorepicmip" to control setting the IGNORE_PICMIP flag in the compiled VTF
- Displays thickness of ropes and cables in hammer
- Re-added the "Learn" section, accessible from the main menu bar
### Fixed (14)

- Fixed Panorama rendertargets being invalidated when mat_picmip is changed
- Fixed TF2 rocketlauncher rockets not properly tracing up close when mom_tf2_rocket_max_extents was 1
- Fixed a crash if entity filters are evaluated on dead entities.
- Fixed a crash in VScript when calling `CreateEntityByName` on a non-existing class
- Fixed allowbhop zones not applying to edgebug jumps
- Fixed an issue where scenes inside scenes.image files would not be properly precached, which resulted in their associated audio files being unable to play.
- Fixed crash when creating decals on some BSP Convert maps
- Fixed crash with the netconsole
- Fixed some displacements having no collision on BSP Convert maps
- Potential fix for runs failing to submit due to invalid run sessions
- Removed zlib and libxml2 dependencies from studiomdl on Linux
- VTF textures below v7.5 are no longer allowed to set v7.5-specific flags to guard against flags from TF2 being set
- Fixed spectator list not updating when changing maps ([game/issues/2642](https://github.com/momentum-mod/game/issues/2642))
- Fixed some maps not properly parsing entities and crashing ([game/issues/2641](https://github.com/momentum-mod/game/issues/2641))
### Improved (6)

- Entity filters will no longer crash if chained in an infinite loop.
- Hammer's Discord Rich Presence no longer shares map name by default
- PBR materials with manually specified $envmap will no longer be overridden to use env_cubemap
- Respawn entities when restarting a run in Defrag modes
- CS:GO mounting now uses the standalone app at https://store.steampowered.com/app/4465480/CounterStrike_Global_Offensive/
- The "mom_hide_players" convar is now a map-runtime var, meaning it will reset to 0 upon changing maps ([game/issues/2615](https://github.com/momentum-mod/game/issues/2615))
