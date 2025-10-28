---
draft: false
showDate: true
date: 2025-10-28T05:13:52+00:00
title: 0.10.2 Changelog
---

Hey there!

This update adds some Steam Achievements, proper Defrag HUD support for replays+online, and TONS of fixes!

We're still investigating the lobby connection issues with Steam Support, KZT is in code review, and voice chat is also being cooked up, so stay tuned for future updates!

### Added (7)

- Added -shadowatlassize launch parameter to specify clustered shadow atlas dimensions. Must be power of two
- Added a console warning for when the clustered shadow/cookie atlases are full
- Added a flag to `light_rt` and `light_rt_spot` to force shadows to update every frame
- Added some Steam Achievements, have fun unlocking them! ([game/issues/1151](https://github.com/momentum-mod/game/issues/1151))
- Added support for $treesway to PBR. The material parameters match VertexLitGeneric
- CSM fix entity tool
- FGD flag values can now have description (currently not visible in any UI)
### Fixed (12)

- Fixed Faceposer crash when loading an invalid subscene
- Fixed Hammer erroring out if Steam mounting is unavailable, even if the selected game doesn't need it
- Fixed Hammer regression causing objects to be duplicated
- Fixed conc beeps not canceling when restarting timer
- Fixed crash upon joining invite to a map lobby in main menu
- Fixed crashes when using mat_crosshair commands from main menu
- Fixed flashlights suddenly becoming invisible far from their origin
- Fixed ghost name panels interpreting names as localization strings
- Fixed lights becoming fully shadowed outside their NearZ/FarZ range
- Fixed possible crash when loading corrupted BSP files
- Fixed potential bug with detail texcoord transforms in VLG when $treesway is enabled. If you notice broken VLG treesway models, please tell us!!
- filter_momentum_surface_collision exported with entity tools using a misnamed key for filter_name
### Improved (12)

- Defaulted cl_threaded_bone_setup to 1 to fix jittery ghost animations ([game/issues/2463](https://github.com/momentum-mod/game/issues/2463))
- Disable mom_mv_df_clip_speed_ground in VTG
- Don't prime the timer if the player has any KZ checkpoints ([game/issues/2497](https://github.com/momentum-mod/game/issues/2497))
- Improved performance of client side entity classname comparisons
- Made low OS memory warning print a little bit less often
- Players will now be warned when they're trying to join an incompatible lobby via the drawer ([game/issues/2516](https://github.com/momentum-mod/game/issues/2516))
- Record movement data for Defrag HUD
- Restored the behavior where a trigger_catapult pointing straight up multiplies its speed by 1.5x, to keep backwards compatibility with existing maps
- Set sv_accelerate to 10 and sv_friction to 4 for VTG
- TF2 rockets will now properly go the full grid length instead of 2000 units (toggle via mom_tf2_rocket_use_max_extents) ([game/issues/1816](https://github.com/momentum-mod/game/issues/1816))
- filter_activator_class matching the class name tf_projectile_rocket now works with Momentum Mod rockets
- func_button OnDamaged output only activates once per shot instead of once per bullet impact, matching Team Fortress 2 behavior
