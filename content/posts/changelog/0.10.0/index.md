# TO-DO!!!
- everyone should look over this and make sure nothing is missing. this probably shouldnt include absolutely everything we changed that's user-facing, but dont want to forget key things
- update convar/command names after any final changes
- map submission and website sections can maybe be elaborated a bit

# Momentum 0.10.0 Changelog

## Timer and Zones
We have completely rewritten and revamped our timer system and zoning tools. These are not just up to par with those found in other games, but feature cutting-edge functionality and design.

Here are the highlights:
- Added stage and bonus tracks with their own leaderboards.
- Generally improved the restrictions around what is allowed when starting a run, including speed limitations and restricting the ability to start from an elevated position (where appropriate).
- Every track start zone now has an explicitly defined teleport destination, including an appropriate yaw angle so the player faces forward when teleporting to the zone with a command.
- Timers for multiple tracks can now run simultaneously and independently of each other.
	> This means while you are running a main track with stages, you can also set a personal best time on one of the individual stage tracks and have it submit to the leaderboard. Simultaneous timers also work with bonuses. For example, on surf_sinsane you can run the main track and, once you finish it, continue onto the extra bonus portion at the end to attempt a bonus completion in the same run.

- Added commands for switching tracks:
	- `mom_main`
	- `mom_stage <number>`	
	- `mom_bonus <number>`
	
	You can also switch tracks from the tab menu.
- `mom_restart_stage` can now be used to restart a non-staged main track or a bonus track.
- When a teleport trigger teleports the player to a zone while also removing their horizontal speed (a "drop teleport", or one that entirely removes speed), air acceleration is disabled until the player lands on the ground.
- When a teleport trigger teleports the player to a zone while removing horizontal speed and keeping only downward speed (a drop teleport), the zone does not activate until the player lands on the ground.
	> This ensures the optimal route for ending a stage is the same whether you are optimizing for the entire map or just that one stage.

- Added support for timer checkpoints which may be activated in any order. This can be enabled on a per-stage basis.
- Added support for optional timer checkpoints which provide timer splits but do not gate progress through the track. This can be enabled on a per-stage basis.
- Added support for "drop" start zones. If there is no standable ground below a track start zone's teleport destination, the track's timer starts as soon as the player teleports to it. The player does not have to drop out of the bottom of the zone first.
- Added a new zone type which allows the player to keep all of their speed when jumping (a.k.a. bhop) while inside it. Bhopping can be enabled at the gamemode level, or per-track, or with this new zone type.
- Added a feature where the player is allowed to bhop on any surface of a certain size or larger.
	> On gamemodes that enable this feature, if a square with a certain side length fits anywhere on the ground where the player jumps, they are allowed to bhop even if the gamemode would otherwise disallow it. For example, this allows the player to bhop on the platform at the end of a surf stage (without needing a bhop zone), but not on narrow ramp spines or small detail geometry. This will, however, allow the player to jump on *large* ramp spines or any other large surface which is easy to aim for, and we hope this will keep some amount of organic bhop usage in a gamemode like Surf that does not otherwise allow unrestricted bhopping.

- Fixed a bug that could cause the player to activate a zone while just barely outside of it.
- Our in-game zoning tools have been remade to support the new zone system and were upgraded with a greatly improved user experience.
	> The tools can be accessed by turning on `sv_cheats 1` and using the button that appears in the bottom left corner of the tab menu.

- For those that prefer to use Hammer, zones can still be set up in Hammer and exported as part of the compile chain or as an independent action, using zonemaker.exe (formerly zonmaker.exe).

- Added command safeguards. Commands that reset your timer now need to be held for a brief duration before they execute. Use `mom_safeguard_minruntime` to specify how long the timer must be running before the safeguards activate.
- Timer restart commands will now teleport to spawn when there are no zones.
	
## Replays and Multiplayer Networking (MomentumTV)
We have also completely rewritten and revamped our replay and multiplayer networking systems. These now function like fast and lightweight Source Engine demos, which makes them extremely capable and accurate to real gameplay.

Replays and multiplayer networking now support and accurately recreate:
- Player animations
- Weapons and projectiles
- Sound effects
- Timer state
- Map entities, like doors and buttons

Momentum Mod is a spectator game as much as it is one you play yourself, so it was absolutely critical for us to have extremely high quality replays as well as peer-to-peer multiplayer networking on par with the networking in other Source Engine games.

This was a short section, but the development took a ton of work! We would love to talk about this in more detail in a future blog post.

## Entities
The 0.10.0 update is all about starting to build up our official map catalog, so it was important to polish existing entities designed for Momentum Mod and give ourselves and community mappers important tools to get existing maps to a high-quality standard:

### Teleport Triggers
- The "Preserve angles" spawnflag is now hidden in Hammer in favor of the newer `UseLandmarkAngles` key, which is now displayed as "Use Destination Angles". The "Preserve angles" spawnflag is still supported if a map made with an older Source Engine branch is loaded in game.
- Removed redundant "reset angles" setting
- When a teleport trigger is configured to snap player view angles to the destination angles, the horizontal component of the player's velocity is now also aligned to the destination angles. The "Snap to Destination" mode has also been removed in favor of this.
- Removed the "Velocity Scale" setting.
- Removed the "Reorient Landmark" setting.
	> This was used to choose whether to use the landmark teleport rotation logic from older or newer Source Engine branches, but the new logic is backwards compatible with the old logic, so the new logic is now always used.

- Removed the landmark teleport setting from the rest of the "modes". The remaining modes are now all "velocity modes" and are no longer mutually exclusive with landmark teleports. The velocity modes are now also supported by the `point_teleport` entity.
- The setting which causes the trigger to activate on `EndTouch` instead of `StartTouch` is now a standard key instead of a spawnflag for better visibility.
- Removed `trigger_momentum_teleport_progress` and re-added `trigger_momentum_teleport`, which is the same as `trigger_teleport` but with an additional option which uses the player's current progress destination as the teleport destination.
- When a teleport trigger uses a velocity mode other than the classic "Retain" mode, that velocity effect will now always take priority over other effects applied in the same tick, like a `trigger_push` boost.
- Teleport triggers now adjust the destination position upward up to one unit to keep the player's feet from getting stuck.
- Teleport triggers now always pick the first entity in the entity list matching the destination name (older Source Engine branch behavior) instead of cycling through each match with each successive teleport (newer Source Engine branch behavior).

### Improvements to `trigger_setspeed`
- Simplified and expanded the entity's settings and generally made it more intuitive to use. You now configure how it should affect the player's horizontal speed and vertical speed separately.

- Horizontal speed behaviors:
	- Set exact speed and velocity yaw
	- Set exact speed without changing velocity yaw
	- Set speed only if moving slower (enforce a minimum speed)
	- Set speed only if moving faster (enforce a maximum speed)
	- Do nothing

- Vertical speed behaviors:
	- Set exact speed
	- Set speed only if lower (possibly a higher magnitude in the negative direction)
	- Set speed only if higher (possibly a lower magnitude in the negative direction)
	- Do nothing

- Added a new setting called "Strict Mode" which adds several restrictions on the trigger's behavior. For example, the trigger wont activate if the player jumps into it, and ducking is disabled while the trigger is active.
	> This mode ensures the trigger gives extremely consistent results. It will be used for most track-start boosters.

### Other Entity Changes
- Added `filter_momentum_surface_collision`. This filter can detect if the player is touching anything, touching a standable surface, touching a non-standable surface, or touching a specific material, and can limit this to only brushes, models, and/or displacements.
	> This filter can be used to effortlessly set up precise fail teleports, instead of needing to hand-make a lot of carefully sculpted triggers. For example, you could place a single `trigger_teleport` around an entire surf track and use this filter with the "touching a standable surface" mode so that the player is reset if they touch anything that is not surfable.
- `trigger_momentum_progress` now has a teleport destination property instead of using the origin of the trigger itself.
	> Note: The progress teleport system is also disabled until we add support for it in the new timer system.

- Added player inputs that increase the player's speed in the direction they are moving: `AddSpeed` (for 3D speed), `AddHorizontalSpeed`, and `AddVerticalSpeed`.
	> These let you create I/O-based omnidirectional boosts, in contrast to something like `AddOutput basevelocity X Y Z` which is always in a single static direction.

- The bhop prevention setting of `trigger_momentum_limitmovement` now causes the player's speed to be capped when jumping instead of disabling jumping for an arbitrary number of ticks.
- Added support for the "grenadeclip" contents type, such as with the material `tools/toolsgrenadeclip` from CS:GO. This is solid to projectiles like stickybombs and rockets, but not to the player or anything else.
- Removed the "stick on entering this area" option from `trigger_stick_explosive` in favor of grenadeclip brushes. We plan on adding more projectile collision tools in the future.
- Added `OnJump` and `OnLand` outputs to all trigger entity classes.
- Added the `func_touch` entity class. This is a *solid* brush entity with all of the same outputs as `trigger_multiple`. For example, you can fire an output when the player collides with the entity (`OnStartTouch`) or jumps off of it (`OnJump`).
- When exiting a `trigger_push`, the player is no longer boosted by an extra half of one tick portion of the boost amount. For example, a 1000 units/sec `trigger_push` on 100 tickrate would previously boost the player by an extra 5 units/sec when exiting it.
	> This technically makes all `trigger_push` boosts slightly slower, though it is a more intuitive and consistent behavior.

- Removed `trigger_momentum_push`, which was redundant.
- Removed `trigger_reversespeed`. We plan on replacing this with a more capable and robust solid entity in the future.
- Removed `trigger_shootboost`. This entity was meant to make it easier to make shoot boosts, but this is an old-school mechanic that has fallen out of favor and is best left to legacy maps.
- Removed `filter_momentum_progress` and `filter_momentum_track_number`, and added `filter_momentum_timer_progress` with similar functionality.
- Removed `trigger_momentum_slide` in favor of `func_slide`.
- Removed `filter_momentum_player_state` in favor of the similar `filter_momentum_surface_collision`.
- Removed `env_surface_teleport` in favor of using `filter_momentum_surface_collision` with a `trigger_teleport`.

## Map Submission System
Momentum Mod is all about maps, and with so many to account for, preparing and adding them needs to be a community effort.

We have an all-new system for adding maps in a structured and streamlined way. Anybody can help add a map to the game by fixing any entity issues, setting up zones, filling out a form on the website with the list of map tracks and their tiers as well as other map info, and submitting the map for public testing and review. Once it passes the review process, the map is added to the game!

## Website and Backend Systems
- The website front page has been redesigned and updated.
- The website dashboard has been upgraded with a new look and no longer requires logging in to view leaderboards.
- Improved the backend's ability to handle traffic.

## Gamemodes
- Added the following new gamemodes:
	- Half-Life Bhop
 	- Counter-Strike 1.6 Climb
  	- VQ3 Defrag: Default movement settings from Quake 3 Arena
  	- Vintage Defrag: Reminiscent of Quake 1 movement, with some adjustments for faster paced gameplay
- Defrag changes:
	- Added Defrag modifier bonuses. These bonuses can add any combination of the following modifiers to a map: haste, slick, damage boost, rockets, plasma gun, and BFG.
 	- Added overbounce zones. These zones allow the player to overbounce while inside of their volume.
- Sticky Jump changes:
	- New knockback mode for stickybombs, which cancels all knockback taken during the tick if stickybomb damage would exceed 175. Off by default, controlled by the `mom_sj_cancel_lethal_knockback` ConVar.
 	- `mom_sj_buffer_window` ConVar to control the stickybomb launcher attack buffer.
  	- `mom_sj_set_sticky_limit` command to set the current stickybomb limit.
  	- `mom_sj_no_damage_window` ConVar to provide a short buffer after arming where the stickybomb won't contribute to damage taken for the purpose of knockback canceling.

## Porting Tools
### Lumper
Lumper is an open source program used for modifying various lumps in Source engine's BSP files. It can be used to make changes to entities, replace texture assets, apply Stripper configs, and review maps. For more information, check [Lumper's GitHub page](https://github.com/momentum-mod/lumper).

### Entity Tools
Entity Tools can be enabled using the `devui_show entitytools` console command. These are in-game tools used to make adjustments to entities to improve gameplay and promote competitive integrity according to Momentum Mod’s standards. The following tools are currently available for modifying in-game entities:
- Teleport Velocity Mode: Change the velocity mode applied to players arriving at a teleport destination. This is mainly used for adding drop teleports to staged surf maps.
- Landmark Teleports: Fixes issues with incorrect landmark destination angles.
- Boost Triggers: Convert boost triggers to more consistent and less exploitable versions.
- Gravity Triggers: Add persistent gravity to trigger_gravity entities used on pre-CS:GO maps.
- Model Scale Fix: Fix the scale of props that use the `modelscale` KV on pre-CS:GO maps.
- Bhop Block Fix: Converts legacy func_door and func_button bhop platforms to func_bhop.

### BSP Convert
BSP Convert is an open source command line interface tool for converting maps from Quake 3 into Strata engine. The main advantage of this tool is that it preserves lightmap data across engines, which is normally lost during decompilation. It also automates the vast majority of the porting process, reducing the time it takes to port maps from hours of manual effort to seconds with one command. For more information on the project, check [BSP Convert's GitHub page](https://github.com/momentum-mod/bspconvert).

## Miscellaneous
- Added clustered rendering, a new rendering system allows for real-time dynamic lighting. For more information, see https://portal2communityedition.com/clustered
- The entire official map list is now cached locally, enabling the map selector to update instantly as you type or change filters.
- Added roaming lobbies, which automatically connect you to players playing the same map as you (toggle with the `mom_lobby_roaming` ConVar).
- Added a "freecam" system to look around the map independently of the player's position. Exiting freecam resumes your control and view of the player. Freecam can be toggled with `mom_freecam`. When your timer is running, the `noclip` command acts like `mom_freecam` instead.
- Added support for automatically starting a third-person replay of your chosen comparison run when your timer starts so you can race it (toggle with the `mom_tv_replay_comparison_show` ConVar).
- Implemented a custom Momentum Mod player model in place of the placeholder shapes.
- Added the `mom_respawn` command, which teleports the player to the map spawn location.
- Defrag's CPM, VQ3, and Vintage movement configurations are now their own game modes.
- The still-unimplemented Tricksurf and Parkour game modes are no longer listed in-game and will be revisited later.
- `sv_noclipspeed_duck_multiplier` and `sv_noclipspeed_sprint_multiplier` can now be used to increase noclip speed above the unmodified speed.
- Air friction applied while noclipping is now controlled by the new ConVar `sv_noclipfriction`, which can be freely customized.
- You can now exceed `sv_maxvelocity` while noclipping.
- Added in-game tools for exploring and modifying entities which commonly need adjustments before the map can be made official. For example, the tools make it easy to assign the "keep negative Z velocity only" mode to the correct teleports on a surf map, or to quickly substitute `trigger_push` start boosts with the more robust `trigger_setspeed`.
	> These tools can be accessed with `devui_show entitytools`.

- The map selector is now always browsed in a single game mode at a time.

- Added `mom_screenshot_official` command, which takes a screenshot using the screen resolution and other settings required for official map screenshots.
- Fixed being able to move while inside areas that should be solid, including outside of the world.
- Added `mom_mv_check_ground_quadrants` movement ConVar.
- Added `mom_mv_use_goldsrc_conc_movement` ConVar.
- Added `mom_tv_replay_save_mode` ConVar. This controls which replays are kept permanently when saving. Setting this to 0 will keep all replays, and 1 will keep all personal best replays.
- Added `mom_tv_replay_expiration` ConVar. This controls how long temporary replays are kept (in days).
- Added `mom_hud_endofrun_autoshow` ConVar. This can be used to toggle the end of run menu automatically displaying when completing a run.
- Added `mom_play_jump_sound` ConVar. Enabling this will make a sound play when you jump.
- Added mounted asset priority detection. Maps that use more assets from one game will prioritize loading assets from that game. This means maps like rj_quba will no longer use HL2 textures for the glass walls.
- Added a map selector gallery component for viewing official map screenshots.
- Additional UI and infrastructure improvements and small bug fixes!
