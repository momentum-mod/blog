---
draft: false
showDate: true
date: 2026-11-21T19:32:20+00:00
title: 0.10.9 Changelog
---

Hey all, we’ve got an exciting update for you today! Groups, voice chat, a brand new leaderboards experience, and a TON of fixes are coming to your favorite movement game!

NOTE: Rank points are NOT in this update, but will be coming VERY soon after. We have some tweaks to make from excellent community feedback, and will deploy it to our site first to see how things are looking. Once we’re comfortable, we’ll show rank points and rankings in the game directly!

### Added (21)

- Added "Touching surface property" filter mode to `filter_momentum_surface_collision`. Set `surfaceprop_name` to a surface property (e.g. `metal`) to filter on it. Unlike "Touching material", this also works on displacements
- Added ConVar r_ssao_max_portal_recursion
- Added SetHoldTime input to game_text
- Added Slope Scale slider to Clustered Light Inspector
- Added `checkpoints_activated` keyvalue to filter_momentum_timer_progress. This can be used to check how many checkpoints the player has activated in the current stage.
- Added `mom_mv_hl_edgefriction_debug` to visualize edge friction in HL/1.6 movement
- Added `r_legacy_model_lighting` to control how map lights light models. -1 = automatic (default), which uses Source-style lighting on maps compiled before Strata's light modes, 0 = Strata, 1 = Source.
- Added a graphics setting to configure volumetrics resolution
- Added an `$alphatransmittance` param (defaulted to 1) to PBR that may be disabled to replicate the old coverage-style alpha handling.
- Added an input to force a `light_rt` entity to update its shadows
- Added an option to `light_rt` entities to disable rendering shadows for dynamic geometry, reducing update frequency significantly
- Added an option to report players by right clicking them in the lobby player list
- Added holding CTRL while zoning to ignore player clips when placing points, so zones can be lined up with the geometry behind them
- Added perfect bhop percentage stat to jump timing HUD (mom_hud_jump_timing_perfs)
- Added r_flushmodel <path/to/model.mdl>, which reloads a specific model
- Added shadow freezing to `light_rt` entities, allowing shadow updates to be disabled
- Added voice chat system. Use +voicerecord to communicate with your microphone.
- HUD Customizer layer controls (Bring to Front, Bring Forward, Send Backward, Send to Back) for overlapping elements.
- Overlays can be applied to brush entities. They will follow the brush around, and can be duplicated if the brush entity is spawned via template.
- Prime Sight inactive zones and CGAZ mirror zones can be colored by input: By Key Count, By Key or By Direction, with a color preview in the settings. Works in CPM and VQ3.
- Turnt Meter, a new Defrag HUD element that replaces the Windicator. It shows whether you are turning at the optimal rate for air control, A/D turns (CPM), VTG air movement, circle jumps and slick.
### Fixed (45)

- Enabling ambient occlusion in vrad doesn't lower sample count to 0
- Fixed CDN request wrongly including an authenticator header
- Fixed `mom_respawn` not resetting weapons and powerups in Defrag gamemodes
- Fixed `trigger_catapult` visualization potentially ending early, if the target is higher/lower than the start.
- Fixed `trigger_look` elapsed time not resetting when players leave the trigger.
- Fixed alphatested/dithered PBR materials darkening with <1.0 alpha values
- Fixed an `env_beam` crash that can occur if no 'ending entity' is used and the target position is in the void.
- Fixed being able to set a checkpoint in Climb modes while standing in a `trigger_momentum_bhop`
- Fixed closing the zoning and HUD customizer menus not closing any open dropdown menus
- Fixed crash when using `/b` or `mom_bonus` without a bonus number on maps that have no zones
- Fixed decal blend mode 9 not using alpha correctly
- Fixed flexes on legacy models such as Dr. Breen
- Fixed map selector thumbnails sometimes showing a map from the previously selected gamemode
- Fixed materials with syntax errors in their VMT failing to load
- Fixed models in rooms built from props being lit far too dark and with the wrong colors (surf_kraken)
- Fixed models not being lit by the sun on maps without an `env_cascade_light` (surf_innokia)
- Fixed non-translucent materials with an alpha channel blending with volumetric fog incorrectly
- Fixed personal best times and favorites sometimes disappearing from the map selector
- Fixed player avatars displaying at players' feet rather than above their heads
- Fixed players, weapons and other moving models getting no direct sunlight on maps without CSM
- Fixed refract materials such as glass and water appearing invisible or without their tint (surf_sacrifice, surf_innokia)
- Fixed replays not loading when already in spectate or watching another replay.
- Fixed savelocs losing their vertical velocity when loaded while standing on the ground
- Fixed some physics intersection state persisting up to one second after teleporting away from the intersection
- Fixed some static props rendering completely black when their map's baked lighting was made for a different version of the model (surf_pantheon, surf_stonework3)
- Fixed splits HUD checkpoint numbering issues when watching replays recorded before the 0.10.6 update
- Fixed the ammo counter not updating in replays (fixed in new replays only)
- Fixed the energy speedometer incorrectly showing height changes from teleports and portals as gained or lost energy
- Fixed the expensive reprojected volumetrics path triggering in unintended situations (e.g. through portals)
- Fixed the map selector background sometimes showing a different map than the selected one after quickly switching between maps
- Fixed the map selector showing no maps when you can't authenticate with the server. It now shows the map list from your last session.
- Fixed the screen going black when spectating a player who is noclipping outside the map
- Fixed the third person replay camera aiming too low in Climb 1.6, HL1 Bhop, Conc, and Defrag
- Fixed the zoning and HUD customizer menus remaining interactable via the keyboard after being closed
- Fixed the zoning step and shape creation mode labels being positioned incorrectly and mostly hidden behind the zoning menu
- Fixed translucent PBR materials becoming near-opaque in both forms of volumetric fog
- Fixed translucent PBR materials incorrectly scaling specular light by opacity
- Fixed translucent effects behind refracting glass, such as glows, disappearing on older maps
- Fixed view briefly rising from below the player after restoring a saveloc shortly after crouching in Climb 1.6 and HL1 Bhop
- Fixed warning popup not displaying when Steam is down
- Fixed z-fighting of non-`$decal` overlays in Hammer
- Fixed zone editor crosshair text (e.g. heights and the "close polygon" hint) not appearing
- Properly adjust colors for disabled QT windows in Hammer and other tools
- Select new visgroups after creation in 'edit visgroups' dialog
- VCD "synctofollowinggesture" flag can now be stored in binary VCD format
### Improved (43)

- Add saveloc support for the energy speedometer
- Added a track selector to the main menu and tab menu. Every main, stage and bonus track now shows its tier, your personal best, your rank out of total completions and your rank group for the selected style.
- Automatically download maps when trying to watch a replay
- Automatically play maps after they are done downloading
- CGAZ mirror zones now work in every direction and follow the same input rules as Prime Sight (two-key inputs in white, one-key inputs in amber by default), including Single-Key Zones and Input Range in VQ3.
- Close tab menu when opening the HUD customizer
- Converted the 'Edit Visgroups' dialog to Qt.
- Hammer now shows loading progress of instances during map loading, showing each individually as well as overall progress.
- Hammer's Entity Report dialog will now save/restore the widget state again.
- Improved AO rendering through portals
- Improved Defrag HUD rendering. In-world HUD elements (CGAZ, Snap HUD, Prime Sight, etc.) are now updated every frame, so they stay locked to the world at any framerate and react to your keys without delay.
- Improved HUD Customizer snapping. HUD elements can now be aligned with other elements. Holding CTRL enables element snapping, and holding Shift locks movement to only x/y directions.
- Improved accuracy of Defrag projectile knockback. This should help with plasma climbing up higher walls.
- Improved stability of volumetrics under motion
- Improved the appearance at the edge of volumetric fog volumes, especially at a distance
- Moved Defrag HUD to the HUD Customizer and removed old Defrag HUD convars (mom_hud_df_cgaz_*, snap, prime, turnt, compass, pitch). These settings are now in the HUD Customizer and are not carried over, so you will need to set up your Defrag HUD again. mom_hud_df_projection and mom_hud_df_fov_override stay as convars.
- Moved the volumetric fog blur pass to its own shader to improve performance
- Opening the console no longer also opens the pause menu
- Panorama HUD panels can be forced to update every frame. This change makes the panels feel less "floaty" when positioned in world space.
- Pitch targets: add as many as you like, each drawn as a line or, with different min and max values, as a zone.
- Pressing <Enter> while typing in the map name filter box now selects the first listed map
- Prime Sight in VQ3 now shows the best zone for every input within an adjustable Input Range of your velocity (45-180 degrees, default 80), not just one inactive zone. Single-Key Zones (Off / No Overlap / Always) controls whether one-key inputs such as half-beats are shown: No Overlap hides them where they would cover a two-key zone, Always shows them anyway.
- Prime Sight now works in all directions, not only forward. See accurate gain zones while moving backwards or sideways.
- Raised primary player color saturation cap to 0.65. This is in addition to fixing lighting bugs that made the player less vibrant than they should be.
- Re-implemented reduced ducktap landing friction in HL1 Bhop (mom_mv_ducktap_friction_timestep)
- Renamed momentum_powerup_doublejump to momentum_powerup_airjump
- Replaced HTTP-based run session tracking with WebSockets
- Show zone dimensions next to the crosshair while zoning (length x width, segment lengths and height) instead of corner coordinates
- Significantly improved performance on maps converted from Quake 3 (5-6x more FPS on detailed maps)
- Snap HUD target highlight now works in every direction, matching Prime Sight's target zone.
- The "Move Selection to Visgroup" window has been converted to Qt.
- The Defrag HUD now hides in free-roam, third-person view and third-person spectating.
- The `singlestep` convar can be set to `2` to count server ticks instead of host ticks.
- The energy speedometer now measures height from where you last stood on the ground without bhopping, instead of your last jump, so bhopping onto higher or lower ground no longer resets it
- The selected map no longer changes when the current map selection becomes hidden by map list filter changes
- Using an empty material field on `material_modify_control` will now match all materials with `MaterialModify` proxy
- Watching a replay from the map selector now closes the pause menu
- When initially placed, overlay sizes will now obey `$decalscale`, or the overall texture size set in Hammer options. New `%overlaysize` and `%overlayoffset` VMT parameters allow directly specifying the size, and offsetting it from the entity position. (Both are `[x y]` vectors.)
- When using `singlestep`, `next` can be set to the number of frames you want to advance.
- Zone heights now follow the zone's own faces instead of whatever is behind the zone, making them much easier to place precisely
- Zone point snapping now works on props with a high vertex count
- `r_unlimitedrefract` now defaults to -1 (automatic), which refreshes refraction for every refracting object only on BSP version 20 and older maps (0 = once per frame, 1 = always)
- `retry`, `restart` and `reload` now reload the map in the gamemode you're currently playing instead of switching back to the map's default gamemode
### Clustered Light Editor (5)

- Added the ability to select a light from the crosshair by pressing the RELOAD key.
- Added the ability to change a light's cookie, including path validation. Requires the light to have specified a cookie in the map to use.
- Added the ability to spawn new lights (light_rt and light_rt_spot).
- All valid lights are now highlighted with a box, instead of the selected one only being highlighted. Unselected lights are RED, while selected lights are GREEN.
- Reduced the maximum slider value of the Light Radius in the Clustered Light Editor, allowing for more granular control. Higher values outside the range can still be set via the text box.
