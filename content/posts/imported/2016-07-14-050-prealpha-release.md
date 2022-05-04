---
markup: html
date: '2016-07-14T04:50:41+00:00'
draft: false
categories:
 - photo
tags: 
 - MomentumMod
 - SourceEngine
 - Surf
 - Bhop
 - Update
 - Prealpha
title: '0.5.0-prealpha release'
showDate: yes
url: /post/147378410384/050-prealpha-release
---

<p>It’s that time again! The Momentum Mod team has been hard at work on the latest update, 0.5.0-prealpha. 0.5.0 is an incremental update that overhauls many UI elements in the main menu as well as fixing some glaring issues with the previous builds.<b><br></b></p><p>By far the largest change is the new main menu design, which is based off of NicolasDe’s GameUI2 from his mod <a href="https://github.com/NicolasDe/project-9">Project-9</a>. Huge thanks go to Nicolas for letting us use GameUI2 in Momentum Mod. The background of the main menu has also changed from a very early alpha version of World 1 to a nearly complete Tutorial map to compliment the new aesthetic. </p><figure data-orig-width="1600" data-orig-height="900" class="tmblr-full"><img src="https://31.media.tumblr.com/6a0d7b38f467ed1dac9b424c46828b83/tumblr_inline_oaafuceZ4y1qiwjjq_540.gif" data-orig-width="1600" data-orig-height="900"></figure><p>0.5.0 also introduces an overhauled momentum settings panel and a brand-new in-game contact/feedback panel.<br></p><figure class="tmblr-full" data-orig-height="499" data-orig-width="893"><img src="https://67.media.tumblr.com/1d707e522e59ac37c3f219890c690900/tumblr_inline_oaafuvKOYY1qiwjjq_540.png" data-orig-height="499" data-orig-width="893"></figure><p>In addition to the new UI elements, 0.5.0 fixes some glaring issues with the previous implementation of the accurate timer. Some players reported that the tick offset was not being calculated on Surf maps where the player falls out of the start zone. This problem was a symptom of a bigger problem, which was that we always started the offset raytrace from the bottom of the player’s bounding box. Because of this, when the player fell out of a trigger, the last part of their collision hull that was touching the trigger was actually the top part, not the bottom, and thus the trace would never hit the trigger and record the time offset. </p><p>To fix this, we implemented a new system for doing the ray trace. We trace from all 8 corners of the player’s collision hull, isolate the shortest ray that was traced (since the shortest ray will be sent from the corner that was touching the trigger last), and use this for our time calculations. </p><p>Finally, you can now right click when the in-game leaderboards are open (tab menu) and right click a time to play the replay for that time, right from the leaderboards! Much more functionality will be added when the times leaderboard gets hooked up with online times in a coming update. </p><figure class="tmblr-full" data-orig-height="413" data-orig-width="672"><img src="https://66.media.tumblr.com/72649d93420f62748acefaac438e4b22/tumblr_inline_oaafz1AdIL1qiwjjq_540.png" data-orig-height="413" data-orig-width="672"></figure><p><b></b></p><p>As always, the latest version is available on our <a href="https://github.com/momentum-mod/game/releases">Github release page</a>.</p><p>That’s all for now! Stay tuned for more updates from the Momentum Mod team.</p>