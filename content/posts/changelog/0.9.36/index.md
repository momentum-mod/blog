---
draft: false
showDate: true
date: 2024-10-21T08:57:46+00:00
title: 0.9.36 Changelog
---

### Added (3)

- Added DevUI windows `cl_anim_debug` and `sv_anim_debug`
- Added animation event `AE_SV_SET_SKIN` to control server side model skin
- Added animation events `AE_SV_ENABLE_BODYGROUP`, `AE_SV_DISABLE_BODYGROUP`, and `AE_SV_BODYGROUP_SET_VALUE` to control server side model bodygroups
### Fixed (8)

- Fixed a Hammer crash related to renaming visgroups
- Fixed a crash related to Steam avatars when offline
- Fixed a crash when precaching sounds after running `sv_soundemitter_flush`
- Fixed a few renderer crashes
- Fixed certain commands related to controlling demos being recorded by demos
- Fixed game crashing when changing display mode without opening panorama video settings
- Fixed the `startdemos` command not working
- Properly fire OnDamaged output for buttons without requiring damage activation spawnflag
### Improved (5)

- Bumped MAXSTUDIOFLEXCTRL to 128
- Enabled HW morph by default
- Main window on Windows 11 now uses square corners
- Raised MAXSTUDIOFLEXVERTS to 65536
- Title bar on main window now follows system dark mode
