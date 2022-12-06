---
title: "0.9.3 Changelog"
date: 2022-12-05T06:47:06-05:00
showDate: true
draft: false
---

## Take Me Higher

After some feedback from [the prior release](../0.9.2), we've raised the `models` and `brushes` limits even further! They were not scaled appropriately in proportion to the other limits that were raised. I've also added the `displacements` limit, forgot that in the previous table, sorry about that!

| **Lump/Data Limit** | **Old (BSP v21)** | **New (BSP v25)** | **Magnitude Increment** |
| ------------------- | ----------------- | ----------------- | :-----: |
| Grid size (units in axis) | 32768 | 131072 | 4x |
| models | 1024 | **65536** | 64x |
| brushes | 8192 | **131072** | 16x |
| brushsides | 81920 | 655360 | 8x |
| planes | 65536 | 1048576 | 16x |
| vertexes | 65536 | 1048576 | 16x |
| nodes | 65536 | 1048576 | 16x |
| texinfos | 12288 | 0 (unlimited) | ∞ |
| texdata | 4096 | 16384 | 4x |
| faces | 65536 | 1048576 | 16x |
| HDR faces | 65536 | 1048576 | 16x |
| origfaces | 65536 | 1048576 | 16x |
| leaves | 65536 | 1048576 | 16x |
| leaffaces | 65536 | 1048576 | 16x |
| leafbrushes | 65536 | 1048576 | 16x |
| areas | 1024 | 65536 | 64x |
| surfedges | 512000 | 2097152 | ~4x |
| edges | 256000 | 1048576 | ~4x |
| LDR worldlights | 8192 | 0 (unlimited) | ∞ |
| HDR worldlights | 8192 | 0 (unlimited) | ∞ |
| leafwaterdata | 32768 | 32768 | 1x |
| waterstrips | 32768 | 1048576 | 32x |
| waterverts | 65536 | 1048576 | 16x |
| waterindices | 65536 | 1048576 | 16x |
| cubemapsamples | 1024 | 16384 | 16x |
| overlays | 1024 | 16384 | 16x |
| **displacements** | **32768** | **262144** | **8x** |
| edicts | 2048 | 8192 | 4x |


## Full Changelog
{{% readfile file="posts/changelog/0.9.3/data/changelog.md" markdownify="true" %}}