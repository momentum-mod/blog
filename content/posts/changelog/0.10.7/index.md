---
draft: false
showDate: true
date: 2026-05-11T23:39:49+00:00
title: 0.10.7 Changelog
---

### Featured Maps (1)

- We've added a new experiment to the map selector called "Featured Map Lobbies". Every hour, three maps are selected for each gamemode which are displayed at the top of the map selector. The idea is to give players looking to play with others a small set of maps to gravitate towards, much like the dedicated servers on other Source games. In the future, we are hoping to have extra incentives or social features for these maps to ensure they are a reliable multiplayer hotspot. Please leave suggestions or other feedback for this feature in Discord!
### Added (8)

- Added "Meet Your Maker" achievement unlock logic
- Added +ducktap bind for HLBhop. Use this bind to duck automatically when touching the ground.
- Added GetWindowDimensions to Panorama GameInterfaceAPI
- Added `SetSvgTextureSize( width, height )` to Panorama ImagePanel class to allow resizing SVG images
- Added `slopescale` property to lights, which allows mappers to tweak the shadow bias slopescale value per light, which can help to reduce shadow acne
- Added support for Fairy Tale Busters APK pack files
- Added support for Quake/HROT PAK pack files
- Added zoning option for negating a zone filter which is combined with the filter's inherent negate property
### Fixed (26)

- Entities not in FGDs will still transform `origin` and `angles` keyvalues
- Fix `ent_bbox` and other commands not working.
- Fix `parallax_obb` entities when inside instances.
- Fix orientation of Hammer entity sprites when inside rotated instances.
- Fix trigger_gravity switching gravity direction sideways on old maps (in particular Portal 1's ending).
- Fixed !savestate/!saveloc not opening the savestate menu
- Fixed FOV resetting on timer restart in Defrag modes
- Fixed `color_correction_volume` not working at all
- Fixed an issue where Panorama CSS aspect ratio classes were not being applied properly
- Fixed an issue where the timer would seemingly reset to 0 seconds when entering a new zone
- Fixed crash when loading maps as an unauthenticated user
- Fixed crashing when spectating a player that respawns
- Fixed leaderboards not reloading when selecting the same map in a different mode on the map selector
- Fixed logic for max-distance rocket traces to properly account for up-close shot angles
- Fixed player avatar not displaying while in free roam spectate
- Fixed player not respawning in start zone in Defrag modes
- Fixed png screenshots not looking right on map with HDR and postprocess effects
- Fixed some maps not properly parsing entities and crashing
- Fixed toggled inputs not resetting with the timer reset
- Fixed trigger edgebug prevention on the Conc gamemode
- Fixed various crashes e.g. when zoning or exiting the game
- Jump speed in areas where full bhopping is not allowed is now capped to exactly the maximum groundstrafe speed, rather than slightly less than that speed
- `ai_scriptconditions` now works properly in multiplayer, evaluating conditions individually on each player.
- `env_projectedtexture` now obeys `r_flashlightbrighness` again.
- Fix missing 'slope scale' on `env_projectedtexture.
- Fix `ent_fire !name`s failing due to case-sensitivity.
### Improved (14)

- Add 'stop' button to sound fields in Hammer.
- Added argument names to VScript functions in `script_help`, as well as the Wiki.
- Added tooltips to Hammer's Entity Find/Replace dialog
- Allow bhopping in start zones with the timer running on the Bhop gamemode
- Apply `ent_text` autocomplete to all other `ent_*` debug info toggle commands.
- Avoid overriding `$color` and `$alpha` when overlays are tinted.
- Enable mom_mv_fix_uphill_slopes in Bhop (HL1)
- Fall back to older DPI modes on Windows if PerMonitorV2 is unsupported
- Fix performance for Hammmer's Entity Report dialog, add more detail to listed entities, allow sorting
- Improved game launch speed for users with many map files across all mounted games
- On Surf, autohop is now only active in areas where you are actually allowed to bhop (jump with uncapped speed)
- Players in your lobby are now added to Recently Played on Steam
- Startup videos should now render at lower framerate
- The limits for overlay count, face count and render order have been mostly removed. Render order is now limited to 65536, while both others can have up to 2 billion.
