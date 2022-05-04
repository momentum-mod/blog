---
markup: html
date: '2016-03-05T03:17:22+00:00'
draft: false
categories:
 - photo
tags: 
 - Momentum
 - GameDev
 - Source
 - GameEngine
 - Multiplayer
title: 'Finished Switch to SDK Base 2013 Multiplayer'
showDate: yes
url: /post/140481349964/finished-switch-to-sdk-base-2013-multiplayer
---

<p>Yesterday the team finished our transition from SDK Base 2013 Singleplayer to SDK Base 2013 Multiplayer, marking a major checkpoint in the mod’s development. We can now put our entire focus on adding new features such as individual player and run statistics, replays, and more.</p><p>Momentum was envisioned as a Singleplayer mod with added in Multiplayer features such as global IRC chat, ghosts of other networked players on the same map, and leaderboards. The reasoning for this was such that players could play maps at their own pace and not have to worry about whether the server was going to switch maps, or if the map they wanted to play was currently being played on a public server.</p><p>However, in September 2015, Valve updated the Source Base MP engine (CS:S, DOD:S, HL2DM), and one of the included updates was static prop lightmaps (previously found in Black Mesa). Among other things, this means that additional keyvalues for each static prop in the map are added to the game lump of map’s bsp structure during compilation. Source SDK 2013 Singleplayer’s engine did not support these new keyvalues in the StaticPropLump structure, it would crash if you tried to load a map that had them. The result of this was that any map compiled after September for CS:S that contained any static props would crash Momentum! <i>Note: SDK Base 2013 Multiplayer doesn’t support the new static prop lighting by default, but the beta_test branch does, which will likely get phased into the main branch soon.</i></p><p>The other issue with going Singleplayer-only is that anti-cheat is a difficult problem to solve when both the client and the server are on the player’s local machine. The player could potentially do whatever they wanted since the <a href="https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking">server-authoritative nature</a> of Source Engine Multiplayer prevents the client from doing outrageous stuff; if the cheater has access to the server as well, this security is instantly removed.&nbsp;</p><p>Ultimately, we decided that it was best to switch to the SDK Base 2013 Multiplayer engine both to solve the issue of maps crashing, as well as insurance for the future, since we can now easily switch to a server-based play model. We still have yet to fully decide whether we want to keep the previous structure or switch to an entirely server-based model for the sake of anti-cheat.</p><p>That’s it for now! Stay tuned for more updates from the Momentum team!</p>