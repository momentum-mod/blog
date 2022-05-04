---
markup: html
date: '2016-06-19T00:50:42+00:00'
draft: false
categories:
 - photo
tags: 
 - MomentumMod
 - GameDev
 - SourceEngine
 - Bhop
 - Surf
title: 'How the Momentum Mod timer works (how to get a time with 6 digits of precision on a 100 tick server)'
showDate: yes
url: /post/146131743729/how-the-momentum-mod-timer-works-how-to-get-a-time-with-6-digits-of-precision-on-a-100-tick-server
---

<p>As many bhoppers and surfers are aware, the smallest interval of time that can be calculated by a Source Engine server is the interval between two ticks, proportional to the tickrate set by the server owner. The server tickrate is just the server’s ”framerate” for simulating movement, physics, and other game logic. 

<i>Note:</i> <i>bhop and kz servers use 100 tickrate, and surf servers use 66 tickrate. This means every tick takes<i> 0.01 seconds. On a 66 tick server, this “interval per tick” is 0.015 seconds.&nbsp;</i></i></p><p>

The game engine updates once per tick, and only once. This means that the server tick rate is the fastest rate in which new information can be processed by the game engine. The player’s position will only update exactly once per tick interval, meaning the game will check to see if it should start the timer only once per tick interval.</p><p>Thus, the most precise timer possible in Source Engine is bound to the tickrate of the server, with a maximum precision of 0.01 seconds (two decimal places) on a 100 tick server. This is evident in almost all SourceMod-based timers, which can only have two decimal places of precision. However, Momentum Mod’s timer is precise to 6 decimal places (the upper bound for precision on 32 bit floating point numbers). So, how exactly do we achieve this?</p><p>Momentum Mod’s timer works by first calculating time the “standard way”, by taking the total elapsed tick count when the player exits the start trigger, and subtracting this from the total elapsed tick count when the play enters the ending trigger, resulting in the total server tick count of the run. We can get the real time from this value by multiplying by the interval per tick. We then&nbsp;“fix” this value using our custom-made timer precision fix system.</p><p>When the player leaves the start trigger, it takes a fraction of a single tick for the server to register that the player has stopped touching the starting trigger and record the starting tick count. Using the player’s current velocity, we can calculate what this fraction of time was and use it to offset the total time, resulting in an extremely accurate timer.&nbsp;</p><figure data-orig-width="512" data-orig-height="256" class="tmblr-full"><img src="https://68.media.tumblr.com/bb82e2210cecf11bab1f9e9b7a5d7722/tumblr_inline_ou31uoX8YN1qiwjjq_540.png" alt="image" data-orig-width="512" data-orig-height="256"></figure><p>We calculate this&nbsp;“tick interval offset” by tracing a ray opposite of the player’s current direction, starting from the player’s position on the tick that the server registers that they have left the zone. Combined with the current velocity of the player, the length of this ray can be used to calculate the amount of time that has passed since the player&nbsp;<i>actually </i>left the zone. We store this&nbsp;“tick interval offset” and add it from the total time after the run has finished. We apply the same process for the ending zone, only in reverse, subtracting 

(1 tick - (offset calculated)) to remove the time the player was inside the trigger before the server registered that they were touching it.&nbsp;<br></p><p>

In our testing, this tick interval offset ranged anywhere from 0.001 seconds to almost a full tick, and the distance was anywhere from 0.10 units to 2 units.

<br></p><p>A small technical detail that made this method confusing was the fact that collision with triggers is calculated using the player’s bounding box, whereas the player’s origin is the world space center of the bounding box. Therefore, we trace eight rays, one from each corner of the player’s bounding box, and use the shortest distance trace as the offset distance. This accounts for the player leaving the trigger from any direction and at any angle.</p><figure data-orig-width="256" data-orig-height="256"><img src="https://68.media.tumblr.com/72feb309a10276bf0b2db22ddbd1720b/tumblr_inline_ou32izKrcQ1qiwjjq_540.png" alt="image" data-orig-width="256" data-orig-height="256"></figure><p>This time precision fix is included in the upcoming test build, 0.4.0-prealpha. We only have a few more features to work on before the public alpha is released, so if you have been containing your hype until now, it might be time to start letting it out a little...</p><p>Finally, an announcement. We now use POEditor to help keep track of localization tokens for translating Momentum Mod into different languages. If you would like to get involved in development of Momentum Mod and know a language other than English, please sign up on our POEditor team! We appreciate your help immensely.&nbsp;</p><p><a href="https://poeditor.com/join/project/NsticU7iCc">https://poeditor.com/join/project/NsticU7iCc</a><br></p><p>That’s all for now!&nbsp;</p><p>-Momentum Mod Team</p>