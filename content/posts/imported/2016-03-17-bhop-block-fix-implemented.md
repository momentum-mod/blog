---
markup: html
date: '2016-03-17T23:21:01+00:00'
draft: false
categories:
 - photo
tags: 
 - Momentum
 - GameDev
 - Bhop
 - Fixes
 - Source
title: 'Bhop Block fix implemented'
showDate: yes
url: /post/141225132564/bhop-block-fix-implemented
---

<p>We’ve finished adding a fix for bhop blocks made using func_door and func_button entities, commonly found in older maps.&nbsp;</p><p>Similar to the <a href="https://forums.alliedmods.net/showthread.php?p=808724">mpbhops </a>plugin for CS:S/CS:GO servers, our system finds bhop blocks made using func_door or func_button entities, and then locks them from moving. We then check the time that the player is touching the entity, and teleport them if they are touching the bhop block for too long. This fix prevents the doors from boosting the player’s height 

 or slowing the player randomly 

as they move.&nbsp;<br></p><p>Our system uses ray-tracing and a custom entity enumeration filter to find the teleport trigger associated with each block, making it orders of magnitude faster than the older server plugin implementations that this fix is based on. The mpbhops plugin iteratively checks every single teleport entity against every single bhop block 

in the map, while Momentum’s ray-tracing method will find the correct teleport entity in only one step. The difference is N vs N³.</p><p>You can try the latest build for yourself on our <a href="https://github.com/momentum-mod/game/releases">Github releases page</a></p><p>-Momentum Mod Team</p>