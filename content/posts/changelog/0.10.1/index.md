---
draft: false
showDate: true
date: 2025-10-09T06:52:27+00:00
title: 0.10.1 Changelog
---

Hey there! We're really glad you all have been enjoying the public release.

We're hard at work fixing a lot of bugs, some of which (related to lobbies) are taking a bit longer than expected with finding the problems exactly. We believe it's something deeper in the Steam Networking library and are working on creating a bug report to submit to Valve.

In the meantime, please keep the feedback rolling in, and we will keep these updates rolling out!

### Added (3)

- Added Sprint button to Conc keypress UI ([game/issues/1590](https://github.com/momentum-mod/game/issues/1590))
- Added conc throw and throw cancel sound entries (no sounds yet) ([game/issues/2087](https://github.com/momentum-mod/game/issues/2087))
- Added mom_hide_players ConVar and /hide chat command for hiding other players ([game/issues/2506](https://github.com/momentum-mod/game/issues/2506))
### Fixed (15)

- Added workaround for SDL2/X11 bugginess with exclusive fullscreen windows. This makes "Fullscreen" and "Fullscreen Window" display modes identical unless -allowexclusivefs is passed
- Brought stickylauncher shoot behavior more in line with TF2 to fix "sticky jamming"
- Fixed being able to hear other players' run upload sound effect
- Fixed bugs with pose parameters, flexes and sequences in the Panorama model panel
- Fixed conc beeps not stopping when fizzling concs ([game/issues/2486](https://github.com/momentum-mod/game/issues/2486))
- Fixed context menus not closing when closing HUD tab menu (leaderboards) ([game/issues/1682](https://github.com/momentum-mod/game/issues/1682))
- Fixed crash when map is exited right after finishing a personal best run ([game/issues/2454](https://github.com/momentum-mod/game/issues/2454))
- Fixed issue where models in the Panorama model panel can be yeeted away by `LookAtModel()` calls
- Fixed rocket launcher always spawning an easter egg in certain conditions ([game/issues/2505](https://github.com/momentum-mod/game/issues/2505))
- Fixed rocket launcher easter egg not respecting mom_tf2_rocket_draw_delay ([game/issues/2171](https://github.com/momentum-mod/game/issues/2171))
- Fixed stickylauncher not respecting ammo checks in some cases ([game/issues/2455](https://github.com/momentum-mod/game/issues/2455))
- Max velocity not getting set to 0 (unlimited) when generated with Zonemaker
- Safe height not getting set to 0 (base of zone) when generated with Zonemaker
- Stickybomb launcher now fires a sticky upon charging->restarting to start zone->depress shoot button ([game/issues/2467](https://github.com/momentum-mod/game/issues/2467))
- Fixed the TF2 related launcher overrides to work with updated override weapon script logic ([game/issues/2473](https://github.com/momentum-mod/game/issues/2473))
### Improved (6)

- Detect player clips in zone vertex snap trace ([game/issues/2483](https://github.com/momentum-mod/game/issues/2483))
- Learn mode is temporarily disabled as we work on it more
- Improved visual clarity of PBR in Hammer's shaded textured polygons mode
- Removed +strafe decel ticks (+strafe nerf)
- Start timer when airborne in VTG ([game/issues/2503](https://github.com/momentum-mod/game/issues/2503))
- Zonemaker start zones now default to -1 max velocity (gamemode default)
