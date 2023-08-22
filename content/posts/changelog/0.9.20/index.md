---
draft: false
showDate: true
date: 2023-08-22T07:38:50+00:00
title: 0.9.20 Changelog
---

### Added (3)

- Added ModelPanel methods to change/enumerate flexes
- Added ModelPanel methods to change/enumerate pose parameters
- Added ModelPanel methods to change/enumerate sequences
### Fixed (5)

- Equip Defrag machine gun on spawn
- Fixed displacement tool sometimes making 2D views to not update
- Fixed logic_branch not firing _OnLogicBranchRemoved to its listeners
- Fixed panorama not loading images when game was started with +map
- Fixed point entities in 2D view not drawing outlines and text
### Improved (11)

- Game no longer creates soundcache directory in maps folder when not needed
- Logical view in hammer now draws its title
- Made vmf saving a little bit more robust to not keep corrupted file on crash
- Move to visgroup dialog now shows user visgoups as well
- Overlays in hammer should no longer z-fight with wall they are on
- Panorama now can handle texture reloading without freaking out
- Removed max limit on texlights in vrad
- Toggling maximized view in hammer now doesn't break active mouse look
- Transform dialog now shows 1 as placeholder when scaling
- Un-developered sv_soundemitter commands
- material_modify_control now should be able to handle when materials are modified by vbsp (cubemap fixup or wvt patch) on newly compiled maps
