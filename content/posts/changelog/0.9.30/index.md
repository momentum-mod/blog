---
draft: false
showDate: true
date: 2024-04-08T06:56:36+00:00
title: 0.9.30 Changelog
---

Hi all! This update introduces some experimental water movement changes in TF2-based modes that we're looking for feedback on, which you can play with with `mom_mv_tf_flat_sharking 1` and different `mom_mv_tf_shark_vertical_speed` values. Get sloshin'!

### Added (3)

- Experimental sharking movement in TF2 based modes which removes water bobbing RNG
- mom_mv_tf_flat_sharking cvar to control sharking movement (defaults to 0)
- mom_mv_tf_shark_vertical_speed cvar to control how much extra speed to add to rocket jumps while sharking
### Fixed (14)

- Can fire stickybombs with zero ammo ([game/issues/2137](https://github.com/momentum-mod/game/issues/2137))
- Increased value of sv_max_allowed_developer to 99
- Increased value of sv_max_allowed_net_graph to 99
- Player can no longer fire sticky bombs in the buffer period when out of ammo
- Player can no longer instantly re-duck in RJ and SJ (fixes losing speed in some water jumps while crouching.)
- Player can now jump while crouched in TF2-based modes when autohop is enabled
- Sticky bomb launcher always consumes ammo when firing stickies
- Fixed -console showing the vgui console in panorama mode, and not working with the panorama console
- Fixed backslashes not working in older BSPs, and increased the entity lump version to 1
- Fixed being unable to switch back to default devui theme in the menu bar
- Fixed crash in the particle editor when attempting to add new item to the root particle node
- Fixed crash when loading malformed or missing VCDs
- Fixed issue in the particle editor on Linux related to adding new operators
- Fixed issue with dynamic mounts in Hammer when running in Wine or Proton
### Improved (4)

- All modes now produce soft and hard landing sounds
- mom_impact_view_punch_enable is no longer cheat protected
- mom_mv_disable_impact_view_punch is renamed to mom_impact_view_punch_enable and defaults to 0
- Misc engine stability improvements
