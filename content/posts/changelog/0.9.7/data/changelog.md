

### Added (11)

- Add `-aoradius` to vrad as alternative to `-aoscale`
- Add detailed information about jump (gain percentage, efficiency percentage) and strafe trainer bar ([game/issues/1629](https://github.com/momentum-mod/game/issues/1629))
- Added Defrag weapon settings to settings
- Added `sleep_when_meeting_framerate` option to video settings
- Added custom soundmixer contexts for easier player-controlled game-specific sound categories
- Added non-uniform prop scaling via the 'scale' parameter
- Allow non-uniform scaling of prop_static ([game/issues/1998](https://github.com/momentum-mod/game/issues/1998))
- Defrag: Damage boost pickup ([game/issues/1847](https://github.com/momentum-mod/game/issues/1847))
- Defrag: Damage boost player entity inputs ([game/issues/1846](https://github.com/momentum-mod/game/issues/1846))
- Defrag: Haste pickup ([game/issues/1814](https://github.com/momentum-mod/game/issues/1814))
- [Panorama] Alpha axis in color picker panel ([game/issues/1585](https://github.com/momentum-mod/game/issues/1585))


### Fixed (19)

- CGAZ Mirror zones flicker ([game/issues/1971](https://github.com/momentum-mod/game/issues/1971))
- CGAZ mirror zones are drawn incorrectly with the Haste powerup ([game/issues/1970](https://github.com/momentum-mod/game/issues/1970))
- Crash in CMomentumPlayer::DisableWeaponAndSwitch ([game/issues/1875](https://github.com/momentum-mod/game/issues/1875))
- Fix crash in Hammer when removing an element
- Fix crash on maps using multiplayer physics props
- Fix crash when loading maps with world portals
- Fix crash when loading surf_cyberwave after bhop_recharge
- Fix crash when player being spectated left the lobby
- Fix jump_academy crash when TF2 isn't mounted
- Fix specular reflections on brush PBR
- Fixed VRAD not compiling on high performance power options
- Fixed entering practice mode getting the player stuck in the ceiling ([game/issues/1735](https://github.com/momentum-mod/game/issues/1735))
- Fixed error when doing `respawn_entities` on a BSPZipped map
- Fixed overlays disappearing after repacking a BSP
- Fixed pitch marker being never drawn in Defrag ([game/issues/1986](https://github.com/momentum-mod/game/issues/1986))
- Resolve panorama debugger crashes
- Spectating icon not visible in chat ([game/issues/1974](https://github.com/momentum-mod/game/issues/1974))
- `mom_replay_playback` entity no longer works ([game/issues/1978](https://github.com/momentum-mod/game/issues/1978))
- bhop_pharma `r_unloadlightmaps 1` perf issue. ([game/issues/1976](https://github.com/momentum-mod/game/issues/1976))


### Improved (19)

- Add triple monitor mode to settings
- Added option to color jump stats on synchronizer ([game/issues/1963](https://github.com/momentum-mod/game/issues/1963))
- Improve error handling if no compatible GPU is available
- Improved handling mounting the platform/ folder
- Optimize the memory that VBSP uses
- Panorama file + folder layout improvements
- Removed DX9 shaders and launch option, defaulting to DX11
- Restructured jump stats to print on takeoff ([game/issues/1964](https://github.com/momentum-mod/game/issues/1964))
- Small optimizations to VRAD to aid in reducing compile times
- Update DXVK to 2.1 (this requires GPU driver support for Vulkan 1.3!)
- Update Panorama sass parser to 1.58.0
- Update SDL to 2.26.2
- Update V8 to 11.2.76
- Update bhop stats to be percentages where ratios are shown ([game/issues/1961](https://github.com/momentum-mod/game/issues/1961))
- Update jump stats panel to show strafes per jump instead of total strafes ([game/issues/1960](https://github.com/momentum-mod/game/issues/1960))
- Updated Panorama debugger to use more consistent rendering
- Use higher precision when making brush cuts in Hammer ([game/issues/1988](https://github.com/momentum-mod/game/issues/1988))
- Various improvements to game startup time
- Various miscellaneous crash fixes
