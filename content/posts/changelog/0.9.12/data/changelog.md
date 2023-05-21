

### Added (4)

- Add speed mode for player_speed entity
- Added minimum speed threshold for calculating strafe synchronizer bar display (Settings > Interface > Synchronizer)
- Added strafe synchronizer functionality in Surf
- Damage boost time and slick time are now sent to UI


### Fixed (14)

- Crash when using bind command in console
- Defrag: Allow players to chain double jumps ([game/issues/2052](https://github.com/momentum-mod/game/issues/2052))
- Defrag: Allow players to jump when crouching under obstacles ([game/issues/2053](https://github.com/momentum-mod/game/issues/2053))
- Defrag: Damage boost pickup now gives damage boost effect instead of haste
- Defrag: Fix sticky stepup in CPM ([game/issues/1844](https://github.com/momentum-mod/game/issues/1844))
- Defrag: Funkyboosts now work in Defrag CPM
- Defrag: Removed machine gun recoil
- Fixed "_restart" not restarting the game (https://github.com/StrataSource/Engine/issues/732)
- Fixed crash when sprite helper would have invalid model and parent tried to change scale kv
- Fixed failing to create swapchain on some hardware
- Fixed map instance resolution under Linux
- Fixed model helper trying to use non-uniform scale on non-prop_static entities
- Fixed some models not rendering in hammer
- Fixed some rare cases of entity IO string corruption


### Improved (4)

- Calculation for ideal yaw rate has been generalized to include ground case (prespeed)
- Entity IO can now send values of any data type to string inputs
- HDR cubemaps are now stored in BC6H format
- Improve synchronizer functionality ([game/issues/2044](https://github.com/momentum-mod/game/issues/2044))
