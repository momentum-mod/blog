---
title: "0.9.1 Changelog"
date: 2022-05-25T23:49:35-04:00
showDate: true
draft: false
cover:
    image: images/091Banner.png
    alt: '0.9.1 Changelog'
    relative: true
---

Hello everyone!

The Momentum Mod team has been hard at work accomplishing the latest version milestone, **0.9.1**! This update has been a while coming, with over 220 (!!!) GitHub cards closed and sees a completely new user interface, a new mode or two, a new solution to the issue of missing textures, tons of fixes to gameplay and rendering, and a lot more!

Let's jump in, shall we?

## Wham, Bam, Panorama!

The majority of the work in this last milestone update has gone towards the complete overhaul of the game’s user interface (UI) to the Panorama framework.

As talked about in the previous blog posts, Panorama is the framework we’ve been graciously blessed with following our access to the CS:GO Source Engine codebase. It uses web-like design principles, with panel layouts defined in XML, styling defined in CSS, and and we’re able to utilize JavaScript via a V8 binding for the scripting layer.

While the default Panorama implementation was great, we needed some more work done to fit a better workflow. SCell took to updating V8 so that our JavaScript code can use more modern ECMAScript standards, and implemented a SCSS compiler inside the engine that allows us to utilize [Sass CSS](https://sass-lang.com/). Similarly, the SVG parser needed some more work to support some of the iconography we wanted to use, so SlidyBat worked on adding the missing specs.

The entire game programming team swarmed various different panels of varying sizes, with the work only picking up more and more speed as we figured out best practices to follow, understood more of the framework and how best to expose data via C++, and got better with communicating panel status between each other.

But the main reason this has taken so long is because not only were we completely rewriting the old user interface (VGUI) panels, but we were _also **rewriting the underlying systems**_ that the major panels used. Some of the old VGUI panels were written when Momentum was just starting off (circa 2015), and some systems were written within a month to get a university senior class project done. So, it’s good to have all this code and systems refactoring done now to a more acceptable code quality that better reflects the team’s gained knowledge over the years.

So, without further ado, I’m very happy to present piece-by-piece, Momentum Mod’s new Panorama UI!

* **Panorama Main Menu**

{{<imgcmp baseImage="images/Pano-MainMenu-Dark.webp" overlayImage="images/Pano-MainMenu-Light.webp">}}

* **Panorama Map Selector**

{{<figure src="images/Pano-MapSelector.webp">}}

* **Panorama Learn section**

{{<figure src="images/Pano-Learn.webp">}}

* **Panorama Settings menu**

{{<figure src="images/Pano-Settings.webp">}}

* **Panorama Drawer Panel**
    * **Lobbies panel (browsing)**
{{<figure src="images/Pano-Drawer-Lobbies-2.webp">}}
    * **Lobbies panel (inside)**
{{<figure src="images/Pano-Drawer-Lobbies-1.webp">}}
    * **About panel**
{{<figure src="images/Pano-Drawer-About.webp">}}

* **Panorama Console**

{{<figure src="images/Pano-Console.webp">}}

* **Panorama Toast manager**

{{<figure src="images/Pano-Toasts.webp">}}
* **Panorama HUD panels**
    * **Crosshair, Speedometer, Timer**
{{<figure src="images/Pano-HUD-CrosshairSpeedo.webp">}}
    * **Keypress input**
{{<figure src="images/Pano-HUD-Keypress.webp">}}
    * **Sticky charge & count**
{{<figure src="images/Pano-HUD-StickyPanels.webp">}}
    * **Conc charge & timers**
{{<figure src="images/Pano-HUD-ConcPanels.webp">}}
    * **Ghost panels**
{{<figure src="images/Pano-HUD-GhostPanels.webp">}}
    * **Leaderboards**
{{<figure src="images/Pano-HUD-Leaderboards.webp">}}
    * **End of Run**
{{<figure src="images/Pano-HUD-EndOfRun.webp">}}
    * **Comparisons**
{{<figure src="images/Pano-HUD-Comparisons.webp">}}
    * **Damage Indicators**
{{<figure src="images/Pano-HUD-DamageIndicators.webp">}}
    * **Weapon selection**
{{<figure src="images/Pano-HUD-WeaponSelect.webp">}}
    * **Chat**
{{<figure src="images/Pano-HUD-Chat.webp">}}
    * **Strafe sync**
{{<figure src="images/Pano-HUD-StrafeSync.webp">}}
    * **Spectate HUD, spec list**
{{<figure src="images/Pano-HUD-Spec.webp">}}
    * **Replay controls**
{{<figure src="images/Pano-HUD-ReplayControls.webp">}}
    * **Static HUD menus**
{{<figure src="images/Pano-HUD-StaticMenus.webp">}}
    * **Version info**
{{<figure src="images/Pano-HUD-MapInfo.webp">}}
* **Misc Panorama Panels**
    * **Panorama color picker**
{{<figure src="images/Pano-ColorPicker.webp">}}
    * **Panorama N state buttons**
{{<figure src="images/Pano-NStateButtons.webp">}}
    * **Dual-knobbed slider**
{{<figure src="images/Pano-DualKnobbedSliders.webp">}}

While this list seems exhaustive, it’s actually not _every_ panel we need to convert! For example, the new map zoning tools are waiting for 0.10.0’s new zone format before being redone. Similarly, Tricksurf’s UI is waiting until we focus on the trick system again after 0.10.0. We have a lot of web work ahead of us as well which will start to populate a lot of these panels with the right data. We also have a plethora of engine-shared VGUI panels like the game_text and Game Instructor panels we want to reimplement in the future, but are low priority for now. For 0.9.1 we focused on the immediately noticeable UI and will be picking off these other panels, and giving them a lot of elbow grease in future versions.

You may have caught some of fingerprice’s development streams over on our Twitch page, but if not, [check them out](https://www.twitch.tv/collections/3Ded0r8KtRYP7Q)! We plan to use our Twitch channel for more Momentum related goodness in the future, so drop us a follow if you’d like to see it!

Finally, as a callback to our open source roots, we open sourced all of this beautiful UI! You can find it over on [our momentum-mod/panorama GitHub repo](https://github.com/momentum-mod/panorama). We’ve made all of the UI code that we can public, under the very permissible MIT license. Feel free to make something like your own strafe trainer or just poke around!


## Speedrunning in the 90s

I think it’s about time we make Conc and Defrag officially part of the game!

### Conc
{{<rawhtml>}}
<video src="https://momentum-mod.org/assets/images/conc_loop.webm" loop autoplay width=100%></video>
{{</rawhtml>}}

Conc was initially added back in the 0.8.6 update, [based on the code found in Fortress Forever](https://github.com/fortressforever/fortressforever), with permission from the lead developer Squeek502. Since then, we’ve been able to reverse engineer a lot of Team Fortress Classic specific timings and behaviors (with immense help from hlstriker!) and get Conc feeling better and better. It’s still not done – we’d like to address [feedback raised on our forums](https://forum.momentum-mod.org/d/70-conc-changes-megathread) and make the mode feel just right! But regardless, welcome to Momentum Mod, Conc!

### Defrag

{{<rawhtml>}}
<video src="images/defrag_loop.mp4" loop autoplay width=100%></video>
{{</rawhtml>}}

Defrag on the other hand started off as an 0.8.7 fork by Lumia, and we were very impressed with their work and brought them onboard to make the mode official! 0.9.1 is the first version seeing the VQ3 and CPM based implementations, with CPM as the default, with things like official VQ3 support and weapons coming later.

We’re amazed with and very thankful for the feedback the Defrag community has been giving us as we integrate the mode into the game. It has led us to getting PeenScreeker onto the team, who, alongside fingerprince, implemented the CGAZ and Snaphud a lot of Defraggers are used to, with plenty of options to boot!

{{<figure src="images/Pano-CGAZ-Snaps.webp">}}

## Any Color, As Long As It’s Not Purple and Black

An active problem for our game and our players is mounted content. Momentum Mod specifically never requires any particular game to be able to play it, but lots of supported maps within the game utilize content from Valve games that the player may not have installed, or in the common case of Counter-Strike: Source, even purchased.

The reason it’s a problem for us is maps tend to pack these assets that should otherwise come from mounting Valve’s games. It makes sense why they originally do, though. For traditional dedicated servers, mounting the games needed (other than the one the server is for) is not even possible, so mappers have to include the games’ assets directly in the BSP file for it to be playable.

Granted, Valve probably doesn't care if maps pack other games’ assets for a server that’s already running on one of their games, but, Momentum Mod is a standalone game. Thus, our goals are to:

1. Maintain our good terms with Valve by not committing copyright infringement
2. Support every map of every supported mode that we possibly can
3. Reduce our cloud storage costs for maps, which:
    1. Optimizes map downloads for users globally
    2. Similarly reduces the amount of storage end users need for maps

As such, we can’t afford, nor want to pack these assets in maps. We similarly don’t want to ship the mounted Valve games’ content with our game, as that will balloon our game’s install size for content that a lot of players may not even need in the first place, or already have on their computers anyways. Simply asking players to install the Valve games locally, and automatically mounting using the Steamworks API is our best option.

But for players, this is a problem because if they don’t have the Valve games installed, these maps will otherwise have the lovely purple-and-black error textures _everywhere_, depending on how much the map relied on them.

For example, did you know the map **surf_utopia** actually uses Team Fortress 2 textures despite being a popular surf map in Counter-Strike? A ton of our surf players didn’t know, and thus don’t have it installed, leading them to this lovely sight on map load:

{{<figure src="images/Utopia-Hell.jpg">}}

Our team member BLT worked on a solution, originally suggested by Exactol, and the approach is pretty brilliant:  

During the map compile process, the texture files (VTFs) used in a map have their average colors copied over into the [texture data lump’s “reflectivity” value](https://developer.valvesoftware.com/wiki/Source_BSP_File_Format#Texdata) by VBSP, which is then used by VRAD for the indirect lighting calculations done on a map. Since this is all done at map compile time, and not at game runtime, this color data exists in the BSP file _regardless of whether the original VTFs are mounted or not_!

This means that instead of having the game point to the eye-searing purple-and-black error texture, we can instead point to a texture of the surface’s reflectivity color, and the results are _astounding_:

{{<imgcmp baseImage="images/Utopia-Textured.webp" overlayImage="images/Utopia-Replacement.webp" >}}

*(Click and drag the blue bar to compare the two images side by side!)*

Obviously, this is just a workaround solution. **We still recommend installing the original Valve games that maps may use assets from!** Not only will the maps look significantly better with more detail, but our solution doesn’t cover every case, especially models, and isn’t meant to be a permanent “you can uninstall everything” answer.

We will be updating our Map Selector in the future to display which Valve game(s) a map mounts assets from, along with the “reliance severity” which suggests how good of a job our texture replacement system will (or won’t) do. For example, maps that are composed of more than 70% assets from a particular game will have a “high reliance severity” on it, and we will be recommending via our UI that you install the given game (if you haven’t already) to have the best experience. While the map still might be playable, the visual experience is going to be very different from what the mapper has intended!

Alas, this is just the first step of our plans to optimize BSPs. Stay tuned for a future blog post that will go into detail about our plans to further optimize BSP sizes, file mounting, and more!

## Fixing Your Movement, One Bug at a Time

Rio was added to the team and licensed, and has been hard at work, working on a plethora of movement fixes.

* **Movement Reimplementation + Cleanup**

Our movement code from the 0.8.6 days has been pretty messy. Every game mode’s code lived in a single file, leading to a ton of if-else spaghetti checks, causing really confusing and hard-to-follow code. While it had the benefit of little code duplication, it was traded for lack of code cleanliness.

For 0.9.1, Rio has painstakingly went through and separated out the movement into the “classes” of movement we support: 2013 (Ahop, Bhop, RJ, SJ, Surf), Defrag (it already was separated out, thanks Lumia!!), Fortress Forever (Conc), and a base class where all of these subclasses share code, like movement through portals.

The benefit now is that a particular gamemode’s movement is found in one instance of the overall movement system, and while we may need to do a little bit of code duplication for applying fixes to every game mode’s movement, the cleanliness more than makes up for it. A byproduct of this effort is that TF2’s modes now are as 1:1 as we can get with the original game’s code, meaning things like ctaps are properly working and giving the expected distances.

* **RNGFix Fully Implemented**
    * Telehop fix - hitting a wall behind teleport triggers will not stop players
    * Slope fixes - consistent speed gain and loss going down and up slopes, respectively
    * Edge fix, including ILDPRUT’s edgebug assistance - edgebugs are more consistent, can jump out of edgebugs in surf/bhop if holding jump
    * Jump height made 100% consistent - consistent 64s every jump for bhop in particular
* **Collision bugs fixed, largely thanks to ILDPRUT**
    * Wallbugs - getting stuck in any wall that isn’t aligned to the player’s axis-aligned bounding box
    * Texturebugs - getting temporarily stuck where two textures form a seam on a wall
    * Pixelwalks - walking where a slope meets a vertical wall
    * Pixelsurfs (mostly) - surfing along a seam in the wall, [3kliksphilip has an excellent video about this bug](https://www.youtube.com/watch?v=pWoETelZP-E)
* **Players can safely strafe through portals now**
* **Slides refactored to a solid (func_slide)**
    * Less bug-prone with being built directly into the movement code
    * Easier mapping experience - mappers need to only put the entity down where a slide section should be, no more covering sections in triggers


## Okay Then, Render Me This!

SlidyBat’s been hard at work porting the rendering backend to DX11 and fixing various bugs that pop up.

* MSAA implemented in DX11
* CSM implemented in DX11, and even added to water:
{{<imgcmp baseImage="images/CSMWater-before.webp" overlayImage="images/CSMWater-after.webp" >}}

* Now utilizing the [DXGI flip model](https://devblogs.microsoft.com/directx/dxgi-flip-model/)
    * Players should be using “Fullscreen windowed” now, as it has no input lag and alt-tabbing is instantaneous  
* Various shader porting and fixes
* Performance optimizations
    * So much so that we’re now GPU bound instead of CPU bound

Smaed is a member of the Chaos Initiative team working on P2CE, but the benefit of using a shared engine repository is that they’ve contributed a couple of very noteworthy rendering related fixes:

* VRAD can now bounce light through static Portals
* PBR now has Parallax-Corrected Cubemaps

We’ll also be bringing on Cowboyana to the licensed developer team, they’re another graphics-focused coder looking forward to helping out wherever they can, so stay tuned for even more graphical goodies!

## Sentry Goin' Up

With an initial implementation by SCell, we're now able to collect and analyze crash reports from the game, utilizing [Sentry.io](https://sentry.io/)'s extremely generous Open Source offering!

What does this mean for players? Well, on first time boot, you will be prompted with this pop-up:

{{<figure src="images/Sentry-Confirm.png">}}

You can opt-in to submitting crash reports automatically to us. If you do, and whenever the game unfortunately crashes, a crash dump is made and sent automatically to our Sentry dashboard.

The only information that is sent to us is:
* The Operating System (Windows / Linux)
* The current Steam user's username and ID number
* The crash dump file itself, containing debugging info such as the stack trace, which allows us to find exactly which line(s) of code are causing the crash

It is entirely optional, but we highly recommend opting-in, as it will help us to improve the game and make it more stable!

You can reset this consent by deleting the `Momentum Mod Playtest/bin/<platform>/_sentry/user-consent` file, which will prompt you again on next boot for your new Yes/No answer.

## Full Changelog

{{<details>}}
### Added (39)

- A button to open the Momentum website in the Steam browser ingame ([game/issues/282](https://github.com/momentum-mod/game/issues/282))
- Add (optional) obnoxious screen tilt on landing ([game/issues/1606](https://github.com/momentum-mod/game/issues/1606))
- Add Panorama API for version info, update versioninfo component ([game/issues/1696](https://github.com/momentum-mod/game/issues/1696))
- Add `mat_error_texture_*` commands to settings  ([game/issues/1656](https://github.com/momentum-mod/game/issues/1656))
- Add ability to switch RL viewmodel to uncentered version without script renaming/reloading ([game/issues/1264](https://github.com/momentum-mod/game/issues/1264))
- Add ability to view public lobby list whilst already in a lobby ([game/issues/1086](https://github.com/momentum-mod/game/issues/1086))
- Add defrag CGAZ hud ([game/issues/1662](https://github.com/momentum-mod/game/issues/1662))
- Add defrag snap zone hud element ([game/issues/1663](https://github.com/momentum-mod/game/issues/1663))
- Add scrolling to console dropdown ([game/issues/1178](https://github.com/momentum-mod/game/issues/1178))
- Basic Panorama drawer panel implementation ([game/issues/1424](https://github.com/momentum-mod/game/issues/1424))
- Change steam store link on the panorama socials to GitHub ([game/issues/1653](https://github.com/momentum-mod/game/issues/1653))
- Conc Gamemode ([game/issues/802](https://github.com/momentum-mod/game/issues/802))
- Consider adding cow mangler shoot angles in RJ ([game/issues/1708](https://github.com/momentum-mod/game/issues/1708))
- Custom Crosshair Settings ([game/issues/1107](https://github.com/momentum-mod/game/issues/1107))
- Defrag Gamemode ([game/issues/1003](https://github.com/momentum-mod/game/issues/1003))
- Expose LZ compression to Panorama ([game/issues/1752](https://github.com/momentum-mod/game/issues/1752))
- Expose Movement Data Required for Cgaz and SnapHUD to Panorama ([game/issues/1678](https://github.com/momentum-mod/game/issues/1678))
- Investigate using portals in VRAD calculations ([game/issues/1412](https://github.com/momentum-mod/game/issues/1412))
- Map finished panel redesign/refactor ([game/issues/1093](https://github.com/momentum-mod/game/issues/1093))
- Panorama Comparisons Panel ([game/issues/1510](https://github.com/momentum-mod/game/issues/1510))
- Panorama Credits panel ([game/issues/1425](https://github.com/momentum-mod/game/issues/1425))
- Panorama HUD Speedometer ([game/issues/1508](https://github.com/momentum-mod/game/issues/1508))
- Panorama Leaderboards Panel ([game/issues/1514](https://github.com/momentum-mod/game/issues/1514))
- Panorama Map Selector ([game/issues/1523](https://github.com/momentum-mod/game/issues/1523))
- Panorama Replay UI ([game/issues/1518](https://github.com/momentum-mod/game/issues/1518))
- Panorama Safeguard Popups ([game/issues/1559](https://github.com/momentum-mod/game/issues/1559))
- Panorama Speedometer Settings ([game/issues/1013](https://github.com/momentum-mod/game/issues/1013))
- Panorama Weapon selection HUD ([game/issues/1512](https://github.com/momentum-mod/game/issues/1512))
- Panorama chat panel ([game/issues/1485](https://github.com/momentum-mod/game/issues/1485))
- Panorama console panel ([game/issues/1493](https://github.com/momentum-mod/game/issues/1493))
- Panorama damage indicators ([game/issues/1517](https://github.com/momentum-mod/game/issues/1517))
- Panorama map finished panel ([game/issues/1509](https://github.com/momentum-mod/game/issues/1509))
- Panorama settings menu ([game/issues/1360](https://github.com/momentum-mod/game/issues/1360))
- Panorama spectate HUD ([game/issues/1511](https://github.com/momentum-mod/game/issues/1511))
- Panorama strafesync HUD ([game/issues/1515](https://github.com/momentum-mod/game/issues/1515))
- Panorama timer HUD ([game/issues/1513](https://github.com/momentum-mod/game/issues/1513))
- Panorama: Spectate List ([game/issues/1719](https://github.com/momentum-mod/game/issues/1719))
- Panorama: Toast Panel ([game/issues/1718](https://github.com/momentum-mod/game/issues/1718))
- Trigger for rolling stickies if inside of trigger ([game/issues/1448](https://github.com/momentum-mod/game/issues/1448))

### Fixed (114)

- "Unknown Command" response only shows when at the main menu, not in-game ([game/issues/1569](https://github.com/momentum-mod/game/issues/1569))
- "sv_interval_per_tick" not correctly setting custom tickrates ([game/issues/1385](https://github.com/momentum-mod/game/issues/1385))
- $color does not work on func_brush ([game/issues/1463](https://github.com/momentum-mod/game/issues/1463))
- (DX11?) +paint decals and shallow water don't interact properly ([game/issues/1299](https://github.com/momentum-mod/game/issues/1299))
- +duck to show/hide mouse cursor in replays doesn't work when bound via an alias ([game/issues/1620](https://github.com/momentum-mod/game/issues/1620))
- All modes 'stick' to ceiling rather than just CSS-based one ([game/issues/1455](https://github.com/momentum-mod/game/issues/1455))
- Bullets don't activate buttons in practice mode ([game/issues/1503](https://github.com/momentum-mod/game/issues/1503))
- Can no longer arrow key through multiple previous commands in console ([game/issues/1697](https://github.com/momentum-mod/game/issues/1697))
- Can't create savestates from replays ([game/issues/1720](https://github.com/momentum-mod/game/issues/1720))
- Can't edit key to change console bind in settings ([game/issues/884](https://github.com/momentum-mod/game/issues/884))
- Character shader crash ([game/issues/1222](https://github.com/momentum-mod/game/issues/1222))
- Console still eats inputs while "fading out" on chaos engine ([game/issues/1355](https://github.com/momentum-mod/game/issues/1355))
- Crash on surf_pantheon ([game/issues/1422](https://github.com/momentum-mod/game/issues/1422))
- Crashing on the bhop_triportals with low shadders setting ([game/issues/1567](https://github.com/momentum-mod/game/issues/1567))
- Crashing when changing map while already in a different map. ([game/issues/1713](https://github.com/momentum-mod/game/issues/1713))
- DX11 Refract shader mostly appears black ([game/issues/1477](https://github.com/momentum-mod/game/issues/1477))
- DX11 `mat_luxels` is missing ([game/issues/1607](https://github.com/momentum-mod/game/issues/1607))
- DX11: CSM doesn't appear to work ([game/issues/1400](https://github.com/momentum-mod/game/issues/1400))
- DX11: Flashlight causes weird view angle ([game/issues/1654](https://github.com/momentum-mod/game/issues/1654))
- DX11: Water 'surface' isn't rendering ([game/issues/1398](https://github.com/momentum-mod/game/issues/1398))
- DX11: Water on surf_pantheon is off ([game/issues/1658](https://github.com/momentum-mod/game/issues/1658))
- DX11: crash on loading `jump_academy2_rc8` ([game/issues/1583](https://github.com/momentum-mod/game/issues/1583))
- Damage indicators should scale to sj/conc damage ([game/issues/1094](https://github.com/momentum-mod/game/issues/1094))
- Discord rich presence constantly tries to establish Discord connection when Discord is closed ([game/issues/1557](https://github.com/momentum-mod/game/issues/1557))
- Distance ctaps seem slightly harder than in tf2 ([game/issues/1609](https://github.com/momentum-mod/game/issues/1609))
- Dx11+Panorama: Using `-profile` causes inconsistent crashing ([game/issues/1439](https://github.com/momentum-mod/game/issues/1439))
- Engine crash on loading jump_pipebomb_v1 ([game/issues/1483](https://github.com/momentum-mod/game/issues/1483))
- Entering end zone with hud disabled softlocks the game ([game/issues/1342](https://github.com/momentum-mod/game/issues/1342))
- Game Crash on Flashlight Use  ([game/issues/1688](https://github.com/momentum-mod/game/issues/1688))
- Game crash when alt-tabbing back into game on jump_finite_v2 ([game/issues/1778](https://github.com/momentum-mod/game/issues/1778))
- HDR commands now cheat protected ([game/issues/1725](https://github.com/momentum-mod/game/issues/1725))
- Hammer Entity Report: SHIFT+Click two items in list ignores the visual filter ([game/issues/1781](https://github.com/momentum-mod/game/issues/1781))
- Hang/Crash loading bhop_happybirthdayantosha ([game/issues/1447](https://github.com/momentum-mod/game/issues/1447))
- Hitting enter in console after downloading a map loads the map ([game/issues/1788](https://github.com/momentum-mod/game/issues/1788))
- Increase mom_conc_bloat_bounds to 0.25 to prevent concs from clipping through walls ([game/issues/1461](https://github.com/momentum-mod/game/issues/1461))
- Leaderboard panel flashes on screen when opened with 'cl_drawhud 0' ([game/issues/1570](https://github.com/momentum-mod/game/issues/1570))
- Light glow has issues rendering ([game/issues/1247](https://github.com/momentum-mod/game/issues/1247))
- Loading screen truncates load % string at specific number ([game/issues/1538](https://github.com/momentum-mod/game/issues/1538))
- Lobby Settings/Create Lobby panels having text in buttons being able to be highlighted with click and drag ([game/issues/1755](https://github.com/momentum-mod/game/issues/1755))
- Looking away from the portal doesn't render other side of the portal correctly  ([game/issues/1756](https://github.com/momentum-mod/game/issues/1756))
- Map Selector mode tooltip doesn't go away ([game/issues/1532](https://github.com/momentum-mod/game/issues/1532))
- Movement keys "freeze" for seemingly no reason ([game/issues/1542](https://github.com/momentum-mod/game/issues/1542))
- Music Volume does not actually work ([game/issues/1459](https://github.com/momentum-mod/game/issues/1459))
- Overlapping warning boxes ([game/issues/1186](https://github.com/momentum-mod/game/issues/1186))
- Panorama JS exception on loading a map from the map selector ([game/issues/1444](https://github.com/momentum-mod/game/issues/1444))
- Panorama Text Input Animations Are Weird ([game/issues/1432](https://github.com/momentum-mod/game/issues/1432))
- Panorama avatar image does not fit the panel ([game/issues/1507](https://github.com/momentum-mod/game/issues/1507))
- Panorama console spam every time the main menu / pause menu is enabled ([game/issues/1435](https://github.com/momentum-mod/game/issues/1435))
- Panorama height-percentage can give parent panels infinite width ([game/issues/1760](https://github.com/momentum-mod/game/issues/1760))
- Panorama img-shadow property doesn't use rgba alpha ([game/issues/1495](https://github.com/momentum-mod/game/issues/1495))
- Panorama show spec button check case-sensitive when it shouldn't be ([game/issues/1671](https://github.com/momentum-mod/game/issues/1671))
- Panorama: Color picker colors that have 0 alpha are "hidden" from the player ([game/issues/1666](https://github.com/momentum-mod/game/issues/1666))
- Panorama: Trick list UI shows up during loading screens briefly ([game/issues/1436](https://github.com/momentum-mod/game/issues/1436))
- Playtest settings not saving / are being affected by base game settings ([game/issues/1689](https://github.com/momentum-mod/game/issues/1689))
- Portal doesn't work properly when you are on the edge of it ([game/issues/1753](https://github.com/momentum-mod/game/issues/1753))
- Portals don't render correctly if "Shader Detail" is below "High" ([game/issues/1601](https://github.com/momentum-mod/game/issues/1601))
- Portals show as a missing texture without mounting Portal 2 ([game/issues/1403](https://github.com/momentum-mod/game/issues/1403))
- Pressing ` with chat open types the character and opens console ([game/issues/1393](https://github.com/momentum-mod/game/issues/1393))
- Props/textures don't load on certain workflows (reproducible) ([game/issues/915](https://github.com/momentum-mod/game/issues/915))
- Quadrant check was inadvertently removed from CategorizePosition() ([game/issues/1368](https://github.com/momentum-mod/game/issues/1368))
- Rebinding the console key will still require ` to close the panel ([game/issues/1479](https://github.com/momentum-mod/game/issues/1479))
- Remove texturebugs ([game/issues/1382](https://github.com/momentum-mod/game/issues/1382))
- Running zonmaker with a BSP completely locks up my system ([game/issues/1664](https://github.com/momentum-mod/game/issues/1664))
- Setting a start mark while ducked in conc puts start mark in the ground ([game/issues/1700](https://github.com/momentum-mod/game/issues/1700))
- Slide trigger unintuitively clamps speed in TF2 modes ([game/issues/1333](https://github.com/momentum-mod/game/issues/1333))
- Spam Players with Projectiles / Other ([game/issues/1626](https://github.com/momentum-mod/game/issues/1626))
- Spamming `mom_spectate` and `mom_spectate_stop` gives extra height ([game/issues/1644](https://github.com/momentum-mod/game/issues/1644))
- Spectate UI buttons / replays keep focus and swallow Enter key ([game/issues/1714](https://github.com/momentum-mod/game/issues/1714))
- Spectator / replay UI shows wrong key to toggle mouse capture ([game/issues/1387](https://github.com/momentum-mod/game/issues/1387))
- Speedometer units (MPH/KMH/Energy) only works for Absolute Speedometer ([game/issues/1458](https://github.com/momentum-mod/game/issues/1458))
- Startup screen is off in panorama ([game/issues/1319](https://github.com/momentum-mod/game/issues/1319))
- Stickies bounce near portals  ([game/issues/1402](https://github.com/momentum-mod/game/issues/1402))
- Tabbing out of & into the game sometimes locks all keyboard input ([game/issues/1560](https://github.com/momentum-mod/game/issues/1560))
- Tabs don't always reset visually when using arrow key navigation ([game/issues/1120](https://github.com/momentum-mod/game/issues/1120))
- Taking a screenshot while around portals has visual artifacts ([game/issues/1589](https://github.com/momentum-mod/game/issues/1589))
- Timer Does Not Hide When Leaderboards Are Open ([game/issues/1732](https://github.com/momentum-mod/game/issues/1732))
- Timer elements for thrown concs are stuttery while moving ([game/issues/1480](https://github.com/momentum-mod/game/issues/1480))
- Toggling `sv_cheats` in the same tick lets you use protected commands ([game/issues/1642](https://github.com/momentum-mod/game/issues/1642))
- Toggling drawing entities crashes the game ([game/issues/1647](https://github.com/momentum-mod/game/issues/1647))
- Tools mode: Layout issues ([game/issues/1218](https://github.com/momentum-mod/game/issues/1218))
- UI for concs is hidden in unrendered visleaf ([game/issues/1383](https://github.com/momentum-mod/game/issues/1383))
- Untranslated string in settings page ([game/issues/1466](https://github.com/momentum-mod/game/issues/1466))
- Using `mom_spectate` while there is nobody to spectate drops weapons ([game/issues/1604](https://github.com/momentum-mod/game/issues/1604))
- Using `quit_prompt` in console softlocks the game ([game/issues/1636](https://github.com/momentum-mod/game/issues/1636))
- Using clear button does not clear search on map selector ([game/issues/1533](https://github.com/momentum-mod/game/issues/1533))
- Using escape to close the settings menu does not unfocus the settings icon ([game/issues/1524](https://github.com/momentum-mod/game/issues/1524))
- VGUI elements always draw under Panorama elements ([game/issues/1437](https://github.com/momentum-mod/game/issues/1437))
- Walking through portals causes a visual "jump" ([game/issues/1405](https://github.com/momentum-mod/game/issues/1405))
- Wallbugging in narrow corners ([game/issues/1581](https://github.com/momentum-mod/game/issues/1581))
- Weapon switch sound not changed by ui volume ([game/issues/1730](https://github.com/momentum-mod/game/issues/1730))
- When Alt-tabbed viewmodel and projectile textures glitch out ([game/issues/1674](https://github.com/momentum-mod/game/issues/1674))
- Wrong reflections from previous map ([game/issues/1293](https://github.com/momentum-mod/game/issues/1293))
- `host_timescale` with `sv_cheats 0` still affects sounds ([game/issues/1710](https://github.com/momentum-mod/game/issues/1710))
- `mom_hud_keypress_enable 0` doesn't always work ([game/issues/1552](https://github.com/momentum-mod/game/issues/1552))
- `sj_zero` crash ([game/issues/1661](https://github.com/momentum-mod/game/issues/1661))
- env_bubbles renders center origin of map ([game/issues/1789](https://github.com/momentum-mod/game/issues/1789))
- env_cascade_light breaks lighting of map compiles ([game/issues/1679](https://github.com/momentum-mod/game/issues/1679))
- env_surface_teleport failing to teleport ([game/issues/1792](https://github.com/momentum-mod/game/issues/1792))
- env_tonemap_controller keeps settings switching to new maps without one ([game/issues/1680](https://github.com/momentum-mod/game/issues/1680))
- func_lod does not show up in game ([game/issues/1324](https://github.com/momentum-mod/game/issues/1324))
- func_precipitation renders precipitation at world center ([game/issues/1695](https://github.com/momentum-mod/game/issues/1695))
- linked_portal_door icon requires portal 2 to be mounted ([game/issues/1440](https://github.com/momentum-mod/game/issues/1440))
- logic_relay_queue crashes the game when doing queues ([game/issues/1488](https://github.com/momentum-mod/game/issues/1488))
- setpause and unpause commands still being used ([game/issues/1388](https://github.com/momentum-mod/game/issues/1388))
- setting "effect detail" to other than high greatly decreases radius of rendering func_lod ([game/issues/1716](https://github.com/momentum-mod/game/issues/1716))
- sj_koi flashlight crash ([game/issues/1593](https://github.com/momentum-mod/game/issues/1593))
- sj_over crash on DX11 ([game/issues/1600](https://github.com/momentum-mod/game/issues/1600))
- skybox-occlusion (compileSkyOcclusion) not correctly occluding ([game/issues/1802](https://github.com/momentum-mod/game/issues/1802))
- snd_mute_losefocus cannot be changed through console ([game/issues/1390](https://github.com/momentum-mod/game/issues/1390))
- surf_bullet / jump_finite_v2 crash/performance hit ([game/issues/1648](https://github.com/momentum-mod/game/issues/1648))
- surf_happyhands crash  ([game/issues/1362](https://github.com/momentum-mod/game/issues/1362))
- trigger_momentum_limitmovement breaks with filternames ([game/issues/1630](https://github.com/momentum-mod/game/issues/1630))
- trigger_momentum_progress does not show ingame ([game/issues/1631](https://github.com/momentum-mod/game/issues/1631))
- win10 Scale and Layout setting messes with ingame resolution ([game/issues/1618](https://github.com/momentum-mod/game/issues/1618))

### Improved (60)

- Add "freeze player on saveloc teleport" toggle ([game/issues/1337](https://github.com/momentum-mod/game/issues/1337))
- Add More Saveloc Commands to Keyboard Settings ([game/issues/1199](https://github.com/momentum-mod/game/issues/1199))
- Add `mom_hud_speedometer_enable` to panorama speedometer settings ([game/issues/1612](https://github.com/momentum-mod/game/issues/1612))
- Add conc cvars to the settings panel ([game/issues/1572](https://github.com/momentum-mod/game/issues/1572))
- Add convar to toggle speedo displays  ([game/issues/1553](https://github.com/momentum-mod/game/issues/1553))
- Add cvar the enable ramp bounce thing. ([game/issues/1616](https://github.com/momentum-mod/game/issues/1616))
- Add helmet for extra server protection ([website/issues/230](https://github.com/momentum-mod/website/issues/230))
- Add in-lobby indicator to main menu ([game/issues/1152](https://github.com/momentum-mod/game/issues/1152))
- Add mom_player_weapon_spawn_desirability to settings ([game/issues/1645](https://github.com/momentum-mod/game/issues/1645))
- Add particle effects to Panorama model panel ([game/issues/1665](https://github.com/momentum-mod/game/issues/1665))
- Add some sort of confirmation when making speedometer changes ([game/issues/1651](https://github.com/momentum-mod/game/issues/1651))
- Add toggles for Discord and Steam rich presence to settings ([game/issues/1556](https://github.com/momentum-mod/game/issues/1556))
- Add toggles for zone outlines to settings ([game/issues/1469](https://github.com/momentum-mod/game/issues/1469))
- Add updated tier1 files from GameNetworkingSockets repo ([game/issues/262](https://github.com/momentum-mod/game/issues/262))
- Add way of specifying model skin in weapon script ([game/issues/1471](https://github.com/momentum-mod/game/issues/1471))
- Allow reload setpos to be used ([game/issues/1490](https://github.com/momentum-mod/game/issues/1490))
- Change in-game quit button to disconnect to menu
- Chat saves current text when exiting and reopening ([game/issues/1548](https://github.com/momentum-mod/game/issues/1548))
- Close static hud menus by repressing the button that opened them ([game/issues/1586](https://github.com/momentum-mod/game/issues/1586))
- Consider Using Steam Encrypted App Tickets for Authentication ([website/issues/303](https://github.com/momentum-mod/website/issues/303))
- Default "author" line to off when no author is specified ([game/issues/1681](https://github.com/momentum-mod/game/issues/1681))
- Default to global times rather than local on official maps ([game/issues/1179](https://github.com/momentum-mod/game/issues/1179))
- Delete and recreate particle effects for projectiles being teleported ([game/issues/1406](https://github.com/momentum-mod/game/issues/1406))
- Disallow changing setting sliders if the setting is turned off ([game/issues/1467](https://github.com/momentum-mod/game/issues/1467))
- Don't show fizzle particles for projectiles destroyed by loading a savestate ([game/issues/1413](https://github.com/momentum-mod/game/issues/1413))
- Dx11 doesn't render some transparent textures properly ([game/issues/1441](https://github.com/momentum-mod/game/issues/1441))
- Enable mom_mv_disable_impact_view_punch in standard game ([game/issues/1731](https://github.com/momentum-mod/game/issues/1731))
- Enter should automatically close chat ([game/issues/1549](https://github.com/momentum-mod/game/issues/1549))
- Expand sv_airdecelerate to all modes & properly restrict it ([game/issues/1384](https://github.com/momentum-mod/game/issues/1384))
- Game movement abstraction ([game/issues/1322](https://github.com/momentum-mod/game/issues/1322))
- Hide the `building_cubemaps` cvar ([game/issues/1754](https://github.com/momentum-mod/game/issues/1754))
- Improve readability of keybinds section in settings (panorama) ([game/issues/1465](https://github.com/momentum-mod/game/issues/1465))
- Include player count in lobby icon on rightnav ([game/issues/1531](https://github.com/momentum-mod/game/issues/1531))
- Investigate optimizing time to mount other games on boot ([game/issues/1328](https://github.com/momentum-mod/game/issues/1328))
- Link Press Kit Page to Bottom of Main Page ([website/issues/492](https://github.com/momentum-mod/website/issues/492))
- Make the conc a required weapon in conc ([game/issues/1592](https://github.com/momentum-mod/game/issues/1592))
- Map info as a sidebar ([game/issues/284](https://github.com/momentum-mod/game/issues/284))
- Map selector redesign ([game/issues/978](https://github.com/momentum-mod/game/issues/978))
- Modernized weapon-switch hud menu ([game/issues/1306](https://github.com/momentum-mod/game/issues/1306))
- Panorama TextEntry tends to eat inputs ([game/issues/1486](https://github.com/momentum-mod/game/issues/1486))
- Panorama colorpicker ([game/issues/1520](https://github.com/momentum-mod/game/issues/1520))
- Panorama console prioritizes autocomplete over fully typed command ([game/issues/1527](https://github.com/momentum-mod/game/issues/1527))
- Panorama settings menu search bar does not allow ctrl+backspace ([game/issues/1419](https://github.com/momentum-mod/game/issues/1419))
- Panorama static HUD menus ([game/issues/1522](https://github.com/momentum-mod/game/issues/1522))
- Panorama textentry doesn't support ctrl+shift+arrow ([game/issues/1482](https://github.com/momentum-mod/game/issues/1482))
- Remove automute from typing too many messages in a lobby ([game/issues/1729](https://github.com/momentum-mod/game/issues/1729))
- Remove mom_ui_menu_background_type ([game/issues/1584](https://github.com/momentum-mod/game/issues/1584))
- Save online zones out to file upon receiving them ([game/issues/1529](https://github.com/momentum-mod/game/issues/1529))
- Set limits for panorama setting Field of view to something sane ([game/issues/1489](https://github.com/momentum-mod/game/issues/1489))
- Stop removing the map-entry--completed class in C++ when a map-entry is selected ([game/issues/1547](https://github.com/momentum-mod/game/issues/1547))
- Update main page BG branding to match new brand direction ([website/issues/523](https://github.com/momentum-mod/website/issues/523))
- Update settings submenu selection on scroll ([game/issues/1433](https://github.com/momentum-mod/game/issues/1433))
- Update weapons on mom_player_weapon_spawn_desirability change immediately ([game/issues/1646](https://github.com/momentum-mod/game/issues/1646))
- Using tab autocomplete in panorama console does not add a space after the command ([game/issues/1540](https://github.com/momentum-mod/game/issues/1540))
- XP Display on stats panel. ([game/issues/1155](https://github.com/momentum-mod/game/issues/1155))
- [Map Selector] Double notched slider component ([game/issues/1545](https://github.com/momentum-mod/game/issues/1545))
- [Map Selector] Tri-state button component ([game/issues/1546](https://github.com/momentum-mod/game/issues/1546))
- [Panorama] Expose convar name for all settings controls ([game/issues/1576](https://github.com/momentum-mod/game/issues/1576))
- [Panorama] Pass convar default value to ChaosSettingsSlider slider default ([game/issues/1577](https://github.com/momentum-mod/game/issues/1577))
- engine_no_focus_sleep unrestricted from mapping mode ([game/issues/1743](https://github.com/momentum-mod/game/issues/1743))
{{</details>}}

---

The response we’ve seen to the playtest is absolutely amazing. We’re currently at **30,000** wishlists, with **13,500** playtesters, and another **12,600** awaiting access. Every time I check the signups, the number of waiting players increases! I cannot wait to get this game in the hands of every single person in the queue!! A gentle reminder: we are granting 50 grants to the playtest every day, and this number will increase to 100 a day at 0.10.0, and 200 a day at 0.11.0!

If you haven’t yet, you can [sign up for the playtest over on our Steam Store page](https://store.steampowered.com/app/669270/Momentum_Mod/), and make sure to [join our (now ~PARTNERED~ !!) Discord server](https://discord.gg/momentummod), check out [our Twitch stream](https://twitch.tv/momentummod), and oh, before I forget, keep on being awesome. 😉

Until [0.9.2](https://github.com/orgs/momentum-mod/projects/14),  
Nick (Gocnak) K.  
Momentum Mod Project Lead