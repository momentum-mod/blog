---
draft: false
showDate: true
date: 2024-08-08T09:22:39+00:00
title: 0.9.33 Changelog
---

Hey all, we have some fixes and changes over the past month while we're still working on 0.10.0!
Engine devs have been working a ton on Hammer related things, so this should help fix some crashes and issues, and adds things like MP3, FLAC, and OGG support in Hammer (Strata has supported these formats for a while now)!

### Added (7)

- Added FLAC and OGG to Hammer's sound browser for raw files
- Added MP3, FLAC, and OGG preview support to Hammer
- Added `snd_thread_mode 2` for updating audio separately from the main thread
- Added support for `$basetexturetransform` to VRAD `-textureshadows`
- FOV converter in settings ([game/issues/2126](https://github.com/momentum-mod/game/issues/2126))
- Ported Hammer's Run Map Configurations dialog to Qt and added "Move Up" and "Move Down" buttons
- Ported Hammer's Run Map Expert dialog to Qt
### Fixed (10)

- Audio pitch will no longer be modified when host_timescale is not equal to 1 and cheats are disabled
- Fixed Hammer Entity Report dialog selecting multiple entities
- Fixed Hammer sound browser not autoplaying the selected sound when the selection was changed with arrow keys
- Fixed `func_movelinear` sounds getting stuck looping forever if interrupted or removed
- Fixed `func_tracktrain` getting stuck when not using `Instantaneously`
- Fixed `trigger_look` firing whenever touched
- Fixed crosshair scaling with `cl_portal_crosshair_scale`
- Fixed duplicate extensions being appended to tool modules in the tool load dialog
- Fixed props not rendering at `(0, 0, 0)`
- Re-enable `mat_buffered_primitives` by default on Linux. This may result in a small performance boost.
### Improved (5)

- Allow negative noise in the displacement noise dialog
- Hammer now uses the same audio system as the game. This allows rndwave, sound operators, and more to function correctly
- Made width/height key on the root SVG element optional. Dimensions can now be parsed from the `viewbox` attribute.
- Moved `func_movelinear` sound handling to client side
- Replaced `host_threaded_sound 1` with `snd_thread_mode 1`
