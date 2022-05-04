---
markup: html
date: '2016-04-15T05:04:13+00:00'
draft: false
categories:
 - photo
tags: 
 - Momentum
 - GamDev
 - Source
 - prealpha
 - update
title: '0.3.0-prealpha release'
showDate: yes
url: /post/142830781914/030-prealpha-release
---

<p>0.3.0-prealpha is a large update to the look and feel of Momentum. </p><p><br></p><p>Release notes:</p><ul><li>&nbsp;Completely overhauled UI</li><ul><li>Velocity is can now be colorized based on acceleration (togglable, on by default)</li><li>Added strafe sync numerical display and visual bar (also colorized)</li><li>&nbsp;Added keypress display with jump and strafe counter</li><li>&nbsp;Added dialog showing statistics after you complete a run</li><li>&nbsp;Added support to save run statistics per-stage as well as overall, which will be expanded upon in future updates</li><li>Added time splits for stages</li></ul><li>Changed main menu</li><ul><li>&nbsp;Font has changed</li><li>&nbsp;Custom settings panel for all of the new momentum-specific settings</li><li>&nbsp;Changed colors of all panels in the menu to align more with Momentum's color scheme and aesthetic.</li></ul><li>Overhauled start zones</li><ul><li>&nbsp;Start zones on bhop/kz maps limit your speed so you are encouraged to get a good edge when prestrafing out of the zone</li><li>Start zones on surf maps do not limit your speed unless you bhop inside the start zone. This is meant to encourage prestrafing in the center of the zone and falling out of the zone as fast as possible.</li></ul></ul><p>This marks a major release for us, as the “vguiruninfo_wip” branch merges 115 commits into the master! (wow.) It also marks our shift in focus to adding essential features such as run statistics and overhauling the UI to make the game look and feel professional.&nbsp;</p><p>The major body of work with this release was on polishing the UI, however the more important features are the run statistics. We now save the following stats for each stage, as well as overall, for every run completed:</p><ul><li>Average Velocity</li><li>Average Sync (based on keypresses)</li><li>Average Sync2 (based on acceleration)</li><li>Maximum Velocity</li><li>Jumps</li><li>Strafes</li><li>Prestrafe/Starting Velocity</li><li>Ending Velocity</li></ul><p>Here’s what the new UI looks like in-game:</p><figure data-orig-width="1600" data-orig-height="900" class="tmblr-full"><img src="https://41.media.tumblr.com/474d0f4473fdc4ac8ba1603337bea769/tumblr_inline_o5nsoeeWhH1qiwjjq_540.jpg" alt="image" data-orig-width="1600" data-orig-height="900"></figure><p>and here’s what the ending screen looks like:</p><figure data-orig-width="1600" data-orig-height="900" class="tmblr-full"><img src="https://40.media.tumblr.com/78e807e95cbc5c341ab89927d3f45b8a/tumblr_inline_o5nsozZzmL1qiwjjq_540.jpg" alt="image" data-orig-width="1600" data-orig-height="900"></figure><p>As always, you can download the latest release from our <a href="https://github.com/momentum-mod/game/releases/tag/0.3.0-prealpha">github releases page</a></p><p>That’s all for now! Stay tuned for more news, updates, and ramblings!</p><p>Momentum Mod Team</p>