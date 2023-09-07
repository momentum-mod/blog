---
draft: false
showDate: true
date: 2023-09-07T07:57:13+00:00
title: 0.9.21 Changelog
---

### Added (3)

- Added CSM and flashlight to `lightmappedreflective`
- Added `gameui_activate` command to Steam Input command list
- Added `zoom`, `toggleconsole`, `showconsole` and `hideconsole` commands to be usable in steam input
### Fixed (7)

- Adjusted folder mounting order to fix wrong assets occasionally being used
- Change default engine cubemap from de_vertigo's to a black cubemap ([game/issues/2074](https://github.com/momentum-mod/game/issues/2074))
- Fixed Hammer inserting extra quotation marks for compile commands [#753](https://github.com/StrataSource/Engine/issues/753)
- Fixed VBSP not always acknowledging parameters in patched materials
- Fixed flashlight making some opaque water disappear
- Fixed the map name not displaying in the top right corner [#912](https://github.com/StrataSource/Engine/issues/912)
- Made ModelPanel rotation speed consistent regardless of FPS
### Improved (7)

- Allowed the game to run alongside other Source games without `-multirun` [#268](https://github.com/momentum-mod/game/issues/268)
- Displacements now use the more accurate VPhysics collisions by default (traceray_force_vphysics 1)
- Ported Hammer Arch and Torus dialogs to Qt
- Ported Hammer Map Diff dialog to Qt
- Removed SFUI prefixes from all localization files
- Unamed instances can now use `func_instance_io_proxy`
- Update Audio Settings to use new MixGroups ([game/issues/2097](https://github.com/momentum-mod/game/issues/2097))
### Other (0)

