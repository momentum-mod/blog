---
draft: false
showDate: true
date: 2024-03-05T09:30:28+00:00
title: 0.9.28 Changelog
---

Hi! As usual, most work is being done on our internal 0.10 branch.

This update fixes certain cvars being locked being sv_cheats 1 since removing -mapping mode, and a crash on close that we introduced last update.

We also have various fixes to the PBR shader, and should have some new PBR materials coming in the near-ish future!

### Added (3)

- Added GameInterfaceAPI.GetCurrentMap to Panorama
- Added PBR parallax dithering to smooth out the appearance of layers
- Added `packed_files_list` to view files packed into the BSP
### Fixed (7)

- Fixed crash when exiting the game using the close window button
- Fixed PBR parallax using texture coordinates from the layer below the correct one
- Fixed WVT and PBR materials not rendering properly when used on displacements ([game/issues/2027](https://github.com/momentum-mod/game/issues/2027))
- Fixed some objects not rendering in Hammer 2D views
- Fixed window size bug on Linux
- Re-enable $depthblend in SpriteCard shader
- cl_drawhud, r_drawclipbrushes and various other debug commands no longer require sv_cheats 1
### Improved (1)

- Hlmv link mode now syncs light state and colors
### Other (1)

- mat_softwareskin / mat_softwarelighting allows for more accurate vertex normals ([game/issues/960](https://github.com/momentum-mod/game/issues/960))
