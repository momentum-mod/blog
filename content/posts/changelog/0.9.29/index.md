---
draft: false
showDate: true
date: 2024-03-13T07:03:39+00:00
title: 0.9.29 Changelog
---

### Added (7)

- Added mom_df_cpm_rocket_method to control the calculation of horizontal CPM rocket knockback
- Added mom_df_cpm_rocket_thresh to control the horizontal CPM rocket knockback threshold
- Added mom_df_smooth_duck cvar to control whether ducking is smooth in Defrag
- Added mom_play_land_sound cvar to control landing sounds
- Added theming support for imgui
- Added Defrag hitscan (Shotgun & Gauntlet) weapons ([game/issues/1933](https://github.com/momentum-mod/game/issues/1933))
- Momentum can now play the MomPlayer.LandSoft and MomPlayer.LandHard sounds on landing.
### Fixed (2)

- Fixed crash when creating a prefab in Hammer
- Horizontal rocket knockback in CPM is now more lenient
### Improved (1)

- Ducking and unducking in defrag is now smoothly animated by default.
