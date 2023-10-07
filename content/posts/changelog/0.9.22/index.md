---
draft: false
showDate: true
date: 2023-10-07T09:32:08+00:00
title: 0.9.22 Changelog
---

### Added (4)

- Added a mandatory whitelist file for panorama's AsyncWebRequest function. The `-unrestrictedwebrequests` launch argument will skip this file and allow all requests
- Added option to set paint colour from surface normal (`mom_paint_color_from_normal`) ([game/issues/951](https://github.com/momentum-mod/game/issues/951))
- Added support for escape sequences `\n`, `\t`, `\"`, and `\\` in VMF and BSP [#60](https://github.com/StrataSource/Engine/issues/60) [#1899](https://github.com/momentum-mod/game/issues/1899)
- Added support for multiroot KV1 in kv3t.
### Fixed (17)

- Crash when firing Defrag machine gun or railgun
- Fixed Hammer crashes related to entity outputs
- Fixed Hammer crashes related to saving and loading files
- Fixed `-multirun` not working [#882](https://github.com/StrataSource/Engine/issues/882)
- Fixed `player_speedmod` not working in singleplayer when inputs are not called directly from the player
- Fixed certain VTFs failing to load due to added resources ([game/issues/1223](https://github.com/momentum-mod/game/issues/1223))
- Fixed explosive decals appearing on both sides of thin brush surfaces ([game/issues/1929](https://github.com/momentum-mod/game/issues/1929))
- Fixed hammer block tool creating brushes that stick out 0.25 units in each direction
- Fixed instance outputs bugs
- Fixed issues with some collision traces, notably bullet impact traces on displacements
- Fixed opening the game menu sometimes requiring an extra ESC input. ([game/issues/2102](https://github.com/momentum-mod/game/issues/2102))
- Fixed sticky explosive decals not appearing on walls/ceilings ([game/issues/1929](https://github.com/momentum-mod/game/issues/1929))
- Fixed string truncation when using SetMessage input on point_worldtext
- Fixed trigger_look not working ([game/issues/1617](https://github.com/momentum-mod/game/issues/1617))
- Prevent a crash when the surface vertex count exceeds the max decal vertex limit
- [Hammer] using '\n' in any text field will cause hammer to error out while trying to open the vmf ([game/issues/1899](https://github.com/momentum-mod/game/issues/1899))
- point_worldtext input 'SetMessage' does not change passed 7 letters ([game/issues/1905](https://github.com/momentum-mod/game/issues/1905))
### Improved (5)

- Fogui FarZ can now be set to -1 (Default value), which disables the override
- Fogui now allows users to enter and copy numbers manually on sliders
- Made SJ/RJ/defrag explosion decals fade out (controlled by `mom_sj_decals_fade`/`mom_rj_decals_fade`/`mom_df_decals_fade`) ([game/issues/2101](https://github.com/momentum-mod/game/issues/2101))
- Ported Select Entity dialog to Qt
- `ambient_generic` now finds Sound Source entity's every time it is played, not only when initialized
