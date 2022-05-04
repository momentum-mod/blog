---
markup: html
date: '2021-04-14T15:55:16+00:00'
draft: false
categories:
 - photo
tags: 
 - MomentumMod
 - momentum mod
 - SourceEngine
 - Counter-Strike: Source
 - counter-strike: global offensive
 - game development
 - game update
title: '0.8.8 - Bring the Chaos'
showDate: yes
url: /post/648455878647939072/088-bring-the-chaos
cover:
  image: 'https://i.imgur.com/gfQfrGj.png'
  alt: 'This is the cover'
  relative: false
---

<p>
<iframe src="https://gfycat.com/ifr/TastyFakeAnt" frameborder="0" scrolling="no" allowfullscreen="allowfullscreen" width="640" height="404"></iframe>
</p>
<p>
Why, <em>hello </em>there! :)
</p>
<p>
The last 4 months have been <em>massive</em> for the project. With getting access to the Source Engine&rsquo;s inner demons, the team has been hard at work porting the game to the Chaos Source engine, and we have some pretty big news regarding it, so strap on in!
</p>
<!-- more -->
<h2>Bring the Chaos</h2>

<p>
0.8.8 marks the first build of Momentum Mod on the Chaos Source engine branch. For those that may have missed <a href="https://blog.momentum-mod.org/post/636153097782280192/you-got-a-license-for-that">the previous blog post about it</a>, the Chaos Source engine branch is a CS:GO-based Source project being worked on by the Chaos Initiative team, which Momentum joined upon obtaining the engine license. Having an engine license opens the door for Momentum to be the best game it can be, and the team is very excited at what&rsquo;s to come! But let&rsquo;s talk about what we have, starting now, shall we?
</p>
<h3>Full Range of Map Compatibility</h3>
<p>
Momentum Mod can now load maps from <strong>Counter-Strike: Source</strong>, <strong>Team Fortress 2</strong>, <strong>Portal 2</strong>, and <strong>Counter-Strike: Global Offensive</strong>, all in one game. Momentum automatically mounts these four games as players have them installed, but as a reminder, <strong><em>they are not required to play the game</em>!</strong>
</p>
<p>
<iframe src="https://gfycat.com/ifr/ThoseSlimHydatidtapeworm" frameborder="0" scrolling="no" allowfullscreen="allowfullscreen" width="640" height="404"></iframe>
</p>
<p>
We will, in the future, update our map selector to show exactly which games would need to be installed to play maps that may use the assets from them. This can help players filter out maps made with assets from games they do not have installed. We will also have some tools to help condense the mounted games into tight VPKs to help reduce the need to have the full game installed, so stay tuned for that!
</p>
<h3>DirectX 11 Renderer</h3>


<p>
Resulting from the immense work of SlidyBat on the team, the Chaos engine (and therefore, Momentum) will be moving to a full DirectX 11 rendering backend by 1.0.0. In fact, 0.8.8 even has the initial version of this rendering backend implemented! Playtesters can opt-in with the launch parameter &ldquo;<strong>-shaderapi shaderapidx11</strong>&rdquo;. 
</p>
<p>
<a href="https://i.imgur.com/QSaRVaL.png"><figure class="tmblr-full" data-orig-height="139" data-orig-width="622" data-orig-src="https://i.imgur.com/QSaRVaL.png"><img src="https://64.media.tumblr.com/16fd76fa666f1119a43eeece1c70d914/ea7ac9053c36f18f-58/s540x810/1fc89d3dbfc04d70b2a76f0387227875f42a869b.png" alt="DX11 Launch Params" data-orig-height="139" data-orig-width="622" data-orig-src="https://i.imgur.com/QSaRVaL.png"></figure></a>
</p>
<p>
This is going to be a Windows-only feature for now as we work towards getting DXVK working for the engine, which aims to replace the ToGL abstraction layer for Linux. It is also expected to have some bugs to iron out on our way to 1.0.0!
</p>
<p>
But what does DX11 really mean for the game? Well, for one, Chaos shaders can take advantage of a more up-to-date rendering API, including things like tessellation. Being on <a href="https://en.wikipedia.org/wiki/High-Level_Shading_Language#Shader_model_comparison">Shader Model 5</a>, our shaders have updated limits and can take advantage of more modern features. For reference, the DX9+ToGL implementation in regular Source limits Windows to Shader Model 3, and Linux to Shader Model 2.0b. Working on things like the PBR shader started to become extremely limited, especially when trying to maintain cross-platform compatibility!
</p>
<p>
<a href="https://i.imgur.com/NgEUAJz.png"><figure class="tmblr-full" data-orig-height="1040" data-orig-width="1920" data-orig-src="https://i.imgur.com/NgEUAJz.png"><img src="https://64.media.tumblr.com/2475af0755ea6942ca32625e6e76c622/ea7ac9053c36f18f-bd/s540x810/9aeed1ed392706193e10174abd2fa04691671e18.png" alt="DX11 Debugging" data-orig-height="1040" data-orig-width="1920" data-orig-src="https://i.imgur.com/NgEUAJz.png"></figure></a> 
</p>
<p>
Also, it&rsquo;s no secret that the graphics debugging workflow for DirectX 9 (what every Source 1 game, including CS:GO, runs on) is pretty lackluster. The Chaos team is greatly looking forward to using more powerful graphics debugging tools like Visual Studio&rsquo;s Graphics debugger (seen above), or <a href="https://renderdoc.org/">RenderDoc</a> to be able to quickly and effectively find bottlenecks or issues in the graphics pipeline! Tools like this have even helped Slidy find bugs in the DX9 renderer while comparing the new renderer to the old one!
</p>
<p>
On the downside, Momentum Mod might not be able to run on your toaster anymore. In seriousness, while we understand the GPU availability situation nowadays, we will only be requiring players to have a graphics card from <a href="https://solidlystated.com/hardware/list-of-directx-12-and-directx-11-compatible-video-cards/">the last 12 years</a> (GTX 400 / Radeon HD 5000 series and up) to be able to play. I&rsquo;d like to reiterate that we understand Momentum is a game about <em>speed</em>, and we will not be going (too) crazy with making the game look incredible, especially not to the significant detriment of performance. High FPS deeply matters to us!
</p>
<h3>Panorama UI</h3>


<p>
Source 2 has enjoyed a much better UI system, called Panorama, than Source 1 has had over the years, called VGUI. CS:GO tried to get away from VGUI and even implemented Scaleform, a Flash-based UI system, before moving over to Panorama. With our access to the CS:GO engine, we now have full access to Panorama, and will be re-designing and re-implementing all of our VGUI-designed UI in this new framework. Below are only some of the mockups done by our UX designers TraZox and Isabella:
</p>
<p>
<a href="https://i.imgur.com/5iiE4hc.png"><figure class="tmblr-full" data-orig-height="1080" data-orig-width="1920" data-orig-src="https://i.imgur.com/5iiE4hc.png"><img src="https://64.media.tumblr.com/e1b4e7030b610ff684eb461a2e3af528/ea7ac9053c36f18f-72/s540x810/27b8e62702b23630622520ac393450cc4058ec2e.png" data-orig-height="1080" data-orig-width="1920" data-orig-src="https://i.imgur.com/5iiE4hc.png" alt="image"></figure></a>
</p>
<p>
<a href="https://i.imgur.com/Ol1cJOD.png"><figure class="tmblr-full" data-orig-height="1080" data-orig-width="1920" data-orig-src="https://i.imgur.com/Ol1cJOD.png"><img src="https://64.media.tumblr.com/3bacbee9f02d21de336676cfdc64fed4/ea7ac9053c36f18f-7f/s540x810/c64c6fd390dd21e454a477fc0c0600b90f71075d.png" data-orig-height="1080" data-orig-width="1920" data-orig-src="https://i.imgur.com/Ol1cJOD.png" alt="image"></figure></a> 
</p>
<p>
<a href="https://i.imgur.com/NYP469H.png"><figure class="tmblr-full" data-orig-height="1080" data-orig-width="1920" data-orig-src="https://i.imgur.com/NYP469H.png"><img src="https://64.media.tumblr.com/e4b32a2a961a83c03391abfea4f0b85d/ea7ac9053c36f18f-8f/s540x810/33d7a1d8756f40679ca1a5f49d6f4ed2586f1054.png" data-orig-height="1080" data-orig-width="1920" data-orig-src="https://i.imgur.com/NYP469H.png" alt="image"></figure></a>
</p>
<p>
Panorama is a web-like UI framework that allows us to iterate on our User Interface design, implementation, and functionality much much, <em>much</em> more quickly than VGUI ever had. 0.8.8 ships with the first version of the framework, but lacks the proper design and implementation of the main menu, which is coming in the next (0.9.0) version!
</p>
<h3>About That Hammer I Owe Ya!</h3>


<p>
As I talked about in <a href="https://blog.momentum-mod.org/post/637078284151275520/087-changelog">our previous changelog blog post</a>, SCell has worked on a ton of valuable Hammer features, now included by default with Hammer for Momentum Mod, some of which are listed below:
</p>
<ul><li>All controls no longer look like Win95

</li><li>Removed frame limiter

</li><li>QuickHide state can is saved

</li><li>Camera positions saved with map

</li><li>Scriptable brush creation tools

</li><li>Material proxies support

</li><li>Models scale depending on their "modelscale" keyvalue

</li><li>Multiple cordons

</li><li>Model browser now can show used models, also now has refresh button

</li><li>Entity report now has targetnames

</li><li>Material history saves between sessions

</li><li>QuickHide can be undo/redo'd

</li><li>If autosave directory path is invalid when changing settings, it defaults to hammer/autosaves

</li><li>Autsave now checks all open documents, and is run from another thread

</li><li>3D view mouse sensitivity slider

</li><li>Angle snapping in entity properties window

</li><li>Custom build window

</li><li>2D views color customization

</li><li>New mode for sculpt - project paint with image file (png, jpg, bmp, tga)

</li><li>Particle browser

</li><li>Keybind editor 

</li><li>Setting to disable alpha inversion for displacements

</li><li>Shaded 3D preview now doesn't flicker

</li><li>Translucent textures in texture browser are drawn transparent

</li><li>Discord integration

</li><li>Light keyvalues now print their value 3D view draws current skybox

</li><li>Scriptable primitive brush via AngelScript
</li>
</ul><p>
For those with a keen eye, you may have noticed a lot of these features are found in Hammer++ as well! These features were originally part of an open source repository SCell and I were working on, aiming to be a general SDK hammer of sorts, but ever since getting Source engine access, we had to remove that repository. Unfortunate, but understandable!
</p>
<p>
Though now with full engine access, our Hammer editor and related tools can be expanded to meet the needs of our mappers. We will be exploring increasing the Hammer and game coordinate grid to allow for bigger maps, direct in-engine integration for faster mapping iteration, and potentially improving tools like VRAD to use the GPU! Having just Hammer code is one thing, but having the code that Hammer and the engine both use is absolutely exciting. We can&rsquo;t wait to deliver a powerful mapping experience for Chaos mappers!
</p>
<h2>Delaying to Late 2021</h2>


<p>
I won&rsquo;t beat around the bush. While we did have a working build at the end of the year, it wasn&rsquo;t fully compatible and needed a lot of work still. Porting to the new engine, understanding the codebase, and getting to a comfortable 0.8.8 release point took a bit longer than expected.
</p>
<p>
Thus, <strong>we&rsquo;re deciding to push the 1.0.0 release back to December 2021</strong>.
</p>
<p>
I understand the disappointment that may arise from this, but urge you to keep in mind that the Summer 2021 deadline was before we had confirmed Source engine access. I would also like to remind everyone that this is a project being worked on by volunteers in their free time, and we are still doing our best to provide a clean, powerful launch of Momentum later this year.
</p>
<p>
I&rsquo;m going to take this time to roadmap exactly what&rsquo;s left, and why we&rsquo;re still absolutely confident in our 2021 release date. Note that this roadmap can be found at <a href="https://github.com/orgs/momentum-mod/projects">our GitHub organization page</a>, including more specific tasks being done.
</p>
<p>
For 0.8.8 (this release), the team has ported the game to be as close to 0.8.7 as possible on a completely new version of the Source engine. Despite this being a massive update, it&rsquo;s still functionally equivalent to 0.8.7, and is even fully backwards compatible with it, hence the 0.8.X designation. While it may seem like it was a simple copy-and-paste job, it was anything but, as we had to delve into the engine to compare what CS:GO does compared to branches like Portal 2 and Team Fortress 2 (SDK 2013). That is what took the most time for the past couple of months. But now, as proof by this release, we&rsquo;re comfortable with the engine and have Momentum running in an acceptable state!
</p>
<p>
Then comes the immediate next version, 0.9.0. 0.9.X releases can be considered the &ldquo;taking advantage of Source engine access&rdquo; updates. We will be implementing (mapper-placed) Portals, the initial Panorama UI, fixing things in our DX11 renderer, and so on. There will be sub-updates as needed, but once we have Panorama being worked on by our UI designers, the coders can move towards 0.10.0. Portals already exist in the codebase, the majority of the work will be the abstraction of the code to be able to be used by both P2:CE and Momentum. We expect these updates to take around a month or so.
</p>
<p>
0.10.0 is the Zone file refactor, alongside the Zone tooling update. We can parse zones from our Hammer, but the in-game zoning tools will also be expanded to support porting maps that don&rsquo;t need decompiling. There will be sub-updates as needed here as well, fixing bugs or implementing more Panorama UI (like HUD elements). This update should also take a month.
</p>
<p>
0.11.0 is the Replay file refactor, along with the update to replay playback tools (and extra things like working with Crashfort on direct SVR integration). Having expanded the scope of Momentum early made refactors like these easier to visualize and tackle, as we know what game modes will potentially require and design the systems to better accommodate them. As the others, we expect this to take a month or two, with sub updates to iron out any problems found in the refactor.
</p>
<p>
0.12.0 is the Bonus track + IL (Stage) submission and comparisons update. Bonus tracks and ILs just require some site backend tweaking to allow the submission of, and a client leaderboards UI update to support showing them. These updates will let players take advantage of the benefits of running replays locally instead of on a server, allowing basic racing against replays and comparing against any run on the leaderboard. Since the majority of this work is just tweaking already-existing-and-implemented systems, we&rsquo;re expecting this to take at most a month.
</p>
<p>
0.13.0 is Localization and polish, mass-testing of the Cosmetic system and Learn sections, and any extra work (cough, Anticheat, cough) needed before 1.0.0. This will take the remaining time before 1.0.0 release.<br></p>
<p>
Sprinkled in these releases as we approach 1.0.0 will be the full implementations of the <strong>Conc</strong>, <strong>Tricksurf</strong>, and (potentially) <strong>Defrag </strong>game modes! Conc requires some game movement abstraction and is expected to land in the 0.9.X updates, Tricksurf requires Panorama for a lot of UI work and will be worked on in the 0.10.X updates, and Defrag is <a href="https://github.com/chovelyoukai/defragmmod">currently being worked on by Lumia</a>, so it all depends on when the work there finishes up. I cannot express how excited I am to give these modes a fun, centralized platform for players!!
</p>
<p>
Then it&rsquo;s the public Beta release, v1.0.0! As a public release, anybody can download and play the game through Steam. You have no idea how excited the team is for this release, and we will make sure to celebrate publicly, so stay tuned for more info on that, but it&rsquo;s a ways away!
</p>
<p>
We have a <em>ton</em> of post-1.0.0 content planned, including adding and supporting the Parkour, Defrag, and Climb modes, community features like Clans and Dedicated Servers, and more! Since this is a bit further out, currently there&rsquo;s not much of a detailed roadmap yet.
</p>
<p>
Then last but not least, 2.0.0 is the full release (Gold), with the Campaign and custom gamemodes, which will have more details in future blog posts.
</p>
<h2>Developer Q&amp;A Streams</h2>


<p>
The last two sections have probably left you with a ton of questions! No worries.
</p>
<p>
We&rsquo;re proud to announce the start of our monthly Developer Questions and Answers streams over at <a href="https://www.twitch.tv/momentummod">our Momentum Mod Twitch channel!</a>  
</p>
<p>
The first one is going to be taking place Saturday, April 17th at 7 PM EST, where the team will be answering questions asked in our #qna-live channel in <a href="https://discord.gg/n4v52uv">the Momentum Mod Discord server</a>! So make sure to join the Discord server and ask your burning questions!
</p>
<p>
We will be announcing the streams on our Twitter and in the Discord. The VODs of the QnA sessions will also be uploaded publicly to YouTube, with timestamps for people to quickly find answers to questions they may have, and for those that may miss the stream.
</p>
<h2>Donations</h2>


<p>
We have had many people show interest in financially supporting the team on our endeavors for creating the game. The problem with being a Source Engine-based game has always been the inherent fees, totalling over $35,000 to properly be able to monetize the game. Money in general also tends to complicate things. I&rsquo;ve run this project on the idea of making a fun platform; I really want to play a game like this (Momentum). Momentum Mod is just a hobby, passion-driven project, so selling the game or having microtransactions just starts to muddy the waters, so to speak.
</p>
<p>
None of that has changed. With our license, the game still <em>has</em> to be 100% free, and will forever be. However, we have opened up the opportunity for those looking to give at-will donations to support us. The idea being that money can go into a pooled account, with the exact amounts publicly visible, and our receipts trackable to the first dollar spent. Luckily, there&rsquo;s a platform that believes in this, called OpenCollective.
</p>
<p>
Thus, I&rsquo;m happy to announce that those who wish to support us financially may do so through our OpenCollective webpage!
</p>
<p>
<a href="https://opencollective.com/momentum-mod">https://opencollective.com/momentum-mod</a> 
</p>
<p>
I will copy the disclaimer from the description here:
</p>
<ol><li>Momentum Mod the game and its related services are, and will always be, 100% free.

</li><li>Every contribution is appreciated but not required.

</li><li>A contribution through OpenCollective does not grant any material effect, it is purely an at-will donation to the team. In other words: 
<ol><li><em>DONATIONS DO NOT AND WILL NOT EVER GIVE KEYS TO THE GAME!</em>
 
</li><li>Donations do not and will not give any in-game advantages, effects, or statuses.
 
</li><li>Donations should be viewed as purely supporting the Momentum Mod Team in their endeavors to create and maintain the game and its platform.
</li> 
</ol></li> 
</ol><p>
Donations will only be used to fund:
</p>
<ol><li>The operating costs of Momentum Mod's servers and services, e.g. AWS storage costs, Website hosting, and so on.

</li><li>Licensing costs for professional software to develop the game, e.g. Substance Designer and related software suites.

</li><li>Costs related to hardware upgrades to improve the development of the game and/or its services, e.g. new computer parts.

</li><li>Marketing the game for its 1.0.0 release.
</li>
</ol><h2>Forums</h2>


<p>
We understand that the Momentum Discord server hasn&rsquo;t been the best at doing self-contained, organized discussions. Oftentimes, discussions about things that have already happened would crop back up, leading to pointless repetition. Therefore, we&rsquo;re also proud to announce that we have a dedicated Forums site!
</p>
<p>
You can find them over at <a href="https://forum.momentum-mod.org/">forum.momentum-mod.org</a>!
</p>
<p>
Please note that we are still using <a href="https://discord.gg/n4v52uv">our Discord server</a> heavily, and it is the best place to stay up to date with the game! The forums are more for larger and/or more-permanent discussions, but will also be used for things like showcasing maps, asking questions, and more!
</p>

<h2>Branding Update</h2>
<p>
TraZox and Bonjorno have been hard at work creating a new 3D background for the game's branding. This new background should better represent the game modes and lively energy the game has!
</p>

<p>
<a href="https://i.imgur.com/uz1soZl.jpg"><figure class="tmblr-full" data-orig-height="2160" data-orig-width="3840" data-orig-src="https://i.imgur.com/uz1soZl.jpg"><img src="https://64.media.tumblr.com/00a0d293360ad0fccbb58ef867df34f6/ea7ac9053c36f18f-1f/s540x810/5ab4b94af7b1dbb0bc28e9933935c9b1f941c8c1.jpg" alt="White Background" data-orig-height="2160" data-orig-width="3840" data-orig-src="https://i.imgur.com/uz1soZl.jpg"></figure></a>
<a href="https://i.imgur.com/YY6KpJS.jpg"><figure class="tmblr-full" data-orig-height="4320" data-orig-width="7680" data-orig-src="https://i.imgur.com/YY6KpJS.jpg"><img src="https://64.media.tumblr.com/e6f9ec4efb2473fefd6c072f7f616cc8/ea7ac9053c36f18f-61/s540x810/09eff7233f86163e7a679b2793c681ecc37bbf24.jpg" alt="Dark Background" data-orig-height="4320" data-orig-width="7680" data-orig-src="https://i.imgur.com/YY6KpJS.jpg"></figure></a>

<iframe src="https://gfycat.com/ifr/HospitableBowedAfricanwildcat" frameborder="0" scrolling="no" allowfullscreen width="640" height="404"></iframe>

</p>

<h2>Full Changelog</h2>


<h3>Added</h3>


<ul><li>Trigger_softbarrier (inherent with Chaos engine) (<a href="https://github.com/momentum-mod/game/issues/175">175</a>)

</li><li>Conc grenades added to func_nogrenades logic (<a href="https://github.com/momentum-mod/game/issues/1229">1229</a>)

</li><li>Ability to fizzle handheld concs (via mouse2) (<a href="https://github.com/momentum-mod/game/issues/1198">1198</a>)

</li><li>Momentum Hammer changes: 
<ul><li>All controls no longer look like Win95
 
</li><li>Removed frame limiter
 
</li><li>QuickHide state can is saved
 
</li><li>Camera positions saved with map
 
</li><li>Scriptable brush creation tools
 
</li><li>Material proxies support
 
</li><li>Models scale depending on their "modelscale" keyvalue
 
</li><li>Multiple cordons
 
</li><li>Model browser now can show used models, also now has refresh button
 
</li><li>Entity report now has targetnames
 
</li><li>Material history saves between sessions
 
</li><li>QuickHide can be undo/redo'd
 
</li><li>If autosave directory path is invalid when changing settings, it defaults to hammer/autosaves
 
</li><li>Autsave now checks all open documents, and is run from another thread
 
</li><li>3D view mouse sensitivity slider
 
</li><li>Angle snapping in entity properties window
 
</li><li>Custom build window
 
</li><li>2D views color customization
 
</li><li>New mode for sculpt - project paint with image file (png, jpg, bmp, tga)
 
</li><li>Particle browser
 
</li><li>Keybind editor 
 
</li><li>Setting to disable alpha inversion for displacements
 
</li><li>Shaded 3D preview now doesn't flicker
 
</li><li>Translucent textures in texture browser are drawn transparent
 
</li><li>Discord integration
 
</li><li>Light keyvalues now print their value 3D view draws current skybox
 
</li><li>Scriptable primitive brush via AngelScript
 
</li><li>And a ton more!
</li> 
</ul></li> 
</ul><h3>Fixed</h3>


<ul><li>Fixed mom_eyetele putting the player in a wall (<a href="https://github.com/momentum-mod/game/issues/1208">1208</a>)

</li><li>Fixed cursor not being hidden while spinning main menu model (<a href="https://github.com/momentum-mod/game/issues/989">989</a>)

</li><li>Fixed shader overriding failing when another game&rsquo;s bin folder is in PATH (<a href="https://github.com/momentum-mod/game/issues/832">832</a>)

</li><li>Fixed some teleport triggers slowing down noclip/practice mode speed (<a href="https://github.com/momentum-mod/game/issues/1195">1195</a>)

</li><li>Fixed getting a warning when correctly using a push trigger with &ldquo;set velocity&rdquo; mode

</li><li>Fix conc timer sounds not stopping on fizzle

</li><li>Fix main menu from being hidden when spamming escape key on level load (<a href="https://github.com/momentum-mod/game/issues/1224">1224</a>)

</li><li>Fix noclip slowdown when passing through teleports with &ldquo;reset velocity&rdquo; flag (<a href="https://github.com/momentum-mod/game/issues/1195">1195</a>)

</li><li>Prevented crash when drawing clip brushes on maps with exactly 1 brush entity (<a href="https://github.com/momentum-mod/game/issues/1266">1266</a>)

</li><li>Fixed paint decals overwriting most recent decal when at limit (<a href="https://github.com/momentum-mod/game/issues/243">243</a>)

</li><li>Better console logging from CSGO, solving console output not being formatted consistently (<a href="https://github.com/momentum-mod/game/issues/949">949</a>)

</li><li>Fixed concs giving knockback in noclip (<a href="https://github.com/momentum-mod/game/issues/1231">1231</a>)
</li>
</ul><h3>Improved</h3>


<ul><li>Color cvars now use RGBA 
<ul><li>cl_crosshair_color
 
</li><li>mom_ghost_color
 
</li><li>mom_hud_damageindicator_color
 
</li><li>mom_paint_color
 
</li><li>mom_trail_color
 
</li><li>mom_teledests_color
 
</li><li>mom_zone_checkpoint_draw_color
 
</li><li>mom_zone_end_draw_color
 
</li><li>mom_zone_stage_draw_color
 
</li><li>mom_zone_start_draw_color
</li> 
</ul></li><li>Improved conc delay timings (<a href="https://github.com/momentum-mod/game/pull/1196">1196</a>)

</li><li>Dynamically change point_spotlight brightness instead of being hardcoded to 64 (&ldquo;brightness&rdquo; &amp; &ldquo;setbrightness&rdquo;) (<a href="https://github.com/momentum-mod/game/issues/1211">1211</a>)

</li><li>Improvements to precaching from CSGO, perhaps solving first stickybomb shot delay (<a href="https://github.com/momentum-mod/game/issues/952">952</a>)
</li>
</ul><p>

</p><hr><p>
I want to thank you all for your understanding as we work towards the public release. We may have had some hiccups in the flow, but our Momentum has stayed strong and we&rsquo;re full Steam ahead! ;)
</p>
<p>
As always, please consider <a href="https://store.steampowered.com/app/669270/Momentum_Mod/">wishlisting us on Steam</a>, <a href="https://discord.gg/n4v52uv">joining our Discord server</a>, and spreading the word of the game!
</p>
<p>
Until <a href="https://github.com/orgs/momentum-mod/projects/12">0.9.0</a>,<br>
Nick (Gocnak) K.<br>
Momentum Mod Project Lead
</p>