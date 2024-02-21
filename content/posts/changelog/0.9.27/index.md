---
draft: false
showDate: true
date: 2024-02-21T03:58:50+00:00
title: 0.9.27 Changelog
---

Hi all!

This update removes the dreaded -mapping launch option, so Learn section, zoning commands and various convars like host_timescale can be used without it, so long as you have sv_cheats set to 1. This refactor was a major item of our 0.10.0 todo list, but made sense to get into the Steam branch straight away.

Also, this update should *actually* fix Defrag movement. It's been a very hard bug to replicate and fix, but this time we think we've finally squashed it :)

### Refactored (1)

- Removed -mapping and replaced it with sv_cheats
### Added (2)

- Added 2 new launch arguments, `-display` to select which monitor the game will start on, and `-adapter` to select which GPU the game will render with
- Added new VProf UI, perf counters UI and VProf report generator UI. The old VProf tree UI has been removed in favor of the new UI.
### Fixed (4)

- Fixed certain datamodel files not loading on Linux
- Fixed file lookups on Linux occasionally failing
- Fixed model browser stretching
- Made Defrag cvars use CPM values by default instead of VQ3 values
### Improved (6)

- Added new categorization method for imgui windows. Should be easier to navigate now.
- Improved Panorama stability and logging
- Improved performance when resizing the game window
- Removed the launch argument `-debugstartupscreen`
- The ambient light cache is now rebuilt for changes in map revision
- The ambient light cache version has been increased to 3
