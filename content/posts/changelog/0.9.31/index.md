---
draft: false
showDate: true
date: 2024-05-07T21:14:27+00:00
title: 0.9.31 Changelog
---

### Added (2)

- Added VBSP flag -upgradeversion which upgrades an existing BSP to Strata Source BSP version 25
- Added mountinfo executable to print search paths used by the game
### Fixed (5)

- Fixed ahop +strafe speed nerf not working if strafe keys were held ([game/issues/2144](https://github.com/momentum-mod/game/issues/2144))
- Fixed some displacements in older maps having no collision when traceray_force_vphysics is enabled
- Player can no longer flat shark while crouching
- Player doesn't get grounded while attempting flat sharking
- Water friction ticks are applied immediately at the start of flat sharking
### Improved (4)

- Improvements to RJ water consistency ([game/issues/1363](https://github.com/momentum-mod/game/issues/1363))
- Replaced `dump_entity_sizes` with `cl_dump_entity_sizes` and `sv_dump_entity_sizes`
- Replaced `dumpentityfactories` with `cl_dump_entity_factories` and `sv_dump_entity_factories`
- Replaced `dumpentitynamespaces` with `cl_dump_entity_namespaces` and `sv_dump_entity_namespaces`
