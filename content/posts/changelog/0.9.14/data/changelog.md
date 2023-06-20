

### Added (4)

- Added $.LoadKeyValues3File to load KV3 files
- Added Prime Sight HUD for Defrag
- Added `distvariance` sound parameter to sound scripts, allowing for distance blending to be tweaked instead of being tied to a cvar. Usage is `distvariance "near, far"`
- Re-enabled the following operators in the math_float sound operator:  asinh, atanh, acosh, expm1, expm2, log2, log1p, logb, erf, erfc, gamma, lgamma, rint, nearbyint, roundtol and trunc


### Fixed (8)

- Fixed 'scale' being applied to all entities in Hammer
- Fixed Linux dependency issues for Panorama
- Fixed MRU material list getting reversed on every Hammer launch
- Fixed MSAA trying to be applied even when driver reported no support
- Fixed cl_csm_debug_2d
- Fixed modelscale not updating when undoing in Hammer
- Fixed possible crash when trying to interact with map window during load
- Fixed solids not rendering in Hammer


### Improved (2)

- Changed Hammer config to text format
- Replaced OpenAL with SDL for voice recording and removed dependency
