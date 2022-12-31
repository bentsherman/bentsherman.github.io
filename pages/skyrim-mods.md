# Skyrim Modding Research

I've been a fan of The Elder Scrolls since I was in elementary school. To the extent that I am a gamer, it's mostly because I have sunk thousands of hours into these games. That's why I continue to play these games 10, 15, 20 years after they are released, and I'll probably keep playing them for the rest of my life.

That being said, I have never gone deep with my own mod setup for Skyrim. I installed a few mods from the Steam workshop a few years ago, mostly for a gag playthrough where dragons were trains, mudcrabs had top hats, and my primary weapons were a lightsaber and a Dwemer longrifle. And every time an NPC said something about arrows to the knee, or sweetrolls, or the Cloud District... they received "divine punishment". And a few quest mods, but they mostly turned out to be just okay. Now that I was finally settled in my new home, I decided I was ready to pursue a new mod setup in earnest.

And I must say, Skyrim modding has come an incredibly long way. It has reached heights I did not expect. I was overwhelmed by the vast sea of _really good mods_ out there. Fortunately, I just completed a dissertation, so I was experienced in carrying out long bouts of research. I endeavoured to find the best mods in every category and build my own ultimate modded Skyrim.

Consider this page a "living research report", in which I maintain my knowledge of mods across the various aspects of Skyrim, as well as some notes about modding Skyrim in general, like how to detect potential mod conflicts, how to find patches, how to deal with crashes, etc.

## Table of Contents

- [Tools](#tools)
- [Discovering Mods](#discovering-mods)
- [Detecting Mod Conflicts](#detecting-mod-conflicts)
- [Debugging Crashes](#debugging-crashes)
- [Selecting Mods](#selecting-mods)
  - [Mod Categories](#mod-categories)
  - [What About Creation Club?](#what-about-creation-club)

## Tools

It's not just the mods themselves that have improved, it's the tools as well. Here's a list of which tools to use for which purpose, to the best of my understanding:

- Use Mod Organizer 2 (MO2) to install and manage mods
- Use LOOT to report ITMs and deleted references, suggest patches
- Use xEdit to clean ITMs and deleted references from mods, create manual patches
- Use Wrye Bash to create "bashed patches"
- Use .NET Script Framework to produce an error log when your game crashes
- Use DynDOLOD to generate distant LOD for your particular mod list

There are several mod managers out there, such as Vortex, NMM, and Wrye Bash itself. But take it from me -- use MO2, it's Better &trade;.

Seeing all of these tools at once can be daunting when you're just getting started, especially if you're been out of the modding world for several years like I was, so it's important that you take your time getting up to speed. Learn one tool at time, incorporating each one into your setup at the appropriate stage. For example, you'll need to learn MO2 in order to install mods, and you can probably learn DynDOLOD last after you've completed your mod list.

## Discovering Mods

I've been able to find most of my mods on [Nexus](https://www.nexusmods.com/skyrimspecialedition), and I think their interface works pretty well. Some notable features:

- You can search for mods within specific categories, rank them by different metrics such as endorsements or downloads (i.e. to find the most popular mods)
- You can list all the mods by a particular author (i.e. if you like one of their mods then see what else they've made)
- You can glean tons of information from the mod page itself, such as the required mods (including off-site requirements) and requiring mods (which is one way to find patches or enhancements)

## Detecting Mod Conflicts

Mod conflicts happen when two mods edit the same content. For example, if one mod edits the name of a potion while another mod edits the effects of that potion, the two mods will conflict. In this case, whichever mod is loaded later will overwrite the other mod. A more common example is when two mods edit the same world space, such as a mod that overhauls city and a mod that makes a few changes to that city for a new quest. An even crazier conflict might be two mods that edit the animation system or combat AI, although I think it would still result in one mod overwriting the other.

Once you go beyond a few mods, you will inevitably have conflicts, so it will be important for you to know how to detect them and resolve them. Now, I come from the world of software engineering, where we already have good tools and processes for resolving conflicts that occur when multiple engineers work on the same codebase. With mods, resolving conflicts is more of an art. I will walk you through some of the strategies that you can use.

1. **Read the mod description for compatibility notes.** This one is the RTFM for modding. If you download a mod from Nexus, for example, always read the **Description** page in its entirety. The mod author will usually include a section on mod compatibility, especially if their mod is popular, and they will say whether a mod is compatible, and if not, if there is a patch.

   Note, however, that the mod author can't test their mod with every other mod in existence. They will usually test the most commonly-used mods that are likely to conflict with theirs, and they might give some rules-of-thumb like "any mod that doesn't edit X location should be compatible". So if they don't mention a particular mod, you'll have to use your best judgement.

2. **Check for compatibility patches.** Beyond the mod description, there are a few easy ways to check for patches.

   In Nexus, there is a **Requirements** dropdown with a section called **Mods requiring this file**. You can quickly scan this section to see if there are any patches for other mods that you use. You can also check the **Files** section for patches from the mod author, although they usually mention these patches in the mod description.

   You can use LOOT to search for mod conflicts and patches. While LOOT is primarily used to sort mods, it also maintains a registry of known mod conflicts and patches, and it will flag these for you. I don't even use LOOT for sorting (more on that later). LOOT's registry contains much of the information you would have found on Nexus, so it's a good way to catch anything you missed. That being said, don't let it become a crutch -- you should still always read the mod descriptions.

3. **Understand how different kinds of mods interact.** Ultimately, you'll want to gain an intuition for the different mod "categories" and which kinds of mods are likely to conflict with each other. This intuition can't be taught, but you will learn over time as you research mods. See my section below on [mod categories](#mod-categories).

   For what it's worth, most of the patches in my mod list are between city overhauls and quest mods. I also spent a long time figuring out which combat mods I could use together, but it turns out that "combat" encompass multiple aspects of the game that are (mostly) independent from each other, so I didn't need very many combat-related patches.

## Debugging Crashes

Skyrim can crash for a lot of different reasons, so the solution will depend on the nature of the crash. The [/r/SkyrimMods](https://www.reddit.com/r/skyrimmods/wiki/troubleshooting_guide/) troubleshooting guide is the most comprehensive guide that I have found. In fact, I learned much of what I know through the guides on that subreddit, and I only hope to provide a gentler overview on this page.

First things first, you should take steps to prevent crashes in the first place:

- WHen you install a mod, make sure to install all of its dependencies. On Nexus, you can find a mod's dependencies under the **Requirements** dropdown, and Nexus will usually alert you about them anyway when you go to download a mod.

- Make sure your mod plugins are ordered sensibly: ESMs should be first, plugins should not be missing any required plugins, and plugins should come after their required plugins. In MO2, you can check all of these things under the **Plugins** tab. Plugins will show an alert icon if they are missing any dependencies.

- In general, just follow the mod author's instructions for every mod you download, no matter how tedious it feels. Do it *when you install the mod* -- if you push it off, you are much more likely to forget something. I cannot stress this point enough. It is much harder to debug a crash caused by a misconfigured mod, than it is to install the mod correctly the first time.

Hopefully these measures will save you from 90% of crashes. But, if you are using hundreds of mods, your game will still probably crash from time to time. Even with the best mod hygiene, you still need to know how to debug. So, here are some options:

- You can use the [.NET Script Framework](https://www.nexusmods.com/skyrimspecialedition/mods/21294) to generate an error log whenever your game crashes. It's like a plugin, but for the *game engine* rather than the game world. When your game crashes, you'll find a new error log with a bunch of diagnostic information. The error log can help you find the root cause by identifying plugins that may have contributed to the crash.

- In some cases, you might be able to use context clues to figure out the root cause. Does the game always crash in a particular area? Or at a particular stage in a quest? Or when a particular event happens? If you suspect a particular mod, disable the mod and try to reproduce the crash.

- If all else fails, your final option is to disable and re-enable mods one at a time until you reproduce the crash. It is the "brute force" approach, and it's last because it's the most time-consuming. To save some time, disable half of your mods at a time until the crash doesn't happen. Then, re-enable each mod from the last "half", one at a time, until the crash happens again. This approach should allow you to figure out just about any remaining crash.

I learned some of these lessons the hard way. While I did try to install everything correctly, I forgot to scrutinize my plugin order because I thought Mod Organizer was syncing it with my mod order, when in fact these two things are independent. Somehow, my game still worked for a while, and I suspect that the game engine is able to handle some basic ordering issues on-the-fly. But, as I explored more of the world, I began to experience more crashes and other weirdness. I fixed most of these issues by correcting my load order and adding a few patches I had been missing (they were flagged by LOOT). The .NET Script Framework helped me identify a few mods that were consistently causing crashes, and I usually ended up removing these mods.

## Selecting Mods

In this section, I will try to demonstrate how to pick mods by walking you through my mod setup.

Researching and selecting mods is by far the most time-consuming aspect of modding for me. In case you haven't noticed, there are a lot of mods. _Way too many_ mods to try them all in one go.

More importantly, game saves are fragile. Most mods can't be cleanly removed after they are added, and some mods can't even be cleanly added mid-game. Yes, you can use the [Script Cleaner](https://www.nexusmods.com/skyrimspecialedition/mods/34601) to "clean" a save after removing mods, but in reality, the idea of "cleaning" a save is a delusion, and the only way to cleanly remove a mod is to revert to a save from before before the mod was added. In some cases you might get lucky -- mods that don't add scripts can usually be removed without much issue. But must mods of any interest use scripts, so don't count on it.

The point is, if you care about a save game, you should care about the mods you add to it. Ideally, you should test new mods one at a time and always save before you add a mod. Of course, it's not always so easy in practice. Some mods have wide-ranging effects on the game, you may have to play it for a while before you know whether or not you like it, and you probably won't want to test one mod at a time when you have a bunch of mods that you want to play together. I dealt with all of these problems because I had several years of new mods to evaluate all at once.

### Mod Categories

Navigating the great sea of mods is much easier once you have an idea of the main categories and the choices that you have within each category. Here I will walk you through the main categories that I use to organize my mods. At this point I've mostly converged with the Nexus categories, but I only get as detailed as I need for it to be helpful.

*NOTE*: This section is not an exhaustive mod list. In particular, I didn't include all of the dependencies required to use these mods. As always, make sure you follow the installation instructions for every mod you use.

#### Bug Fixes

The most commonly used bugfix mods by far are Arthmoor's Unofficial Skyrim Special Edition Patch (USSEP) and Cutting Room Floor (CRF). USSEP fixes a bunch of bugs while CRF adds a bunch of extra content that was in the game files but removed from the world. I could probably live without these mods, but I use them anyway because some mods depend on them.

If you're using SKSE, there are a bunch of SKSE plugins out there that provide various "fixes" and "tweaks" to the game engine. The only one that I've used thus far is SSE Engine Fixes, because it actually prevents certain kinds of crashes. Beyond that, I haven't found any consensus on what other "tweaks" plugins are worthwhile, or tested any of them myself. Otherwise, I only use another bugfix plugin if it's required by another mod (e.g. powerofthree's Tweaks).

- Cutting Room Floor
- SSE Engine Fixes
- Unofficial Skyrim Special Edition Patch

#### User Interface

I'm pretty happy with the UI mods that I've settled on. All of these mods are solid, and they work together seamlessly.

I'll just highlight some of my favorites. Alternate Conversation Camera gives you an Oblivion-style dialogue zoom that feels more immersive (IMO). Immersive HUD allows you to keep your screen entirely HUD-free, while only displaying HUD elements when they are needed. Sovngarde is a font that feels much more like Elder Scrolls. The Loading Screens mod adds a bunch of beautiful and lore-friendly loading screens based on artwork from Elder Scrolls Legends.

- Alternate Conversation Camera
- Fuz Ro D-oh - Silent Voice
- Immersive HUD
- Nordic UI
- SkyHUD
- SkyUI
- Sovngarde - A Nordic Font
- The Elder Scrolls Legends - Loading Screens
- TrueHUD - HUD Additions

#### Gameplay: Animation

It feels like the Skyrim animation modding scene exploded after the pandemic. Thanks to tools like Nemesis and DAR, modders have been able to use animations in some really cool ways. Note that some of the combat mods also involve animation, but I listed them under the Combat section.

At some point I'm going to try out [EVG Animated Traversal](https://www.nexusmods.com/skyrimspecialedition/mods/63232) and all the downstream mods that incorporate it into the world.

- EVG Animation Variance
- EVG Conditional Idles
- EVG Pristine Vanilla Movement
- Immersive Interactions
- Take a Seat

#### Gameplay: Combat

Out of all the categories, I think the combat mods took the longest for me to figure out. It was difficult in part because "combat" encompasses things like animation, behavior, AI, and mechanics, so it was hard to figure out which mods could be used together.

Here are some highlights. SkySA introduces "attack commitment", which causes you to step into every attack you make. TK Dodge allows you to... dodge. True Directional Movement introduces several features, including 360 degree movement and enemy tracking. Ultimate Combat makes enemies more aggresive and strategic in combat. ZUPA introduces a potion drinking animation, so that you can't spam healing potions during combat.

All in all, these mods make the combat in Skyrim feel more like The Witcher 3 or Dark Souls. These games have a much better third-person combat experience (IMO) because they give you more tools (e.g. dodging and parrying) and require you to play smarter in order to win. In fact, if you only play Skyrim in first-person, then most of these mods will not affect you. On the other hand, maybe you're playing in first-person because third-person is actually bad, and these mods just might make you switch.

- Hellblade - Timed Block
- Precision - Accurate Melee Collisions
- Shield Of Stamina - Blocking Redux
- SkySA
- SkySA Movesets
- SmoothCam
- SmoothCam Modern Camera Preset
- TK Dodge RE
- True Directional Movement
- Ultimate Combat
- zxlice ultimate potion animation (ZUPA)

Because of the flurry of new combat mods each year, there are a few mods I haven't tried yet:

- [Attack MCO](https://www.skyrim-guild.com/mods/attack) (would replace SkySA)
- [Dodge MCO](https://www.skyrim-guild.com/mods/dodge) (would replace TK Dodge)
- [SCAR](https://www.nexusmods.com/skyrimspecialedition/mods/72014)
- [Valhalla Combat](https://www.nexusmods.com/skyrimspecialedition/mods/64741) (would replace Hellblade, Shield of Stamina)

#### Gameplay: Mechanics

This category is kind of a catch-all for other gameplay mods. Like combat, "gameplay" encompasses lots of different things.

Andromeda, Odin, and Vokrii are part of the "EnaiRim" collection of gameplay mods by the modder Enai. I haven't gone very far down the EnaiRim rabbit hole, but these mods stood out to me and so far I've enjoyed them. Maybe one day I'll try some of his more heavyweight mods like Apocalypse and Ordinator.

ALl of the other mods are also worth highlighting. Simply Knock allows you to enter a locked building by asking the owner to let you in. Sojourn Over Signposts makes fast travel allowed only by interacting with a signpost, forcing you to move through the world instead of the map menu. Take a Peek allows you to peek through the keyhole of a door and see what's on the other side. Wet and Cold makes NPCs wear cloaks and hoods when it rains or snows, and also makes them run inside during storms. All of these mods are among my favorites for their simplicity and the clear value they add to the game.

- Andromeda - Unique Standing Stones of Skyrim
- Odin - Skyrim Magic Overhaul
- Simply Knock
- Sojourn Over Signposts - Witcher-Style Fast Travel Alternative
- Take a Peek - New Stealth Mechanic
- Vokrii - Minimalistic Perks of Skyrim
- Wet and Cold

#### Audio

Audio mods typically either improve or replace existing sounds, or add new sounds, where "sounds" could be sound effects, dialogue, or music. Despite my background as a musician, I am not the stereotypical "audiophile" -- I don't keep all my music in a lossless format or listen to everything with ultra-high quality headphones. So I probably don't fully appreciate the quality improvement mods like Ludicity, HQ Music, and HQ Voices. However, I do appreciate the new sound effects added by Sounds of Skyrim (one of the first mods I ever used), and I can certainly appreciate the new bard music provided by Badass Bard Songs.

Other notable mods include Immersive Sounds and the Unofficial HD Audio Project. They look like excellent mods, I just don't use them because they are incompatible with my current setup.

- BA Bard Songs
- Bandit Lines Expansion
- Lucidity Sound FX
- Reverb and Ambiance Overhaul
- Sounds of Skyrim Complete
- SSE High Quality Music
- SSE High Quality Voices

#### Visuals

Visual mods are another category that took me a while to research, and one that I will continue to experiment with as I understand it better. Like combat, there are multiple aspects to lighting, so you really have a lighting "stack". There are multiple options for each layer in the stack, and some mods are designed to "play well" with specific mods from other layers. Also, each layer is optional, so you can decide how far you want to go with the graphics overhauls.

First, pick your ENB preset. [ENB](http://enbdev.com/) itself is a library that adds a bunch of fancy effects to the game engine's graphics pipeline, like Depth of Field and Sun Rays. To enable these effects, you have to configure ENB, but most people just use a preset created by someone else who knows what they're doing. Here are some notable options:

- Bjorn ENB-Reshade
- Rudy ENB
- Silent Horizons ENB
- SkyrimSE Re-Engaged ENB

Next, pick your ReShade preset. [ReShade](https://reshade.me/) is another library that adds graphics effects to video games, similar to ENB. I'm not really sure how they are different, but there appears to be some consensus around using ENB and ReShade together. Some notable options:

- Bjorn ENB-Reshade
- Nolvus Reshade

(Note that Bjorn includes both an ENB preset and a ReShade preset.)

Next, pick a weather mod. Weather mods overhaul everything about the weather in Skyrim to give it a certain look and feel, from the sky textures to storm audio effects to ambient lighting for each weather type. Some notable options:

- Aequinoctium - Weathers and Seasons
- Cathedral Weathers and Seasons
- Natural and Atmospheric Tamriel (NAT)
- Obsidian Weathers and Seasons

Next, pick a lighting mod. Lighting mods make light sources (e.g. torches, lanterns, fire pits) and their shadows more pronounced, making the game feel darker overall but also more dynamic. Lighting mods typically have separate interior and exterior components, and they tend to require patches for everything. But they are worth it!

Interior lighting mods:

- Enhanced Lights and FX (ELFX)
- Lux

Exterior lighting mods:

- ELFX Exterior
- Lux Orbis
- Lux Via
- Tamriel Master Lights

My current "stack" is Rudy ENB, Nolvus Reshade, Obsidian Weathers, and ELFX (Interiors and Enhancer only). I haven't picked an exterior lighting mod yet -- I'm considering Tamriel Master Lights, but I'm afraid of all the patches I might need. I got this mod combination from Heavy Burns, who spent a lot more time than me experimenting with visual mods. However, now that I have more experience on my own, the next combination I'd like to try is Bjorn, Cathedral, and Lux.

It is typical for ENB preset authors to create patches for specific weather and lighting mods. For example, since I use Rudy ENB, Obsidian Weathers, and ELFX, I also use the "Rudy ENB for Obsidian Weathers and ELFX" patch.

Finally, there are a few more lighting mods that are good to have in general:

- ENB Grass Collisions
- ENB Light
- ENB Lights for Effects Shaders
- Enhanced Volumetric Lighting and Shadows (EVLaS)
- Window Shadows

#### Models and Textures

Models (aka meshes) and textures are the 3D and 2D assets that comprise everything you see in the game world, from the landscape and the sky to buildings and items and people. Basically every Elder Scrolls game ships with mediocre assets, probably so that they can push the limits on other fronts like world size and AI complexity. Inevitably, modders bring higher resolutions and polygon counts to each game, but some modders also take the opportunity to create their own look and feel, especially with textures. You can make Skyrim look like a [very different game](https://www.nexusmods.com/skyrim/mods/33017) with only a texture pack.

Model and texture mods can be divided into "base" mods that cover everything and "additional" mods that cover only a subset of objects. The small mods tend to be more focused and detailed, and more subject to individual preferences. A good practice is to apply your "base" mods first, then apply any smaller mods to suit your taste.

For models, start with Static Mesh Improvment Mod (SMIM) and High Poly Project (HPP). These mods simply improve all 3D models throughout the game. For textures, there are a plethora of "all-in-one" texture packs to choose from:

- CleverCharff’s AIO
- Noble Skyrim
- Pfuscher’s Skyrim 202X
- Skyland AIO

I use Pfuscher's Skyrim followed by Noble Skyrim. For "additional" mods, I will just list the few that I currently use:

- aMidianBorn Book of Silence
- Blended Roads
- Daedric Shrines - All in One
- Embers HD
- Majestic Mountains Lightside

All of these mods are highly regarded, and you'll probably find them on most mod lists. Beyond that, there is an endless stream of mods for weapons, armor, flora, clutter, furniture, creatures, and so on, and you really have to figure out for yourself which ones you like. A good strategy is to find modders that you like and keep up with their mod releases, which should make it easier to create a consistent look and feel for your game. Some well-known modders include [DrJacopo](https://www.nexusmods.com/skyrimspecialedition/users/50222836), [ElSopa](https://www.nexusmods.com/skyrimspecialedition/users/6960827), [mathy79](https://www.nexusmods.com/skyrimspecialedition/users/12770808), and [rudy102](https://www.nexusmods.com/skyrimspecialedition/users/93362). I'm content at the moment with the base texture overhauls, so I don't use anything else, but if I ever go further down the rabbit hole, I'll probably start with these modders.

#### Environment

Environmental mods mainly add content to the natural world (e.g. trees, grass, water), but may also include new models and textures. Here are the mods I currently use:

- Folkvangr
- Happy Little Trees
- Morning Fogs
- Origins of the Forest
- Origins of the Forest Reduced
- Realistic Water Two
- Volumetric Mists

Another popular water mod is Water for ENB. I honestly couldn't tell you which one I like more, they both look really good to me, but you should use one or the other.

#### Locations

Location, location, location. Yet another category that took me forever to decide on. There are so many cool city overhauls, and I wish I could have them all at once, but alas, I must choose.

The most popular city overhauls that I have found are JK's Skyrim, Dawn of Skyrim, Cities of the North, and The Great Cities. Although I haven't actually tried it, I believe it is possible to use all of these mods together with only two patches -- one patch for JK and DoS, and another patch called The Great Cities of JK's North. These patches are possible mainly because the four mods are somewhat complementary -- JK adds clutter and small details, DoS overhauls the major cities, and CotN and TGC overhaul the minor cities and towns.

So, if you want to keep things simple while achieving maximum coverage, try this combo and be done with it.

But if you want to take things further, there are some really good expansion mods for Solidute, Whiterun, and Windhelm. The easiest way to introduce them into the mix is to remove JK's Skyrim and instead use [JK's Markarth](https://www.nexusmods.com/skyrim/mods/58283) and [JK's Riften](https://www.nexusmods.com/skyrim/mods/58489). Or, you might be able to keep JK's Skyrim if you can find a patch for each city overhaul. I haven't tried the latter approach yet because I ran out of patience. I don't know how you would keep DoS at this point.

Finally, there are overhauls for various other locations. I haven't checked all of these mods for compatibility with JK's Skyrim since I resorted to using JK's individual mods anyway. Here is my current list:

- Better Tel Mithryn
- Capital Whiterun Expansion
- Capital Windhelm Expansion
- Cities of the North - Dawnstar
- Cities of the North - Falkreath
- Cities of the North - Morthal
- Cities of the North - Winterhold
- Cities of the North Addon - Anga's Mill
- Cities of the North Addon - Half-Moon Mill
- City Entrances Overhaul - Markarth
- City Entrances Overhaul - Windhelm
- Enhanced Solitude
- Enhanced Solitude Docks
- Greater Skaal Village
- Grey Quarter Expansion
- Immersive Fort Dawnguard
- JK's High Hrothgar
- JK's Markarth
- JK's Riften
- JK's Riverwood
- JK's Sky Haven Temple
- Nordic Ruins of Skyrim
- Obscure's College of Winterhold
- Palaces and Castles Enhanced
- Quaint Raven Rock
- The Great Cities - Minor Cities and Towns
- The Great Settlement of Darkwater Crossing
- The Great Settlement of Kolskeggr Mine
- The Great Town of Ivarstead
- The Great Town of Karthwasten
- The Great Town of Shor's Stone
- The Great Village of Kynesgrove
- The Great Village of Mixwater Mill
- The Great Village of Old Hroldan

In my next iteration, I will try to include JK's Skyrim and all of JK's interior mods. I might still be able to keep the individual city overhauls depending on compatibility with quest mods. I will probably have to drop Enhanced Solitude and/or the Docks, which might be for the best anyway since those mods are a bit much for my machine.

#### NPCs

NPC mods include body / face / hair replacers, companions, and population mods.

I don't care that much about body mods because everyone is almost always clothed... at least in *my* playthroughs. If you want a body mod, CBBE is a good place to start, at least for female bodies. As for face and hair replacers, here are a few good options:

- Bijin Warmaidens
- Cathedral Player and NPC Overhaul
- Diversity - A Character Overhaul
- High Poly NPC Overhaul
- Modpocalypse NPCs
- Pandorable's NPCs
- RS Children Overhaul
- TK Children

I use Diversity and RS Children (as well as Realistic RS Children), which provides a good vanilla-friendly uplift to basically every NPC in the game. Cathedral also looks really good to me. A lot of face and hair mods make everything too smooth for my taste, or they only update a few characters, leaving everyone else to wallow in their relative ugliness. But to each their own.

Another thing I haven't tried yet is [HDT-SMP](https://www.nexusmods.com/skyrimspecialedition/mods/57339), an SKSE plugin that adds support for body, hair, and clothing physics. I know you can use [Artesian Cloaks of Skyrim](https://www.nexusmods.com/skyrimspecialedition/mods/17416) to add physics to the cloaks from Wet and Cold, but I haven't found anything for the hair from Diversity.

Some of my favorite mods are companion mods. If you decide not to mess with any mods, then at the very least, pick a good companion mod (or three) and start a new game. Some of these companions will really enrich your time in the game world, and they'll surprise you with some of the things they say. As much as I love playing with graphics and combat mods in Skyrim, the things that always keep me interested are good stories and *good characters*.

Here are the companions I've played with and enjoyed:

- INIGO
- Lucien
- Sofia
- Song of the Green (Auri Follower)
- Vilja in Skyrim

Some other mods that I haven't tried yet:

- Ambriel - The Lost Princess
- Arissa - The Wandering Rogue
- Aurlyn Dawnstone - The Reclusive Philosopher
- Hoth
- Kaidan 2
- Mirai - the Girl with the Dragon Heart
- Nebarra
- Recorder
- Serana Dialogue Add-On
- Shirley
- Skeever

The biggest question I had with companion mods was how to have more than one follower at a time. As it turns out, most of these companion mods implement their own "follower quest", which means that these companions don't use the default follower quest and therefore aren't beholden to any follower limits. So you could have all of these companions follow you at the same time and still have one vanilla follower.

That being said, I still ended up using a follower framework, specifically Nether's Follower Framework, to remove this limit and take advantage of some other nice features. There are several such frameworks, and I'm sure they all work just as well, but NFF seemed to me like the most lightweight option. I think my favorite feature in NFF is that your followers will "sandbox" (e.g. sit down, order food and drink, use crafting stations) whenever you remain in one area. This behavior is much more immersive than *standing right behind you* at all times.

Finally, I use a variety of "population" mods that make the general population more interesting, either by improving the AI of existing NPCs or adding new NPCs:

- Citizens of Tamriel
- Immersive Citizens - AI Overhaul
- Immersive Patrols
- Interesting NPCs (3DNPC)
- Populated Dungeons Caves Ruins
- Populated Forts Towers Places

CoT and 3DNPC collectively add hundreds of unique NPCs to the game, with tons of dialogue and quests. Based on what I've seen so far in my current playthrough, many of these NPCs rival or exceed their vanilla counterparts with their personalities and backstories. ICAIO overhauls the behavior and schedules of many vanilla NPCs to be more realistic (Sinmir actually leaves the Bannered Mare from time to time).

I initially used the entire Populated series of mods because I wanted to have *tons* of generic NPCs like the Witcher 3. These mods add generic NPCs to cities and towns and roads, hostile NPCs and creatures to dungeons, and huge civil war battles across the map. After playing for a while, some of these mods started to cause weird crashes (possibly an incompatibility with other mods) and had to be removed. Also, I realized that the unique NPCs from CoT and 3DNPC, although fewer in number, added so much more to my gameplay experience than the generic NPCs, and in fact were plentiful enough to make the world feel more "populated". In the end, I only kept the dungeon-related mods, since they provide a necessary difficulty bump to compensate for all of my new companions.

#### Quests

Under "quest" mods I lump together mods that add quests to Skyrim, mods that add new locations, and total conversion mods.

I think quest mods get the most hype because they promise "X hours of new gameplay", and people are willing to wait for ambitious mods because they understand how much work goes into making them. After playing through many such mods across multiple Elder Scrolls games, I've learned that not every quest mod is *really* worth playing. A mod can add entirely new lands filled with NPCs and quests, but if the stories and dialogue aren't very memorable, or even if it just feels like more of the same Skyrim content, I end up feeling like it wasn't worthwhile.

I feel harsh saying these things, because I know how much time and effort goes into quest mods, and for little to no compensation. But the reality is that there are *so many* mods out there, more than I will ever have time to play, so I want to find the very best of them. Not just the *most popular* mods, but the *best* mods. I want to experience something that I wouldn't find in the original game. This is why I can enjoy smaller but unique mods, like The Bottomless Pit and The Forgotten City, way more than larger but relatively mundane mods like Falskaar and Wyrmstooth.

Here are the mods that I really enjoyed:

- Clockwork
- Enderal
- Faction - Pit Fighter
- Helgen Reborn
- Project AHO
- The Bottomless Pit
- The Forgotten City

Here are the mods that I thought were just okay:

- Falskaar
- Here There Be Monsters
- Moon and Star
- Moonpath to Elsweyr
- Wyrmstooth

The mods I'm currently playing through:

- Carved Brink
- Leaps of Faith - A Misc Quest
- Legacy of the Dragonborn
- Quest Expansions by jayserpa
- The Gray Cowl of Nocturnal
- There Is No Umbra - Chapter II

The mods I'm looking forward to playing (mods marked WIP haven't been released at the time of writing):

- Apotheosis (WIP)
- Beyond Reach
- Beyond Skyrim - Bruma
- GLENMORIL
- Konahrik's Accoutrements
- Odyssey of the Dragonborn (WIP)
- Rigmor of Bruma
- Rigmor of Cyrodiil
- Shezarrine - The Fate of Tamriel - Prologue
- Sirenroot (WIP)
- Skyblivion (WIP)
- Skyrim: Extended Cut (WIP)
- Skywind (WIP)
- Trainwiz' Aethernautics - A Space Travel Mod
- Trainwiz' Blackreach Railroad
- Trainwiz' Brhuce Hammar Legacy
- Trainwiz' The Lost Wonders of Mzark
- Trainwiz' The Wheels of Lull
- Undeath Remastered
- UNSLAAD
- VIGILANT

Looks like I have enough adventures in my backlog to keep me busy for a while!

I'll end with a few mods that provide some general quality improvements rather than big quests. Alternate Start (and the New Beginnings extension) allows you to start the game any number of ways instead of Helgen (you can still start the main quest by traveling to Helgen and inspecting the aftermath). At Your Own Pace tweaks the main quest and faction quests to feel less urgent and not make you the center of attention so much. Immersive World Encounters adds a bunch of random encounters to the game, and also serves as a lightweight population mod.

- Alternate Start - Live Another Life
- At Your Own Pace
- Immersive World Encounters
- New Beginnings - Live Another Life Extension

#### What About Creation Club?

The Anniversary Edition of Skyrim comes with all of the Creation Club content, which was partly what motivated me to give Skyrim another go. The CC content is considered canon, and I like to keep up with Elder Scrolls lore, so I decided to buy the AE upgrade and try out the CC addons for myself. So, since we're already going through my mod setup, I'll give you my two cents on Creation Club.

Ultimately, I think most of the CC content is just fine. They are all high-quality mods by skilled modders, but most of them just didn't add much value for me, especially among all the other mods I already have. In future playthoughs, I will probably only keep a few of the Creation Club mods:

- Adventurer's Backpack
- Alternative Armors (all 15 of them)
- Arcane Archer Pack
- Bittercup
- Camping
- Expanded Crossbow Pack
- Fishing
- Shadowrend
- Survival Mode

TBD:

- Arcane Accessories
- Dwarven Armored Mudcrab
- Forgotten Seasons
- Ghosts of the Tribunal
- Nchuanthumz: Dwarven Home
- Necromantic Grimoire
- Netch Leather Armor
- Nix-Hound
- Rare Curios
- Ruin's Edge
- Staff of Sheogorath

The Alternative Armors collection was probably my favorite CC content, because all of the armor sets are connected by a commen story, the rise and fall of the Crimson Dirks. It was great fun to find each armor set and learn about the Crimson Dirk who wore it. And while I dropped most of the other weapon and armor mods, I kept Shadowrend in particular because of the... unique combat situation that it provides.

Many of the other CC mods were dropped because they add artifacts that are already covered by other mods such as Legacy of the Dragonborn, The Gray Cowl of Nocturnal, and There is No Umbra. Additionally, the team behind Skyrim: Extended Cut released an [extended cut of Saints and Seducers](https://www.nexusmods.com/skyrimspecialedition/mods/72772). So far, I have enjoyed these mods more than their CC counterparts.

Here are the CC mods already covered by Legacy of the Dragonborn:

- Bow of Shadows
- Chrysamere
- Dawnfang & Duskfang
- Dead Man's Dread
- Divine Crusader
- Goldbrand
- Lord's Mail
- Staff of Hasedoki
- Stendarr's Hammer
- Sunder & Wraithguard
- The Contest

Like I said before, all of the CC mods are good, and any one of them could make a fine addition to the right playthrough. Depending on your mod setup or character build, you might choose differently from me. Lots of people like to dunk on these mods because they didn't like the Creation Club as a concept, which I understand, but I don't feel strongly about it either way. I'm just very minimalist with mods, especially small mods, so most CC content just doesn't make the cut.

(And yes, for the amount of coverage I'm getting, the ~150 mods I'm using are pretty minimal.)
