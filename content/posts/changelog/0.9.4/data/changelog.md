

### Fixed (7)

- Fixed `4088 bytes` memory allocation issue on certain maps
- Fixed crashes when loading maps with portals in them
- Fixed defrag HUD elements not updating when `mom_df_hud_accel_enable` is OFF.
- Fixed incorrect output from texture conversion
- Fixed js error caused by attempting to set css values to `NaN`px.
- Fixed water rendering in skybox, for maps like ahop_coast
- Water fog value for `watercheap` shader is properly fetched


### Improved (2)

- BSP v25 edges raised from 256,000 to 4,096,000 (16x)
- BSP v25 surfedges raised from 512,000 to 8,192,000 (16x)
