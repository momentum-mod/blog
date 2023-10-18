---
draft: false
showDate: true
date: 2023-10-18T07:28:10+00:00
title: 0.9.23 Changelog
---

### Gamemode System (6)

- All ConVars with gamemode-specific values can now be viewed with `mom_print_modevars`. This shows which ConVars are supported by the current gamemode and their default values.
- Added new ConVars for offline customization of gamemode movement: `mom_mv_limit_ground_speed`, `mom_mv_limit_jump_speed`, and `mom_mv_limit_jump_speed_factor`
- Renamed or refactored some ConVars. Use `mom_print_modevars` to see an updated list of ConVars relevant to gamemodes.
- Removed the "Unknown" gamemode.
- Added `mom_gamemode_fallback`, which specifies which gamemode should be used when the game can't determine an appropriate gamemode from the current map. This has lower priority than `mom_gamemode_override`.
- Using `mom_gamemode_override` will now persist until changing the override, loading a map from the map selector, or restarting the game. Previously, the override would be cleared after loading a map from the console in some cases.
### Added (3)

- Added language support for Indonesian
- Jump sound for all gamemodes, controlled with cvar "mom_play_jump_sound". Off by default. ([game/issues/2070](https://github.com/momentum-mod/game/issues/2070))
- Player takes full deceleration on jump when +strafe is held for a certain number of ticks before and after the jump. Controlled by the "mom_mv_ahop_strafe_decel_ticks_prejump" and "mom_mv_ahop_strafe_decel_ticks_postjump" cvars.
### Fixed (2)

- JavaScript error when going closing settings ([game/issues/2104](https://github.com/momentum-mod/game/issues/2104))
- Defrag players no longer hits top edge of steep ramps ([game/issues/2082](https://github.com/momentum-mod/game/issues/2082))
### Improved (3)

- Defrag player now autoswitches to next best weapon when out of ammo ([game/issues/2081](https://github.com/momentum-mod/game/issues/2081))
- Ported displacement noise dialog to Qt
- SplineRope shader now supports $baseTextureTransform and $color params
