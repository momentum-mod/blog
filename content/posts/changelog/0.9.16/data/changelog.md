

### Added (2)

- Added "Keep Horizontal Speed" and "Keep Vertical Speed" options to trigger_jumppad
- Added `cl_playeranimstate_transitions`/`sv_playeranimstate_transitions` cvars to enable transitions in player animations


### Fixed (7)

- Bhop stats broken in 0.9.15 ([game/issues/2083](https://github.com/momentum-mod/game/issues/2083))
- Disabling damage indicators does not work ([game/issues/2072](https://github.com/momentum-mod/game/issues/2072))
- Fixed defrag weapons not having a cooldown and not spawning projectiles in spectate.
- Fixed faulty logic causing IK to be unusable
- Fixed occasional crash that could happen when using playvol command
- logic_format doesn't work as intended ([game/issues/2031](https://github.com/momentum-mod/game/issues/2031))
- math_clamp does not OutValue current value ([game/issues/1925](https://github.com/momentum-mod/game/issues/1925))


### Improved (1)

- Removed devonly flag from showanimstate cvars
