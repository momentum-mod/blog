

### Added (8)

- Added ConVar change listener method for Panorama
- Added Defrag pitch marker offset setting
- Added Defrag pitch marker width setting
- Added Defrag prime sight setting to lock all zones to one line
- Added pose parameter output to mdlinfo and improved output formatting
- mom_mv_df_additive_jumps cvar to enable buffered additive jumps in Vintage Defrag
- mom_mv_df_fast_rampslides cvar to enable Quake 2 rampslides in Vintage Defrag
- mom_mv_df_low_jumps cvar to enable Quake 1 style low jumps in Vintage Defrag


### Fixed (14)

- Defrag player gets stuck in narrow corners ([game/issues/2068](https://github.com/momentum-mod/game/issues/2068))
- Defrag player no longer gets random HOBs on downwards ramps ([game/issues/2057](https://github.com/momentum-mod/game/issues/2057))
- Fixed $detailtint not working on VertexLitGeneric with $phong
- Fixed 3D view in Hammer flickering when antialiasing was disabled
- Fixed Hammer crash when changing prop_static entity into prop_dynamic
- Fixed crash when decoding certain 8-bit WAV files
- Fixed handling of CRLF files in studiomdl on Linux
- Fixed nodraw/favourite button in Hammer sometimes not working
- Fixed occasional lockups on very large maps when opening portals
- Fixed vbsp not finding entities at "0 0 0" and leaking the map
- Holding crouch in Defrag while jumping doesn't reset jump held status ([game/issues/2075](https://github.com/momentum-mod/game/issues/2075))
- Player can now skim over 44u ledges in VQ3 Defrag ([game/issues/2062](https://github.com/momentum-mod/game/issues/2062))
- Prime sight highlight selection wrong at non-1080p resolutions ([game/issues/2079](https://github.com/momentum-mod/game/issues/2079))
- Prime sight showing wrong zones/freezing ([game/issues/2078](https://github.com/momentum-mod/game/issues/2078))


### Improved (15)

- AddAmmo and ammo pickups now give (ammo - 1) to the player when the player has infinite ammo ([game/issues/2073](https://github.com/momentum-mod/game/issues/2073))
- Additive jumps in Vintage Defrag are now much more consistent
- Decouple Defrag HUD elements from cgaz position ([game/issues/2076](https://github.com/momentum-mod/game/issues/2076))
- Defrag player is no longer clipped to steep surfaces by default, removing sticky surf ramps
- Improved Defrag compass size by separating arrow and tick sizes
- Improved Defrag compass, windicator, and snaphud by decoupling offset from cgaz (existing configs will need to be adjusted!)
- Improved RJ trail sound attenuation
- Improved outline-styled Defrag hud zones by adding border thickness settings
- Increased max lightmap size on surfaces
- Moved imgui.ini to be under cfg/imgui.ini
- Negative entity coordinates are now sent to the client more accurately
- Quake 2 rampslides are now consistent in vintage defrag when enabled
- Show attack, attack2 on skeys HUD ([game/issues/1871](https://github.com/momentum-mod/game/issues/1871))
- Smoothstairs no longer applies when running up or down ramps in Defrag ([game/issues/1845](https://github.com/momentum-mod/game/issues/1845))
- Vintage Defrag now has CPM style double jumps by default
