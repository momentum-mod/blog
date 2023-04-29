

### Added (9)

- Added %compileslick material parameter
- Added 'maxprojectedtextures' keyvalue to world entity to control projected texture limit
- Added CS:S stamina mapping mode cvar via `mom_mv_stamina_enabled`
- Added SetSlick player input to control slick status programmatically
- Added _nocubemapsprite to disable light sprites when building cubemaps
- Added compute shader support with stretchrect compute shader
- Added func_slick entity for Defrag slick behavior
- Added help (-h or -help) command line parameters to VBSP, VRAD, and VVIS
- Added imgui UI framework for fogui and CSM settings


### Fixed (8)

- Fix +showbudget_texture(_global) not showing data properly
- Fixed brush entities with primitive geometry not rendering correctly
- Fixed crash related to instances in VBSP
- Fixed crash related to static prop scaling
- Fixed screenshots not working with MSAA enabled
- Packed .mrf files not being loaded by mom_replay_playback entity ([game/issues/2011](https://github.com/momentum-mod/game/issues/2011))
- Panorama border size changes when color is changed ([game/issues/2045](https://github.com/momentum-mod/game/issues/2045))
- Snap hud offset calculated incorrectly ([game/issues/2039](https://github.com/momentum-mod/game/issues/2039))


### Improved (2)

- Add customization settings to defrag groundboost indicator ([game/issues/2046](https://github.com/momentum-mod/game/issues/2046))
- Improve Defrag groundboost indicator behavior ([game/issues/2040](https://github.com/momentum-mod/game/issues/2040))
