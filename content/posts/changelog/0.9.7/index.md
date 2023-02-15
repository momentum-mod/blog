---
draft: false
showDate: true
date: 2023-02-15T01:41:10-08:00
title: 0.9.7 Changelog
---

Hello all!

Apologies on the delay of this update, we plan to get right back on schedule with our release cadence. We've got a bunch of goodies for you, along with two breaking changes:

- **DX11 is now the only way to play the game, as DX9 has been removed**
- **DXVK was updated to latest (v2.1), which requires a GPU that can run Vulkan 1.3 (use [this site](https://vulkan.gpuinfo.org/) to see if your GPU is compatible)**

As mentioned in some Q&A streams, while we aren't planning on making a graphically intensive game, we are keeping the Chaos engine (and therefore Momentum Mod) up to date with regards to graphics in order to to aid in debugging efforts, take advantage of performance improvements, and better futureproof our codebase. We apologize for any inconvenience this may cause, however, hardware that does not support DX11 is perhaps hardware that should most likely be replaced nowadays.

# Full Changelog

{{% readfile file="posts/changelog/0.9.7/data/changelog.md" markdownify="true" %}}