---
draft: false
showDate: true
date: 2026-02-23T00:10:18+00:00
title: 0.10.5 Changelog
---

### Added (13)

- A "Use Native File Browser" option in Hammer, to allow using Qt file dialogs and vice versa
- Added "Paste Special Again" context menu option in Hammer, which will use the last saved Paste Special options in the session without a prompt.
- Added `-debug_dynamic_mounts` to debug steam dynamic mounts
- Added an imgui game events debugger
- Added an in-game ImGui material inspector/rudimentary editor
- Added an in-game cloth/softbody debugger
- Added enabled field to particle operators to toggle operator on/off
- Added mdl2dmx, a very basic static prop decompiler
- Added mom_zoning_start_zone_button_radius and mom_zoning_end_zone_button_radius for configuring climb button zone radius
- Entity Tools: Added an option to convert trigger_multiple outputs to OnJump if they activate trigger_push entities
- Ignore backface displacement collisions in maps converted from Quake 3
- Quake 2-style ladder climbing for Defrag modes
- When using the eyedropper tool, Hammer will prompt to name entities if they did not have one already.
### Fixed (19)

- Fix a crash when removing/changing loaded FGDs in Hammer
- Fixed Paste Special entity name prefix field not retaining its value across multiple different invocations of the dialog.
- Fixed SSAO crashing game in some cases
- Fixed `SetLightScale` on clustered lights not changing the light intensity
- Fixed `SettingsSlider` `invert` not working correctly when the slider is set to display a percentage
- Fixed anti-bhop triggers preventing checkpoints from being set in climb modes
- Fixed copy+paste in ImGui windows
- Fixed crash on shutdown when lumper sync is enabled
- Fixed crashes when using some material proxies on non-standard stuff
- Fixed flashlight and env_projectedtexture shadows being 4x larger per-dimension than their pre-clustered equivalents
- Fixed misspelled KV on `snd_op_occlusion`: `occlusio_db_loss` is now `occlusion_db_loss` (old KV still works though)
- Fixed rockets firing from the wrong location when crouched by disabling mom_tf2_rocket_use_max_extents
- Fixed stage timer disabling on tracks with bhop enabled
- Fixed studiomdl trying to run `md` on Linux to create the output dir. It now runs `mkdir -p`
- Jump and forward move inputs can now stack while using the flight powerup in Defrag
- Light cookies now correctly use the light entity orientation
- Make env_global's GetCounter input usable
- Model browser getting sometimes getting stuck
- r_ssao no longer breaks cubemap building
### Improved (19)

- Added support for custom fonts in devui themes. FontScaleDpi, FontScaleMain, FontScaleBase control font size. Font property controls the actual font and is a path like `resource/MyFont.ttf`
- Allow `bool`/`boolean` to be interchangably for FGD IO and KV definitions.
- Cloth no longer simulates while the game is paused by default.
- Console input autocomplete suggestions now include fuzzy matches
- Disable null binds in CPM and VQ3
- Displacement tools now edit continuously without needing to move mouse
- Entity Tools: Restore scrollbar position when reloading entities
- Entity report dialog can now be sorted
- Exposed the following debug convars: snd_occlusion_pos_override, snd_occlusion_material_override, snd_occlusion_visualize, snd_occlusion_visualize_filter, snd_occlusion_indirect_radius, snd_occlusion_indirect_min, snd_occlusion_indirect_max, snd_occlusion_collide_min_distance
- Hammer now does not spam warning about unknown detail object types
- Hammer prints more fgd errors when something goes wrong
- Increased default clustered shadow budget from 6 to 12
- Made sv_gravity affect cloth
- Removed -winecompat from Hammer, fixes will be applied when WINE is detected automatically
- Removed soundsystem.dll
- Updated VRad help text
- VRad AO is now DISABLED by default and can be enabled by passing `-ao`. XeGTAO should be preferred for VRad baked AO.
- `fps_max_menu` is now also respected while in game with opened menu
- env_spark entities can now override fx_new_sparks to use new or old sparks
