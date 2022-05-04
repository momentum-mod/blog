---
markup: html
date: '2020-11-29T20:47:50+00:00'
draft: false
categories:
 - photo
tags: 
 - SourceEngine
 - game development
 - gamedev
 - MomentumMod
 - momentum mod
 - bunnyhop
 - Surf
 - rocket jump
 - sticky jump
 - conc
title: 'You Got a License for That?'
showDate: yes
url: /post/636153097782280192/you-got-a-license-for-that
---


<p>
Hello everyone, I have some <em>extremely</em> exciting news!!
</p>
<p>
<h1>Momentum Mod was granted engine access by Valve!</h1>
</p>
<p>
Firstly, this would not have been possible without the immense help from the team at Chaos Initiative, specifically CitadelCore and Tewan. With their guidance and direct help, we have been able to successfully get through to Valve to obtain access to the licensed Source Engine codebase!
</p>
<p>
And that is not all! I am also proud to announce that Momentum Mod is partnering with the Chaos Initiative team and co-developing a shared branch of Source titled the “Chaos” engine. This flavor of Source will be a cocktail of awesomeness, the best of <em>all</em> (TF2, CS:GO, Portal 2) worlds, providing a ton of opportunities for both players and mappers alike (explained more below)!
</p>
<p>
So, you probably have a ton of questions! Let’s see if I can answer the majority of them:
</p>
<!-- more -->
<p>
<h3>What’s this Chaos Initiative and Portal 2 Community Edition (P2CE) stuff?</h3>
</p>
<p>
Chaos Initiative is a team of licensed developers currently working on the Portal 2: Community Edition project. The goal of Chaos Initiative is to create and maintain the “Chaos” Source engine branch, which is a collaborative CS:GO-based Source engine branch designed to be used as a base for P2CE, Momentum, and other future projects as well!
</p>
<p>
The team at Momentum Mod is going to be co-developing the Chaos engine alongside the team at Chaos Initiative, using the shared codebase to develop Momentum, but also to deliver features and improvements to P2CE and any of its derived mods.
</p>
<p>
Learn more about the Chaos Initiative at their website: <a href="https://chaosinitiative.com/">https://chaosinitiative.com/</a><br>
You may also join the Chaos Initiative Discord here: <a href="https://discord.gg/AhkqPBb">https://discord.gg/AhkqPBb</a>
</p>
<p>
Portal 2: Community Edition is a mod for Portal 2 built on the Chaos engine that allows for much more enhanced modding capability. On top of that, it aims to contain its own custom campaigns and integrated workshop.
</p>
<p>
P2CE’s main site: <a href="https://www.portal2communityedition.com/">https://www.portal2communityedition.com/</a><br>
P2CE Discord: <a href="https://discord.gg/NcHSmgb">https://discord.gg/NcHSmgb</a><br>
Wishlist P2CE on the Steam Store: <a href="https://store.steampowered.com/app/440000/Portal_2_Community_Edition/">https://store.steampowered.com/app/440000/Portal_2_Community_Edition/</a>
</p>
<p>
<h3>What does an “engine license” even mean?</h3>
</p>
<p>
When we started Momentum Mod, the project was considered a “source mod,” only mounting CS:S and based on <a href="https://github.com/ValveSoftware/source-sdk-2013">the Source SDK 2013 codebase</a>. While plentiful for those looking to make basic Source mods, the SDK codebase is still only a very limited subset of modules of the entire Source engine. This 2013 SDK only gives server and client code access (for game movement, basic UI like HUD, entities), minor tool code (VBSP, VRAD, but no Hammer) and only has Half-Life 2 entities as a base.
</p>
<p>
The 2013 SDK was enough to get Momentum started, but as the game grew, so did the restrictions. All game movement and entities had to be reverse engineered, all game UI (main menu, console, etc) and shaders (VertexLit, Lightmapped, etc) done from scratch or copied over from Alien Swarm (a different, otherwise incompatible SDK), and we were limited to doing runtime patching of the engine to fix certain things like allowing runtime-modifiable tickrate.
</p>
<p>
Now, with an engine license, not only do we have access to practically <strong><em><span style="text-decoration:underline;">every</span></em> </strong>aspect of the engine (launcher code, engine code, full tool code, netcode code, etc), but we <strong><em>also </em></strong>have access to the Team Fortress 2, Counter-Strike Source, Counter-Strike Global Offensive, <em>and </em>Portal 2 codebases! So let’s give a bit of an overview of what the community is going to enjoy, right off the bat:<br>
</p>
<ul>

<li>Panorama, allowing the team to easily implement beautiful, powerful UI

<li>Portal 2’s portals (especially <a href="https://developer.valvesoftware.com/wiki/Linked_portal_door">ones placed by mappers</a>), gels, catapults, and other entities

<li>CS:GO’s <a href="http://counter-strike.net/workshop/workshopmaps#oswaldheader1">various improvements to VBSP, VRAD, shaders</a> and entities

<li>Support for both CS:GO <strong><em>and </em></strong>CS:S/TF2 maps, all in one game

<li>TF2’s code to verify our implementations of Rocket and Sticky jumping
</li>
</ul>
<p>
Of course, that’s not all! The team is also looking to heavily improve upon the systems found deep within the Source engine. Some of this work is already done or well underway, and will only accelerate now with this greenlight from Valve:
</p>
<ul>

<li>Steam Audio replacing Miles audio

<li>Webm support replacing Bink video

<li>Full DirectX 11 renderer and using the DXVK wrapper for UNIX systems

<li>The ability to ship 64-bit builds which allows modern, pre-ARM Mac OSX support

<li>Completely customized Hammer editor (and other tools!)

<li>Various fixes and improvements that <a href="https://github.com/momentum-mod/game/blob/develop/mp/src/game/shared/momentum/util/engine_patch.cpp">we had to literally hook into the engine to even do</a>

<li>Various feature requests and <a href="https://github.com/momentum-mod/game/issues?q=is%3Aopen+is%3Aissue+label%3A%22Blocked%3A+Needs+engine+access%22">things that we couldn’t do, until now</a>
</li>
</ul>
<p>
These are only <em>some</em> of the great things we have in mind for the shared engine. The really nice thing is, these changes will <em>also </em>be able to benefit P2CE as it’s in our shared Chaos engine base, so everybody wins!
</p>
<p>
<h3>Does this mean Momentum Mod will “feel” different?</h3>
</p>
<p>
Well, it depends on what you mean by “feel.”
</p>
<p>
<strong><em>We are not jumping engines to something like Unreal or Unity</em></strong>, the game is still going to be 100% grass-fed all-natural organic <strong><span style="text-decoration:underline;">Source Engine</span></strong> goodness! We have complete control over things like movement still, so this means all your movement and muscle memory will still be a one-to-one match, as if it’s still on the SDK Momentum build. <em>For example, the game won’t “feel” like CS:GO’s movement unless we <strong>explicitly use</strong> CS:GO’s movement code!</em>
</p>
<p>
As for improvements, we know this is a game focusing on <em>speed</em>. Players can’t have an enjoyable experience if we implement crazy things like RTX ray tracing with global illumination; surfing at max velocity while at 15 FPS or something. Our priority for the game will always be to have the <strong><em>smoothest feel possible first with cool effects second</em></strong>! Our improvements to things like the game rendering backend should give you even <em>more </em>FPS in most situations!
</p>
<p>
And if you mean things like how the game looks in terms of UI and Shaders, our game is going to feel like its own standalone, modern title. Both the access to Panorama and the renderer by itself will let us go pretty crazy on making the game look and feel unique. We can’t wait to show you what we have in mind!
</p>
<p>
<h3>Does this mean Momentum Mod can/will make money from the game now?</h3>
</p>
<p>
No, the game <strong>is and will always be 100% free to play</strong>. An engine license <em>only </em>means that we have full access to the Source Engine code. While we may be looking at reasonable ways to accept donations (team PayPal) or monetize (merch, soundtrack, etc), <strong>the game and all of its content <em>will be 100% free, forever. Period.</em></strong>
</p>
<p>
<h3>What does this mean for the public <a href="https://github.com/momentum-mod/game">momentum-mod/game</a> repository?</h3>
</p>
<p>
We are going to be actively approaching our 0.8.7 release as planned on <a href="https://github.com/orgs/momentum-mod/projects/11">our GitHub project board for it</a>. This will be our last bit of work that we do for the public repository. We will, in parallel, start the transition over to our shared Chaos engine repository. This engine repository will unfortunately have to be closed source due to the nature of the engine license agreement.
</p>
<p>
<strong><em>We will <span style="text-decoration:underline;">never</span> be deleting this open source game repository!</em></strong> We plan to use the game repository as a monument for how far we got and with whose help, and as a permanent beacon that open source game development is <strong><em>absolutely possible</em>! </strong>We will <em>also </em>be using the game repo as a public issue tracker for the game still, so it’s not going to go anywhere!
</p>
<p>
I also want to take some time to thank the impeccable number of contributors that have taken the time to help us progress to where we are today. Any contribution, big or small, regardless of intent, helped us get here. Thank you. Your efforts will <strong><em>not </em></strong>go uncredited or unnoticed!
</p>
<p>
We would absolutely love to continue our game development as openly as we possibly could, but we will instead have to be selective on which developers we could bring onto the closed repository, as new members of this repository need to go through a process to sign an NDA to gain access. It’s not impossible to bring on more licensed developers though, and we may be considering it in the future!
</p>
<p>
Also note that we still have our <a href="https://github.com/momentum-mod/website">website</a>, <a href="https://github.com/momentum-mod/discord-bot">discord bot</a>, and <a href="https://github.com/momentum-mod/docs">documentation</a> completely open source, and we would absolutely love any help we can get on these repositories! Any contribution can go towards obtaining a key for the game!
</p>
<p>
<h3>What does this mean for the “Summer 2021” release date estimate?</h3>
</p>
<p>
We are still on target, but may have to bump it back to Autumn 2021 to be safe! The really nice thing about teaming up with the P2CE team is we already have a base engine onto which we may implant our Momentum code. Depending on how long it takes for this new build to get up and running, we may not even see a noticeable impact in our confidence to hit the Summer 2021 release date!
</p>
<p>
Of course, on-going game code progress is now limited to the developers with access to the closed repository, so while work may not be done in parallel by outside contributors anymore, the team is going to be extremely focused on delivering consistent updates for the game, whether it be builds on Steam or just public dev logs!
</p>
<p>
<h3>I have more questions, where could I ask them?</h3>
</p>
<p>
We implore you to join our very active <a href="https://discord.gg/n4v52uv">Discord server</a> to ask all your unanswered burning questions about the game / this announcement!<br><br>We will make it our duty to show active progress on the game on our server as well. Whether it be teaser photos/videos of the new build, or game announcements at large, the <a href="https://discord.gg/n4v52uv">Momentum Mod Discord server</a> is and will be the best place to stay up-to-date with the game’s development!
</p>
<p>

<hr>
</p>
<p>
If you haven’t already, please consider <a href="https://store.steampowered.com/app/669270/Momentum_Mod/">wishlisting Momentum Mod on Steam</a> to support the game and share it with your friends. We deeply appreciate any and all support we can get for the game!
</p>
<p>
Until next time,<br>
Nick (Gocnak) K.<br>
Momentum Mod Project Lead
</p>