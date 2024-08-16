---
draft: false
showDate: true
date: 2024-08-16T23:32:23+00:00
title: 0.9.34 Changelog
---

### Added (2)

- Added modelbrowser-like search mode to texturebrowser
- Added support to VRAD for L4D1/ASW static prop models (those using `.vtx` instead of `.dx90.vtx`)
### Fixed (2)

- Fixed VRAD crash when using `-textureshadows` with opaque materials using `$basetexturetransform`
- Fixed VRAD regression with maps being too bright
### Improved (4)

- $color value is now applied in linear space for previews in texturebrowser
- Hammer is now more stable
- Reduced VRAD memory utilization when using `-textureshadows` with multiple materials that refer to the same texture
- mat_picmip now allows its full -10 to 4 range
