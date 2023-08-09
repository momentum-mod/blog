

### VPhysics Traces (6)

- VPhysics traces now report complete hit surface info
- Fixed VPhysics traces sometimes not hitting displacements, especially more axis-aligned ones
- Fixed VPhysics point traces not hitting brush entities
- Improved performance of VPhysics traces against displacements
- VPhysics traces now generally behave more like non-VPhysics ones
- Added `traceray_test` command for testing collision trace behavior


### Added (7)

- Added input for setting mouse sensitivity in distance per 360 ([game/issues/2047](https://github.com/momentum-mod/game/issues/2047))
- Added ConVar "traceray_force_vphysics" for testing (1 = Use VPhysics collisions for displacements, 2 = for everything)
- Added ConVar "traceray_unshrink_vphysics_brushes" which unshrinks VPhysics-type brush entities
- Added Railgun, Lightning Gun, and Machine Gun to Defrag
- Added `mom_df_knockback_method` cvar to control how the Defrag splash damage bounding box is calculated
- Added `mom_df_lg_damage` cvar to control lightning gun splash damage
- `mom_df_lg_radius` cvar to control lightning gun splash radius


### Fixed (5)

- Fixed crash when omitting certain child elements from the Panorama loading screen panel
- Fixed crash when popup-manager.xml is invalid (the game now exits with an error dialogue)
- Fixed hang on start when the engine is told to play an invalid startup movie
- Fixed rare possibility for a trace that starts inside a world brush or entity and then runs into a different entity to pass through that entity
- Use more accurate bounding box for splash damage in defrag.


### Improved (1)

- Reduced the number of required child elements for the Panorama main menu and intro movie
