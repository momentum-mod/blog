---
draft: false
showDate: true
date: 2024-06-15T02:15:28+00:00
title: 0.9.32 Changelog
---

### Added (4)

- Added ConVar `traceray_seamshots_enable` (default disabled)
- Exposed `$.SystemInDarkMode()` function to panorama to query system dark theme status
- Image preview in hammer now shows all $baseTextures that material has
- Ported Hammer's Paste Special dialog to Qt
### Fixed (6)

- Fixed an uncommon crash when loading into maps with a compressed entity lump
- Fixed hammer window title being H
- Fixed occasional Hammer crashes when changing targetnames or undoing, related to entity IO
- Fixed rare crash when standing on displacements
- Fixed webm recordings encoding incorrectly
- Hammer game configuration dialog will now repopulate entity dropdowns when fgd list changes
### Improved (4)

- Ported Hammer Sound Browser to Qt
- Replaced MFC texture browser and texture replace dialog with Qt one
- Slightly decreased memory usage
- env_spritetrail no longer draws a segment where it teleported
