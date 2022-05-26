---
markup: html
date: '2017-01-22T21:09:28+00:00'
draft: false
categories:
 - photo
tags: 
 - MomentumMod
 - SourceEngine
 - gamedev
 - Update
title: '0.6.2-prealpha released!'
showDate: yes
url: /post/156231196844/062-prealpha-released
---

<p>0.6.2-prealpha is another (relatively) small update that provides some new features, a preview of 0.7.0, and a bunch of fixes for bugs reported in 0.6.1.<br></p><h2><b>You Got a Purdy Map</b></h2><ul><li>Saul Rennison's Dynamic RTT Shadows<br></li></ul><p>Thanks to the very generous Saul Rennison, we were able to implement <a href="https://developer.valvesoftware.com/wiki/Dynamic_RTT_shadow_angles_in_Source_2007">his Dynamic RTT Shadows code</a> to make shadows casted by world lights be more accurate. A comparison can be shown below:</p><p><b>Before</b>:</p><figure data-orig-width="1600" data-orig-height="900" class="tmblr-full"><img src="https://68.media.tumblr.com/820ba8ba4c1bc9daa855f0ea074824ed/tumblr_inline_ok796aFqXa1u33hai_540.png" alt="image" data-orig-width="1600" data-orig-height="900"></figure><p><b>After</b>:</p><figure data-orig-width="1600" data-orig-height="900" class="tmblr-full"><img src="https://68.media.tumblr.com/82bdf9b5627d3b80af34ef57b2486c8b/tumblr_inline_ok7972HLnk1u33hai_540.png" alt="image" data-orig-width="1600" data-orig-height="900"></figure><p>These are applied to lights automatically, for every map in the mod, including old ones! One noticed map was one of Valve’s default CS:S maps, cs_assault.</p><ul><li>Brian Charles' Parallax-Corrected Cubemaps</li></ul><figure data-orig-width="445" data-orig-height="250" class="tmblr-full"><img src="https://68.media.tumblr.com/930ae08ad60e2774ba2e177ad03d64f4/tumblr_inline_ok798igzs11u33hai_500.gif" alt="image" data-orig-width="445" data-orig-height="250"></figure><p>Similarly, thanks to the very generous Brian Charles, we have implemented his parallax-corrected cubemaps for the Source Engine. This allows for more accurate reflections for cubemaps on world geometry, as seen <a href="https://www.youtube.com/watch?v=ZH6s1hbwoQQ">in his video</a>. A tutorial will be available for mappers looking to implement this in <a href="https://github.com/momentum-mod/level-design">the level-design repo</a>, but it should be noted that since Valve does not allow modders to override base shaders found in the game, it will not apply to every map! These cubemaps only apply to any material using the SDK_LightmappedGeneric shader. If old maps want this functionality, either the map needs recompiled with the new shader on the materials in the map (annoying), or Valve must grant modders the power to override base shaders (unlikely).</p><p>You can see both of these new features working in the triggertests map!</p><h2><b>Small Features Added</b></h2><p>We’ve received a bunch of input along the way, leading to small features here and there, all of which don’t necessarily deserve their own major release, so we’ve bundled them with 0.6.2:</p><ul><li>Disabled inputs - The keypress HUD element now shows disabled keys set by <b>trigger_momentum_limitmovement</b><br></li><li>Invalid run start - A sound now plays if the run cannot be started (will be expanded upon in the future).</li><li>Checkpoint saving - Maps save which checkpoint you were on when you end the map.</li><li><b>mom_punchangle_enable </b>- Landing punchangle has been disabled by default now, and can be scaled (if desired) by this convar.</li><li><b>mom_speedometer_colorize 2</b> - New colorization method suggested by Acta</li><li><b>mom_stage_tele</b> - Teleport to the start of a specific stage number (1 = start)</li><li><b>showRuler</b> - Shows a menu to measure distance in-game (in units)</li><li><b>sv_gravity</b> - Allow players to change gravity in-game.</li><li><b>sv_tickrate</b> - In-game tickrate changes force the level to reload now, allowing replays of different tickrate to be played.</li></ul><h2><b>RIP Tim, You Shall Be Missed</b></h2><p>“<i>If a man has not discovered something that he will die for, he isn't fit to live.</i>” – <b>MLK, Jr.</b></p><ul><li>.tim files are completely removed, in favor of reading replay files<br></li></ul><p>As we get closer to Alpha, our file formats will start to be somewhat finalized. With this process, we remove our old skeleton/proof-of-concept code, and in this update, we’ve murdered Tim. Tim was a good friend of ours, allowing us to store times in a convenient manner, but as we began to finalize the replay files, we started to realize we didn’t really need Tim anymore. </p><p>So, with this update, you can delete all your old .tim and .momrec files, since the former is no longer used, and the latter was changed in this update.</p><h2><b>Yet To Come</b></h2><ul><li>Overhauled Map Selector (0.7.0)<br></li></ul><p>We’ve included a preview of what the new map selector is going to look like. The UI is nowhere near complete, since the majority of the work requires the companion web API for selecting/downloading online maps, as well as storing a bit more information about maps, like author and difficulty.</p><h2><b>Fixes</b></h2><p>Of course, this wouldn’t be considered a minor update without any bug fixes, and there’s quite a few that we found:</p><ul><li>Fixed credits.bsp's invalid textures</li><li>Fixed crash when running mod in Offline mode on Steam (thanks .Enjoy!)</li><li>Fixed lots of minute bugs in Linux (fonts, layouts, etc) [more to come!]</li><li>Fixed bug with main menu buttons animating even when not in focus</li><li>Fixed <b>sv_tickrate</b> now updating when set by gamemode code</li><li>Fixed bug with start zone exit velocity</li><li>Fixed bug with mounted maps not properly loading sounds packed in the map when on a separate drive</li><li>Fixed bug with checkpoints saving out of order when the player had &gt; 10 checkpoints</li><li>Fixed bug with timer layout with regards to stage time comparisons</li><li>Fixed various Valve slip-ups and optimized pristine 2004 code</li></ul><p><i><b>And we’ve fixed a few things under the hood to make development/mapping a bit better:</b></i></p><ul><li>Fixed smoothing groups not being applied to brushes (thanks tgnottingham!)</li><li>Fixed hammer not loading custom shaders (Thanks Biohazard!)</li></ul><hr><p>As always, you can find this release at our <a href="https://github.com/momentum-mod/game/releases">GitHub Releases page</a>. Don’t forget that there’s a feedback button in-game, and that you can also join <a href="https://discord.gg/wQWkRb6">our Discord server</a> for more immediate discussion! We hope to have 0.7.0 out eventually, if our work/university/life permits!</p><p>Happy surfing/hopping!</p><p>Team Momentum</p>