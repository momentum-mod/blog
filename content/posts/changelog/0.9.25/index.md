---
draft: false
showDate: true
date: 2024-01-20T05:29:43+00:00
title: 0.9.25 Changelog
---

### Refactored (5)

- Removed the `Chaos` prefix from any Panorama panels/panels that had it. `ChaosHud` is now `Hud`, `ChaosMainMenu` is now `MainMenu`, and so on.
- Removed the `Chaos` prefix from any Panorama events that had it. `ChaosFrameUpdate` is now `FrameUpdate`, `ChaosShowIntroMovie` is now `ShowIntroMovie`, and so on.
- Renamed `chaos_hud_menu_show` command to `hud_menu_show`
- Renamed `chaos_hud_menu_hide` command to `hud_menu_hide`
- Renamed `chaos_hud_menu_reload` command to `hud_menu_reload`
### Removed (2)

- Removed `ChaosPopupManager` from Panorama. Use `PopupManager` instead.
- Removed `ChaosTooltipManager` from Panorama. Use `TooltipManager` instead.
### Added (5)

- Added an overlay plane when using Hammer's Clipping Tool
- Added buildambientcache concommand to pack ambient light cache into bsp
- Added checkpoint system for KZ.
- Added support for AVX/AVX2 (and other modern x86 extensions) in VRAD. If your processor doesn't support it (or if you pass -noavx), it will fallback to a more generic version of VRAD.
- Added Comparisons HUD option to settings
### Fixed (13)

- Fixed DX11 swapchain creation failing in some cases
- Fixed a bug causing ambient_generic to not use the correct source entity when played using the Toggle input
- Fixed a bug preventing ambient_generic entities without the 'Start Silent' flag from playing
- Fixed crash when `ContextMenuFadoutTime` is undefined
- Fixed crash-on-exit in most utilities on Linux. This was a harmless crash, but annoying nonetheless.
- Fixed dynamic game mounts when running under WINE
- Fixed hammer 3D view selection not working properly with instances
- Fixed materials being used for ropes and anything else simultaneously sometimes not being drawn (e.g. on surf_arcade)
- Fixed packing of certain files into VPKs with vpk.exe
- Fixed vgui_script trying to create a video material every frame when it fails to load
- Load gameevents.res and modevents.res from the MOD search path instead of GAME. Previously, custom folder and workshop addons could unintentionally break things.
- News component now uses up-to-date Steam feed
- Fixed settings import/export dialogue
### Improved (8)

- Cleaned up some console spam
- Display times on end of run graph axis as time strings  ([game/issues/1995](https://github.com/momentum-mod/game/issues/1995))
- Hid some potentially buggy debug console commands
- Improved L4D1 and ASW model compatiblity
- Improved behavior of vpk.exe on Windows
- Load particles_manifest.txt from MOD search path. This is to prevent workshop addons overriding it. The additional BSP-packed particles_manifest.txt is unaffected by this change.
- Removed controller support in Momentum
- Static prop ambient light cache is now stored
