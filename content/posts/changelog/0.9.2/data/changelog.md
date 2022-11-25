

### Added (28)

- Add "view on website" button to uploaded runs ([game/issues/1353](https://github.com/momentum-mod/game/issues/1353))
- Add trigger to limit max number of stickies within the volume. ([game/issues/1833](https://github.com/momentum-mod/game/issues/1833))
- Added BC7 texture format support
- Added Jolt VPhysics (currently unfinished implementation, can launch with -jolt to test it out)
- Added `$seamless_scale` back to DX11 shaders
- Added `-nousermount` which prevents loading the `mounts.kv` file
- Added `m_rawinput 2`, a.k.a. the 'interpolated' raw mouse, which provides consistent mouse accuracy at any framerate
- Added `mat_brightness` which allows for changing brightness regardless of fullscreen status
- Added `mom_replay_recording_start/stop` commands to do manual Replay recordings
- Added brand new models for the rocket launcher, some upcoming defrag weapons, including new player hands with animations from SpringScale
- Added initial support for BSP v25, Chaos Source's new BSP version with immensely bigger map limits than found in CS:GO (or older games)
- Added keyvalue to gravity triggers for persisting gravity changes outside trigger volumes, returning CS:S/TF2-like functionality to them
- Added mom_replay_playback entity for mappers to playback a packed replay file
- Added spawnflag to base trigger which allows explosives to trigger things
- Added trigger_momentum_promptinput
- Added weapons to Defrag: Rocket launcher, grenade launcher, BFG, and plasma gun
- Allow mappers to store replays in their maps and use them ([game/issues/1252](https://github.com/momentum-mod/game/issues/1252))
- Bhop strafe synchronizer HUD
- DEFLATE support added to VTex, allowing compression of .vtf files outside of BSPZip
- DXT creation is now supported on Linux
- Defrag 'Vintage' physics (`mom_df_physics 2`) added, with Quake 1 strafing, rampsliding, additive jumps on ramps, and Quake 2 additive jumps on ledges, with buffering, and Q2 rampsliding on slick ramps
- Defrag jump timing HUD with `mom_df_hud_jump_*` convars
- Investigate changing default HDR parameters to more reasonable values  ([game/issues/1334](https://github.com/momentum-mod/game/issues/1334))
- Localisation tokens for all* text in the UI
- Network weapons to online ghosts ([game/issues/1839](https://github.com/momentum-mod/game/issues/1839))
- New entity - trigger_userinput with more features ([game/issues/1738](https://github.com/momentum-mod/game/issues/1738))
- Panorama FPS meter HUD ([game/issues/1516](https://github.com/momentum-mod/game/issues/1516))
- Panorama Persistent Storage Dump and Clear Commands ([game/issues/1580](https://github.com/momentum-mod/game/issues/1580))


### Fixed (31)

- Account for replay timescale in savelocs ([game/issues/1699](https://github.com/momentum-mod/game/issues/1699))
- Binding a key too quickly causes the input to be cancelled  ([game/issues/1551](https://github.com/momentum-mod/game/issues/1551))
- Crash after `kill`-ing rocket/stickybomb/conc ([game/issues/1869](https://github.com/momentum-mod/game/issues/1869))
- Defrag: Change vintage physics ([game/issues/1862](https://github.com/momentum-mod/game/issues/1862))
- Defrag: Incorrect skim behaviour on ramps ([game/issues/1799](https://github.com/momentum-mod/game/issues/1799))
- Defrag: Overbounces don't work at some heights ([game/issues/1818](https://github.com/momentum-mod/game/issues/1818))
- Defrag: Projectiles spawning/exploding incorrectly ([game/issues/1883](https://github.com/momentum-mod/game/issues/1883))
- Free spectate no longer works ([game/issues/1290](https://github.com/momentum-mod/game/issues/1290))
- Game no longer saves/changes display mode setting ([game/issues/1777](https://github.com/momentum-mod/game/issues/1777))
- Hammer Map Launcher stays active in the backround when using `-hijack` ([game/issues/1476](https://github.com/momentum-mod/game/issues/1476))
- Impossible to resume game after going to menu while result window is open ([game/issues/1747](https://github.com/momentum-mod/game/issues/1747))
- Other modes not changing some Vars from defrag ([game/issues/1748](https://github.com/momentum-mod/game/issues/1748))
- Paint not displaying for the player using it ([game/issues/1865](https://github.com/momentum-mod/game/issues/1865))
- Portal view rotation transition does not reset when resetting through a bind ([game/issues/1571](https://github.com/momentum-mod/game/issues/1571))
- RJ/SJ Swimming Speed Bugged ([game/issues/1750](https://github.com/momentum-mod/game/issues/1750))
- Ramps acting more surf-like in low AA modes ([game/issues/1879](https://github.com/momentum-mod/game/issues/1879))
- Rotating brushes in-game with Solid Type "BSP" breaks them ([game/issues/1831](https://github.com/momentum-mod/game/issues/1831))
- Settings slider text entry changes don't apply without pressing enter ([game/issues/1779](https://github.com/momentum-mod/game/issues/1779))
- Skybox seams on some maps ([game/issues/1841](https://github.com/momentum-mod/game/issues/1841))
- Some prop_dynamic renderfx are not supported ([game/issues/1842](https://github.com/momentum-mod/game/issues/1842))
- Strange view animation when ducking while walking through a portal ([game/issues/1798](https://github.com/momentum-mod/game/issues/1798))
- Trigger with Explosive Only flag still gets activated by clients ([game/issues/1838](https://github.com/momentum-mod/game/issues/1838))
- [Panorama Console] Caught-repeat messages do not show back up in developer console notify panel ([game/issues/1534](https://github.com/momentum-mod/game/issues/1534))
- `$bumpframe` is ignored by the `PBR` shader ([game/issues/1825](https://github.com/momentum-mod/game/issues/1825))
- console spam with "missing skybox texture" on a map without it ([game/issues/1677](https://github.com/momentum-mod/game/issues/1677))
- env_hudhint does not display hud hints (on both panorama and vgui) ([game/issues/1376](https://github.com/momentum-mod/game/issues/1376))
- gamemode not set on workshop maps ([game/issues/1501](https://github.com/momentum-mod/game/issues/1501))
- surf_quickie missing textures on linux ([game/issues/1826](https://github.com/momentum-mod/game/issues/1826))
- texture loading fails with lightmapped_4wayblend shader on dx11 ([game/issues/1858](https://github.com/momentum-mod/game/issues/1858))
- trigger_look does not have the correct Outputs ([game/issues/1912](https://github.com/momentum-mod/game/issues/1912))
- trigger_push not affecting players in defrag ([game/issues/1707](https://github.com/momentum-mod/game/issues/1707))


### Improved (16)

- Add inputs like `explode` `fizzle` etc to projectiles ([game/issues/1870](https://github.com/momentum-mod/game/issues/1870))
- Change default viewmodel FOV to 54 from 70 ([game/issues/1800](https://github.com/momentum-mod/game/issues/1800))
- Clean up `mom_gamemode_override` console autocomplete menu ([game/issues/1897](https://github.com/momentum-mod/game/issues/1897))
- Color the `"" isn't a valid key` output ([game/issues/1850](https://github.com/momentum-mod/game/issues/1850))
- Default `mom_mv_fix_downhill_slopes 0` in RJ and SJ ([game/issues/1893](https://github.com/momentum-mod/game/issues/1893))
- Expand holding space when in practice mode to ignore limitmovement triggers ([game/issues/1751](https://github.com/momentum-mod/game/issues/1751))
- Expose variables to API for Haste pickup (defrag) ([game/issues/1774](https://github.com/momentum-mod/game/issues/1774))
- Forward slider settings in ChaosSettingsSlider ([game/issues/1737](https://github.com/momentum-mod/game/issues/1737))
- Have a specific entity flag for explosive projectiles ([game/issues/1277](https://github.com/momentum-mod/game/issues/1277))
- Make conc UI timers appear properly through portals ([game/issues/1407](https://github.com/momentum-mod/game/issues/1407))
- Make drawer panel open on clicking the tiny buttons ([game/issues/1784](https://github.com/momentum-mod/game/issues/1784))
- Make the `Quit game` keybind always pop a confirmation menu; Remove the `quitting the game` safeguard ([game/issues/1637](https://github.com/momentum-mod/game/issues/1637))
- Momentum Pistol Single Shot Should Behave Like the USP from CS:S ([game/issues/1627](https://github.com/momentum-mod/game/issues/1627))
- Remove tiny blood splatter on shooting/knifing another player ([game/issues/1494](https://github.com/momentum-mod/game/issues/1494))
- System to Update Convar Values Post-Update ([game/issues/1855](https://github.com/momentum-mod/game/issues/1855))
- hud_saytext_time convar for panorama chat ([game/issues/1594](https://github.com/momentum-mod/game/issues/1594))
