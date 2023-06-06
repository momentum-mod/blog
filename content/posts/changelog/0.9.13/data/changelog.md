

### Added (7)

- Added crash feedback dialog
- Added ent_text debug output to logic_gate
- Added framerate limit to hammer 3D viewport to prevent GPU ramping up to 100% usage
- Added utility to dump shader documentation
- New mom_mv_df_clip_steep_ground for testing non-sticky surf ramps in Defrag
- Option to choose framerate limit in Hammer
- Option to disable lazy texture loading in Hammer


### Fixed (20)

- Crash loading `jump_lanc_v3` ([game/issues/2065](https://github.com/momentum-mod/game/issues/2065))
- Curved walls in Defrag cause the player to get stuck ([game/issues/1734](https://github.com/momentum-mod/game/issues/1734))
- Defrag haste UI regression ([game/issues/2058](https://github.com/momentum-mod/game/issues/2058))
- Fixed Linux dependency issues for Panorama
- Fixed crash when sprite helper would have invalid model and parent tried to change scale kv
- Fixed game missing the `depthresolve_ps50` shader
- Fixed loading of TF2 maps with v7 static prop lump
- Fixed logic_gate having incorrect starting state
- Fixed logic_gate state being incorrect after reloading a save
- Fixed model helper trying to use non-uniform scale on non-prop_static entities
- Fixed not being able to choose game config with doubleclick
- Fixed occasional hammer and game crash when reloading models
- Fixed png screenshots having a weird line in them in some cases
- Fixed png screenshots on maps with HDR being too dark
- Fixed rendering breaking when disabling postprocess on HDR maps
- Fixed the incorrectly sized viewport in HLMV and Faceposer
- Game and tools no longer rename themselves "MainThrd" on Linux
- Hammer camera button and statistics now render correctly
- RemoveDFWeapon output ignores weapon switch delay ([game/issues/1884](https://github.com/momentum-mod/game/issues/1884))
- Wait for timer to run out when removing Defrag weapons (fixes instant rocket -> plasma switch on df_precision)


### Improved (8)

- Converted hammer options to Qt
- Correct Defrag CPM swimming physics ([game/issues/1843](https://github.com/momentum-mod/game/issues/1843))
- HDR cubemaps are now stored in BC6H format
- LDR cubemaps are now stored in BC7 format
- Player no longer has 1-2 ups in Defrag when hitting corners at high speed
- Ported vgui debug system menu to ImGui
- Remove 1 ups when hitting corners at high speed in Defrag ([game/issues/2064](https://github.com/momentum-mod/game/issues/2064))
- Water movement is now more accurate in Defrag
