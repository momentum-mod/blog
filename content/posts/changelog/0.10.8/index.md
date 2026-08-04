---
draft: false
showDate: true
date: 2026-08-04T05:49:16+00:00
title: 0.10.8 Changelog
---

Hey there, we've got some fun things for you all to try!

The first is the long-awaited HUD Customizer worked on by Natan and Tom. You can activate the customizer by clicking the in-game TAB menu icon, or via the game settings while in a map, allowing you to completely change the locations, fonts, colors and more of the HUD! The lovely Pace has made a wonderful video on how it works here: https://www.youtube.com/watch?v=WI9mNxF1_zQ

Panzer, with some help from Mac, has been getting BSPConvert cleaned up for its 1.0.0 release! 0.10.8 brings a ton of compatibility and general fixes to defrag maps, including support for Q3's volumetric fog and spheremap reflections. This work helps unblock a lot of defrag maps from being ported, so keep an eye out for more Q3 maps coming soon!

This update also features another couple levers to pull for attempting to fix the dreaded Lobby Join Lag issue we've seen players deal with for a while now. By default, we're disabling the ability for players to make direct connections to one another, instead relying on connecting to the Steam relay servers only. This may introduce some latency with sending packets to some players, but since Momentum doesn't rely on synchronized game state, this is a trade worth making to see if it finally fixes this once and for all! Please let us know if the join lag still happens for you, or if the game still crashes upon quitting shortly after leaving a lobby with others in it.

0.10.9 is going to be sooner than this release took to come out, and with it, lobby voice chat along with a basic reporting system! Thank you all for playing and giving your feedback, and keep it coming!

### HUD Customizer (1)

- The in-game HUD is now fully customizable! Players can enable HUD editing via the in-game TAB menu, or via the settings while in a map! You can get an overview on how to use it via Pace's wonderful video found here: https://www.youtube.com/watch?v=WI9mNxF1_zQ
### Lobby Lag Fixes (3)

- - `mom_lobby_ice_disable` - Sets the global `P2P_Transport_ICE_Enable` config to 0, routing lobby/TV connections over the Steam relay instead of direct P2P. Potentially eliminates an expensive network-adapter enumeration that only happens on Windows. This is defaulted to ON.
- - `mom_lobby_stagger_tv_peers_delay` - The amount of time (in seconds) to delay connecting to each peer in your lobby. Can potentially help with joining larger lobbies and not connecting to everyone. Default to OFF.
- - `mom_lobby_prewarm_networking` - Attempt to pre-load of steamwebrtc64.dll at startup so the module load doesn't happen on the first lobby join for Windows users. Defaults to OFF, as `mom_lobbby_ice_disable` supersedes this behavior.
### Added (21)

- $decaltexture, $decalmrao, and $decalbump to PBR materials to assign decals that use a second UV map
- Add TeleportDelay KV to trigger_momentum_teleport
- Added "Damage Opens" spawnflag to func_door
- Added "gamemodes" key value to all entities. This key value can be used to enable entities for specific gamemodes.
- Added $detailtexturetransform to LightmappedGeneric. This VMT parameter can be used to transform detail textures independently from the base texture.
- Added $spheremap and $spheremapscale material parameters to LightmappedGeneric, VertexLitGeneric, and UnlitGeneric
- Added %CompileNoImpact (SURF_NOIMPACT) surface flag, which can be used to prevent bullet/projectile impact effects and missile explosions
- Added OnJump and OnLand outputs to func_bhop
- Added Quake 3-style volumetric fog. This effect can be created by using the "Fog" shader along with the "%compileFog 1", "$fogcolor [r g b]", and "$fogdepthforopaque <distance>" VMT parameters.
- Added SnapVelocityToDestinationAngles key value to trigger_teleport and point_teleport. This can be used to recreate misaligned telehops from CS:S.
- Added double jump powerup to Defrag modes (momentum_powerup_doublejump)
- Added energy speedometer. This displays your total mechanical energy (kinetic + potential) as the height you could reach above your last jump.
- Added material proxy that can evaluate custom math expression
- Added math_evaluate entity that can evaluate custom math expression(s)
- Added new devui panel "Clustered Light Stats" which can help you troubleshoot performance issues with dynamic lights
- Added new inputs to `func_movelinear`: `Toggle`, `Pause`, `Resume` and `SetPositionImmediately`, as well as an `OnReachedPosition` output.
- Added new options to trigger_look - optional LOS check, outputs that fire when the player starts/stops looking as well as not looking.
- Added trigger_momentum_bhop (trigger-based version of func_bhop)
- Added volumetric fog system
- Added vtexd executable for extracting images from VTF textures
- Load placeholder models/collisions for unmounted games.
### Fixed (13)

- Fix Defrag projectile vector snapping issues
- Fixed an issue where the 'png' command would fail to write the image to disk
- Fixed an issue where the Volume, FadeIn, and FadeOut inputs for ambient_generics could not function properly
- Fixed crash when changing maps after rendering a cookie light
- Fixed offsets being ignored for `$texturetransform` variables on the `PBR` shader.
- Fixed orientation of Hammer entity sprites outside of instances.
- Fixed softlock if a player is catapulted by `trigger_catapult`, after using a ladder at any point.
- Fixed some BSP Convert maps crashing due to an index buffer memory access violation (df_torque, df_fpscup02-6)
- Fixed the backbuffer turning dark after being copied once
- Hammer entity sprites will now always correctly use alpha blending.
- Reset the underwater ripple overlay after respawning or loading saves
- The "Show shadow updates" checkbox on the Clustered Stats devui can be toggled off
- Use exact min/max pitch angles from Quake 3 in Defrag modes
### Improved (19)

- A warning will now display if the Volume input on a non-looping ambient_generic is fired with a value of 0, due to it innately stopping the sound
- Added `$decaltint`, `$decalmraointensity` and `$decalbumpintensity` to PBR shader.
- Allow editing zone bottom on freeform point zones
- Automatically unduck when ducktapping
- Certain ambient_generic inputs no longer start the sound again, if they were triggered while the sound was not playing
- Disable autohop while ducktapping
- Hammer will now properly show `$collisionjoints` collision models
- Heavily improved performance when volumetric fog could not possibly be visible
- Improved appearance of volumetrics, especially for harsh drop-off spotlights
- PlaySound on looping ambient_generic entities will now always start or restart it, matching its non-looping counterpart behavior
- Reduced mom_safeguard_holdtime minimum value to 0.1
- Renamed momentum_powerup_damage_boost to momentum_powerup_damageboost
- StopSound on non-looping ambient_generic entities will now properly stop it, matching its looping counterpart behavior
- VBSP will now immediately error if an instance has cordons enabled, instead of crashing with hard-to-debug brush errors
- While editing an existing zone, the delete key can be used to delete a point while moving it, instead of only while hovering over a point
- `//` comments are now supported in `.cfg` command files. Slashes inside quotes are unaffected.
- `env_beam` "Texture Scroll Rate" can now be negative
- `trigger_catapult` has an improved preview ingame and in Hammer, showing more precise possible trajectories. Added `catapult_debug_points` and `catapult_debug_interval` to tweak the visualisation.
- trigger_momentum_limitmovement's prevent bhop flag now temporarily disables jump input after landing for the duration set by the BhopCooldown keyvalue
