---
draft: false
showDate: true
date: 2023-08-15T09:56:30+00:00
title: 0.9.19 Changelog
---

### Console (8)

- Console autocomplete and history can now be navigated with tab and shift+tab, like in other games
- Console input is now immediately filled in when navigating the autocomplete menu
- Autocomplete now correctly shows the first 100 results alphabetically out of all matches, instead of just the first 100 found
- Input history no longer saves empty or duplicate inputs
- The backtick key (\`) will now always close the console if it is open (controlled by `con_backtick_always_closes`)
- Closing the console now also automatically closes the game menu
- Pressing ESC will now clear the console input box if it has text, otherwise it will close the console
- Closing the console no longer clears the input box automatically
### Added (1)

- Exposed `SetSelected(bool)` on `RadioButton` in Panorama JavaScript API
### Fixed (2)

- Fixed Panorama UI controller movement always moving right no matter the input direction
- Fixed shaded textured view not working
### Improved (10)

- Hammer fix map dialog now will try to warn about unused keyvalue typos of existing keyvalues are not set, instead of suggesting to remove them
- Hammer options dialog now only saves settings when pressing OK button
- Hammer options dialog now updates 2D/3D views when changing visual settings
- Opening Console Opens Main Menu ([game/issues/1966](https://github.com/momentum-mod/game/issues/1966))
- Panorama xml parsing errors should now give more context to the error
- Remove blank lines from console history ([game/issues/1972](https://github.com/momentum-mod/game/issues/1972))
- Updated Conc models and textures ([game/issues/2090](https://github.com/momentum-mod/game/issues/2090))
- Updated Railgun sound ([game/issues/2089](https://github.com/momentum-mod/game/issues/2089))
- Updated explosion decals ([game/issues/2091](https://github.com/momentum-mod/game/issues/2091))
- [Console] Investigate improving tab autocomplete behavior ([game/issues/1776](https://github.com/momentum-mod/game/issues/1776))