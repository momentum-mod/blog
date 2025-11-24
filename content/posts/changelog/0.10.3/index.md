---
draft: false
showDate: true
date: 2025-11-24T22:56:35+00:00
title: 0.10.3 Changelog
---

Hey there, we have a bunch of big things in the works, but in the meantime we wanted to push out more fixes and minor additions we've done.

For those with limited accounts, you should be able to play the game, but nothing will submit. We strongly recommend making your Steam account unlimited (spending $5 USD of your own money) if you are playing on a Steam account you care about.

KZT, SDL3, and more will be coming in 0.10.4!

### Added (13)

- !ss chat command for setting start marks
- Added -report console parameter to vbsp vrad and vvis to output compile time reports as keyvalue files
- Added mom_lobby_relay_status and mom_lobby_relay_init commands to help with debugging relay-related problems with lobbies
- Added mom_zone_experimental_appearance ConVar, which for now just changes the appearance of Checkpoint zones as an early reference for zoners while we are still working out the new zone visuals. ([game/issues/2095](https://github.com/momentum-mod/game/issues/2095))
- Added soundscriptui for debugging sound scripts
- Added sv_particles_reload/cl_particles_reload to reload particles
- Added the texture parameter $detailmask to the PBR shader, which masks the detail texture.
- Automatically generate zones for climb modes when looking at a button ([game/issues/2494](https://github.com/momentum-mod/game/issues/2494))
- Enabled mom_mv_fix_uphill_slopes on Surf
- Prime sight highlight strength setting (mom_hud_df_prime_highlight_strength)
- Re-added the mom_chat_sound convar which controls whether a sound plays on incoming chat message, defaulted to ON.
- Use gamemode-specific behavior emulating func_door blocks when func_bhop landing limit is set to -1
- mom_movement_sound_jump_df and mom_movement_sound_land_df for Defrag specific movement sounds
### Fixed (14)

- $lod replacemodel works as expected
- ATI1N and ATI2N formats will now use their correct names in debug windows like mat_texture_list
- Display stage start zone safe height
- Fixed "Fragged Surf" achievement to only unlock when the local player shoots another player
- Fixed "Momentum Man" and "WR Holder" achievement unlock logic to require the player to be playing with you in a map
- Fixed HUD spectator list not working ([game/issues/2393](https://github.com/momentum-mod/game/issues/2393))
- Fixed chat message not printing when player leaves a Map lobby
- Fixed end of run "Watch Replay" button not working when getting a new PB ([game/issues/2490](https://github.com/momentum-mod/game/issues/2490))
- Fixed one of the main reasons for lobby joinlag. Please let us know if it continues to happen! ([game/issues/1659](https://github.com/momentum-mod/game/issues/1659))
- Fixed some refract textures being too dark ([game/issues/2556](https://github.com/momentum-mod/game/issues/2556))
- Fixed the jump height normalization gamemode setting to no longer be tickrate dependent so the player jumps 65.5 units high regardless of tickrate (after ducking in mid-air, on CS-based modes)
- Fixed viewmodels being forced to draw when using AlternativeSorting on an entity ([game/issues/2558](https://github.com/momentum-mod/game/issues/2558))
- StudioMdl properly caches models when loading.
- Zone height and safe height are now able to be snapped to a map vertex when zoning
### Improved (10)

- !saveloc/!savestate now opens the save state menu
- Cycle through bonuses when mom_bonus or !b has no parameters
- Improved clustered lighting performance on some GPUs and maps with many lights
- Increase max player model saturation to 0.5
- The zone for the current stage now stays visible instead of disappearing when activated
- Various improvements around lobby socket cleanup to hopefully reduce connection issues and crashing on shutdown. These may still happen, please keep an eye out in your console for status codes and let us know of any!
- Vbsp, vrad and vvis now accept `-nogamemount` and `-nousermount`
- Videos can now be loaded from vpks and bsps
- When using `-nogamemount` switch, the game now will mount appids that are marked as required
- Added all HL2 related content from the SDK 2013 Singleplayer repository, which adds some episodic models and materials
