

### Fixed (10)

- Fixed crash at surf_mesa spawn
- Fixed crash when building cubemaps if none are present in the map
- Fixed crashes observed on surf_classics
- Fixed crashes observed when mounting CS:S
- Fixed fog being inconsistent in PBR shader
- Fixed mat_showcamerarendertarget not working
- Fixed screenshots not working with antialiaising enabled
- Fixed text in Hammer being blurry
- JS Exception in chat.js ([game/issues/1958](https://github.com/momentum-mod/game/issues/1958))
- Visual artifacts in surf_summer spawn area (resulting from incorrect depth blur)


### Improved (5)

- Ammo HUD: Use dialog variable ([game/issues/1955](https://github.com/momentum-mod/game/issues/1955))
- Depth resolve (and r_depthoverlay) implemented in DX11
- Devices that do not support DX11 will no longer try to boot the game (and crash)
- Linux loading performance should be greatly improved
- Port Depth of Field shader to dx11 ([game/issues/1952](https://github.com/momentum-mod/game/issues/1952))
