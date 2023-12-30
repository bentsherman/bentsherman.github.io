# Skyrim Mods

*Epistemic Status: basically done*

I've been playing Elder Scrolls games since I was in elementary school. To the extent that I am a gamer, it's mostly because I've' sunk thousands of hours into these games. That's why I continue to play them 10, 15, 20 years later, and I'll probably keep playing them for the rest of my life.

That being said, I've never gone deep with my own mod setup for Skyrim. I installed a few mods from the Steam workshop a few years ago, mostly for a gag playthrough with trains for dragons, mudcrabs with top hats, lightsabers, a Dwemer longrifle, "divine punishment" for any NPC who said anything about arrows to the knee, or sweetrolls, or the Cloud District... and some quest mods that turned out to be just okay. After getting married, finishing my PhD, and moving to Texas, I decided I was ready to pursue a new mod setup in earnest.

And I must say, Skyrim modding has come an incredibly long way. It has reached heights I did not expect. I was overwhelmed by the vast sea of *really good mods* out there. Fortunately, since I had just completed a dissertation, I had some experience with long bouts of research. So, I endeavoured to find the best mods in every category and build my own ultimate mod list.

Consider this page a living guide, in which I maintain my knowledge of Skyrim mods across various aspects of the game, as well as some notes about modding Skyrim in general, like how to detect potential mod conflicts, how to find patches, how to deal with crashes, etc. I hope this guide can be for you what I wish I had when I started.

## Table of Contents

- [Tools](#tools)
- [Discovering Mods](#discovering-mods)
- [Selecting Mods](#selecting-mods)
  - [Bug Fixes](#bug-fixes)
  - [User Interface](#user-interface)
  - [Gameplay](#gameplay)
  - [Audio](#audio)
  - [Visuals](#visuals)
  - [Models and Textures](#models-and-textures)
  - [Environment](#environment)
  - [Locations](#locations)
  - [Items](#items)
  - [NPCs](#npcs)
  - [Quests](#quests)
  - [Patches](#patches)
  - [What About Creation Club?](#what-about-creation-club)
  - [What About Anniversary Edition?](#what-about-anniversary-edition)
- [Detecting Mod Conflicts](#detecting-mod-conflicts)
- [Debugging Crashes](#debugging-crashes)
- [Additional Resources](#additional-resources)

## Tools

It's not just the mods themselves that have improved, it's the tools as well. Here's a list of which tools to use for which purpose, to the best of my understanding:

- Use Mod Organizer 2 (MO2) to install and manage mods
- Use LOOT to report ITMs and deleted references, suggest patches
- Use xEdit to clean ITMs and deleted references from mods, create manual patches
- Use Wrye Bash to create "bashed patches"
- Use .NET Script Framework to produce an error log when your game crashes
- Use DynDOLOD to generate distant LOD for your particular mod list

There are several mod managers out there, such as Vortex, NMM, and Wrye Bash itself. But take it from me -- use MO2, it's Better &trade;.

Seeing all of these tools at once can be daunting when you're just getting started, especially if you've been out of the modding world for several years like I was, so it's important that you take your time getting up to speed. Learn one tool at time, incorporating each one into your setup at the appropriate stage. For example, you'll need to learn MO2 in order to install mods, and you can probably learn DynDOLOD last after you've completed your mod list.

## Discovering Mods

I've been able to find most of my mods on [Nexus](https://www.nexusmods.com/skyrimspecialedition), and I think their interface works pretty well. Some notable features:

- You can search for mods within specific categories, rank them by different metrics such as endorsements or downloads (e.g. to find the most popular mods)
- You can list all the mods by a particular author (e.g. if you like one of their mods then see what else they've made)
- You can glean tons of information from the mod page itself, such as the required mods (including off-site requirements) and requiring mods (which is one way to find patches or enhancements)

## Selecting Mods

In this section, I will try to demonstrate how to pick mods by walking you through my mod setup.

Researching and selecting mods is by far the most time-consuming aspect of modding for me. In case you haven't noticed, there are a *lot* of mods. Way too many mods to try them all at once.

More importantly, saves are fragile. Most mods can't be cleanly removed after they are added, and some mods can't even be cleanly added mid-game. Yes, you can use the [Script Cleaner](https://www.nexusmods.com/skyrimspecialedition/mods/34601) to "clean" a save after removing mods, but in reality, the idea of "cleaning" a save is a delusion. The only way to cleanly remove a mod is to revert to a save from before the mod was added. In some cases you might get lucky -- mods that don't add scripts can usually be removed without much issue. But most mods use scripts, so don't count on getting lucky.

The point is, if you care about a save game, you should care about the mods you add to it. Ideally, you should test new mods one at a time and always save before you add a mod. Of course, it's not always so easy in practice. Some mods have wide-ranging effects on the game, you may have to play with a mod for a while before you know whether or not you like it, and you probably won't want to test one mod at a time when you have a bunch of mods that you want to use together. I dealt with all of these challenges because I had several years of new mods to evaluate all at once. Just do the best you can.

Navigating the great sea of mods is much easier once you have an idea of the main categories and the choices that you have within each category. Here I will walk you through the categories that I use to organize my mods. At this point, I've mostly converged with the Nexus categories, but I only use as many categories as I find helpful.

*NOTE*: This section is not an exhaustive mod list. In particular, I didn't include all of the dependencies required to use these mods. As always, make sure you follow the installation instructions for every mod you use.

### Bug Fixes

The most commonly used bugfix mods by far are Arthmoor's Unofficial Skyrim Special Edition Patch (USSEP) and Cutting Room Floor (CRF). USSEP fixes a bunch of bugs while CRF adds a bunch of extra content that was in the game files but removed from the world. I could probably live without these mods, but I use them anyway because they're nice to have and some mods depend on them.

If you're using SKSE, there are a bunch of SKSE plugins out there that provide various "fixes" and "tweaks" to the game engine. The only one that I've used thus far is SSE Engine Fixes, because it supposedly prevents certain kinds of crashes. Beyond that, I haven't found any consensus on what other "tweaks" plugins are worthwhile, or tested any of them myself, but I will use other bugfix plugins if they are required by a mod (e.g. powerofthree's Tweaks).

- Cutting Room Floor
- SSE Engine Fixes
- Unofficial Skyrim Special Edition Patch

### User Interface

I'm quite happy with the UI mods that I've settled on. All of these mods are solid, and they work together seamlessly.

I'll just highlight some of my favorites. Alternate Conversation Camera gives you an Oblivion-style dialogue zoom that feels more immersive (IMO). Immersive HUD allows you to keep your screen entirely HUD-free, while only displaying HUD elements when they are needed. Sovngarde is a font that feels much more like Elder Scrolls. The Loading Screens mod adds a bunch of beautiful and lore-friendly loading screens based on artwork from Elder Scrolls Legends.

- Alternate Conversation Camera
- Better Third Person Selection
- Fuz Ro D-oh - Silent Voice
- Immersive HUD
- Nordic UI
- Quickloot EE
- SkyHUD
- SkyUI
- Sovngarde - A Nordic Font
- The Elder Scrolls Legends - Loading Screens
- TrueHUD - HUD Additions

### Gameplay

What even is "gameplay"? This category probably took me the longest to figure out. Gameplay, at least in my mind, encompasses many aspects of the game, including animation, behavior, combat, player controls, skills and leveling, and of course, "mechanics". All of these aspects are closely related, so it was hard to tell which mods could be used together.

To make things as simple as possible, I will use three broad categories: animation, combat, and mechanics.

#### Animation

It feels like the Skyrim animation modding scene exploded after the pandemic. Thanks to tools like Nemesis and DAR, modders have been able to use animations in some really cool ways.

- EVG Animation Variance
- EVG Conditional Idles
- EVG Pristine Vanilla Movement
- Immersive Interactions
- Take a Seat

At some point I'm also going to try out [EVG Animated Traversal](https://www.nexusmods.com/skyrimspecialedition/mods/63232) and all the downstream mods that incorporate it into the game world.

#### Combat

Combat mods have also benefited greatly from tools like Nemesis, DAR, and SKSE. Some of these mods (e.g. SkySA) also involve animation, but I listed them here because I consider them to be "primarily" combat mods.

All in all, these mods make the combat in Skyrim feel more like The Witcher 3 or Dark Souls. These games have a much better third-person combat experience (IMO) because they give you more tools (e.g. dodging and parrying) and require you to play smarter in order to win. I used to only play in first-person, but now I switch to third-person during melee combat for the best gameplay experience.

Anyway, here are some highlights. SkySA introduces "attack commitment", which causes you to step into every attack you make. TK Dodge allows you to... dodge. True Directional Movement introduces 360 degree movement, enemy tracking, and some other nice gameplay features. Ultimate Combat makes enemies more aggressive and strategic in combat. ZUPA introduces a potion drinking animation, so that you can't spam healing potions during combat.

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

#### Mechanics

This category is kind of a catch-all for other gameplay mods. Like combat, "gameplay" encompasses lots of different things.

Andromeda, Odin, and Vokrii are part of the "Enairim" collection of gameplay mods by the modder Enai. I haven't gone very far down the Enairim rabbit hole, but I've enjoyed these three mods so far. Maybe one day I'll try some of his more heavyweight mods like Apocalypse and Ordinator.

ALl of the other mods are also worth highlighting. Simply Knock allows you to enter a locked building by asking the owner to let you in. Sojourn Over Signposts makes fast travel allowed only by interacting with a signpost, forcing you to move through the world instead of the map menu. Take a Peek allows you to peek through the keyhole of a door and see what's on the other side. Wet and Cold makes NPCs wear cloaks and hoods when it rains or snows, and also makes them run inside during storms. All of these mods are among my favorites for their simplicity and the unique value they each add to the game.

- Andromeda - Unique Standing Stones of Skyrim
- Odin - Skyrim Magic Overhaul
- Simply Knock
- Sojourn Over Signposts - Witcher-Style Fast Travel Alternative
- Take a Peek - New Stealth Mechanic
- Vokrii - Minimalistic Perks of Skyrim
- Wet and Cold

### Audio

Audio mods typically replace existing sounds or add new sounds, where "sounds" could be sound effects, dialogue, or music. Despite my background as a musician, I am not really an "audiophile" -- I don't keep all my music in a lossless format or listen to everything with ultra-high quality headphones. So I probably don't fully appreciate the quality improvement mods like Ludicity, HQ Music, and HQ Voices. However, I do appreciate the new sound effects added by Sounds of Skyrim (one of the first mods I ever used), and I can certainly appreciate the new bard music provided by Badass Bard Songs.

- BA Bard Songs
- Bandit Lines Expansion
- Lucidity Sound FX
- Reverb and Ambiance Overhaul
- Sounds of Skyrim Complete
- SSE High Quality Music
- SSE High Quality Voices

Other notable mods include Immersive Sounds and the Unofficial HD Audio Project. They look like excellent mods, I just don't use them because they are incompatible with my current setup.

### Visuals

Visual mods are another category that took me a while to research, and one that I will continue to experiment with as I understand it better. Like gameplay and combat, there are multiple aspects to lighting, so you really have a lighting "stack", combining several (mostly) independent mods to improve each aspect. Also, each aspect is optional, so take what you want and leave the rest.

First, pick your ENB preset. [ENB](http://enbdev.com/) itself is a library that adds a bunch of fancy effects to the game engine's graphics pipeline, like Depth of Field and Sun Rays. To enable these effects, you have to configure ENB, but most people just use a preset created by someone else who knows what they're doing. Here are some notable presets:

- Bjorn ENB-Reshade
- Rudy ENB
- Silent Horizons ENB
- SkyrimSE Re-Engaged ENB

Next, pick your ReShade preset. [ReShade](https://reshade.me/) is another library that adds graphics effects to video games, similar to ENB. I'm not really sure how these libraries are different, but there appears to be some consensus around using ENB and ReShade together. Some notable options:

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

### Models and Textures

Models (aka meshes) and textures are the 3D and 2D assets that comprise everything you see in the game world, from the landscape and the sky to buildings and items and people. Basically every Elder Scrolls game ships with mediocre assets, probably so that they can push the limits on other fronts like world size and AI complexity. Inevitably, modders bring higher resolutions and polygon counts to each game, but some modders also take the opportunity to create their own look and feel, especially with textures. You can make Skyrim look like a [very different game](https://www.nexusmods.com/skyrim/mods/33017) with only a texture pack.

Model and texture mods can be divided into "base" mods that cover everything and "additional" mods that cover only a subset of objects. The small mods tend to be more focused and detailed, and more subject to individual preferences. A good practice is to apply your "base" mods first, then apply any smaller mods to suit your taste.

For models, start with Static Mesh Improvement Mod (SMIM) and High Poly Project (HPP). These mods simply improve all 3D models throughout the game. For textures, there are a number of "all-in-one" texture packs to choose from:

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

All of these mods are highly regarded, and you'll probably find them on most mod lists. Beyond that, there is a vast sea of mods for weapons, armor, flora, clutter, furniture, creatures, and so on, and you really have to figure out for yourself which ones you like. A good strategy is to find modders that you like and keep up with their mod releases, which should make it easier to create a consistent look and feel for your game. Some well-known modders include [DrJacopo](https://www.nexusmods.com/skyrimspecialedition/users/50222836), [ElSopa](https://www.nexusmods.com/skyrimspecialedition/users/6960827), [mathy79](https://www.nexusmods.com/skyrimspecialedition/users/12770808), and [rudy102](https://www.nexusmods.com/skyrimspecialedition/users/93362). I'm content at the moment with the base texture overhauls, so I don't use anything else, but if I ever go further down the rabbit hole, I'll probably start with these modders.

### Environment

Environmental mods mainly add content to the natural world, such as trees, grass, and water. Here are the mods I currently use:

- Folkvangr
- Happy Little Trees
- Morning Fogs
- Origins of the Forest
- Origins of the Forest Reduced
- Volumetric Mists
- Water for ENB

Another popular water mod is Realistic Water Two. I honestly couldn't tell you which one I like more, they both look really good to me, but you should use one or the other.

### Locations

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

In my next iteration, I will try to use JK's Skyrim, all of JK's interior mods, and Dawn of Skyrim. I will probably have to drop the individual city overhauls as well as Palaces and Castles Enhanced in order to make it work. Sooner or later, a man must decide how many patches he is willing to tolerate...

I didn't include new lands mods here because I decided to group them with quest mods instead. There are also tons of mods that add new dungeons and player homes, I'm just not as interested in such mods unless there's a good quest involved.

### Items

Item mods add new weapons, armors, clothing, or other items to the game. I don't use any at the moment, as I'm generally content with the items in my current setup, but I'll list a few that I'm considering:

- Armors of the Velothi
- Immersive Armors
- Immersive Weapons

### NPCs

NPC mods include body / face / hair replacers, companions, and population mods.

#### Body, Face, and Hair

I don't care that much about body mods because everyone is almost always clothed... at least in *my* playthroughs. If you want a body mod, CBBE is a good place to start, at least for female bodies. As for face and hair replacers, here are a few good options:

- Bijin Warmaidens
- Cathedral Player and NPC Overhaul
- Diversity - A Character Overhaul
- High Poly NPC Overhaul
- Legacy of the Dragonborn Visual Overhaul
- Modpocalypse NPCs
- Pandorable's NPCs
- RS Children Overhaul
- TK Children

I use Diversity and RS Children (as well as Realistic RS Children), which provides a vanilla-friendly uplift to every NPC in the game. Cathedral also looks really good to me. A lot of face and hair mods make everything too smooth for my taste, or they only update a few characters, leaving everyone else to wallow in their relative ugliness. But to each their own.

Another popular mod I haven't tried yet is [HDT-SMP](https://www.nexusmods.com/skyrimspecialedition/mods/57339), an SKSE plugin that adds support for body, hair, and clothing physics. I know you can use [Artesian Cloaks of Skyrim](https://www.nexusmods.com/skyrimspecialedition/mods/17416) to add physics to the cloaks from Wet and Cold, but I haven't found anything for the hair from Diversity.

#### Companions

Companion mods are some of my favorite mods, right alongside quest mods. If you were to take only one thing from this guide, I would say, add a good companion mod (or three) to your next playthrough. Some of these companions will really enrich your time in the game world, and sometimes they'll surprise you with the things they say (and do!). As much as I love playing Skyrim with modern graphics and combat, the things that really keep me in the game are good stories and *good characters*.

Here are the companions I've enjoyed so far:

- Hoth
- INIGO
- Lucien
- Serana Dialogue Add-On
- Shirley
- Skeever
- Sofia
- Song of the Green (Auri Follower)
- Vilja in Skyrim

And some other mods that I want to try:

- Ambriel - The Lost Princess
- Arissa - The Wandering Rogue
- Aurlyn Dawnstone - The Reclusive Philosopher
- Kaidan 2
- Mirai - the Girl with the Dragon Heart
- Nebarra
- Recorder

The biggest question I had with companion mods was how to have more than one follower at a time. As it turns out, most of these companion mods implement their own "follower quest", which means that they aren't beholden to the normal one-follower limit. So you could have most of these companions following you at the same time and still have one vanilla follower.

That being said, I still ended up using Nether's Follower Framework to remove this limit and take advantage of some other nice features. There are several such frameworks, and I'm sure they all work just as well, but I'm happy with NFF and don't have any reason to switch. One of my favorite features in NFF is that your followers will "sandbox" (e.g. sit down, order food and drink, use crafting stations) whenever you remain in one area, which is much more immersive than *standing right behind you* at all times.

#### Population

I use several "population" mods to make the general population more interesting, either by improving the AI of existing NPCs or adding new NPCs:

- Citizens of Tamriel
- Immersive Citizens - AI Overhaul
- Immersive Patrols
- Immersive World Encounters
- Interesting NPCs (3DNPC)
- Populated Dungeons Caves Ruins
- Populated Forts Towers Places

CoT and 3DNPC collectively add hundreds of unique NPCs to the game, with tons of dialogue and quests. Based on what I've seen so far in my current playthrough, many of these NPCs rival or exceed their vanilla counterparts with their personalities and backstories. ICAIO overhauls the behavior and schedules of many vanilla NPCs to be more realistic (Sinmir actually leaves the Bannered Mare from time to time).

I initially used the entire Populated series of mods because I wanted to have *tons* of generic NPCs like the Witcher 3. These mods add generic NPCs to cities and towns and roads, hostile NPCs and creatures to dungeons, and huge civil war battles across the map. After playing for a while, I realized that the unique NPCs from CoT and 3DNPC, although fewer in number, added so much more to my gameplay experience than the generic NPCs, and in fact were plentiful enough to make the world feel more "populated". In the end, I only kept the dungeon-related mods, since they provide a necessary difficulty bump to compensate for all of my new companions.

### Quests

Under "quest" mods I lump together mods that add quests to Skyrim, mods that add new locations, and total conversion mods.

I think quest mods get the most hype because they promise "X hours of new gameplay", and it's easy to assume that bigger mods are always better. After playing through many such mods across multiple Elder Scrolls games, I've learned that not every quest mod is *really* worth playing. A mod can add entirely new lands filled with NPCs and quests, but if the stories and dialogue aren't very memorable, or even if it just feels like more of the same Skyrim content, I end up feeling like it wasn't worthwhile.

I feel harsh saying these things, because I know how much time and effort goes into quest mods, and for little to no compensation. But the reality is that there are *so many* mods out there, more than I will ever have time to play, so I want to find the very best of them. Not just the *most popular* mods, but the *best* mods. I want to experience something that I wouldn't find in the original game. This is why smaller but unique mods, like The Bottomless Pit and The Forgotten City, can be way more enjoyable (to me) than larger but relatively mundane mods like Falskaar and Wyrmstooth.

Here are the mods that I really enjoyed:

- Clockwork
- Enderal
- Faction - Pit Fighter
- Helgen Reborn
- Legacy of the Dragonborn
- Project AHO
- The Bottomless Pit
- The Forgotten City
- The Gray Cowl of Nocturnal
- There Is No Umbra
- Trainwiz' The Wheels of Lull

Here are the mods that I thought were just okay:

- Carved Brink
- Falskaar
- Here There Be Monsters
- Moon and Star
- Moonpath to Elsweyr
- Wyrmstooth

The mods I'm currently playing through:

- Leaps of Faith - A Misc Quest
- Quest Expansions by jayserpa

The mods I want to play (mods marked WIP haven't been released at the time of writing):

- Apotheosis (WIP)
- Beyond Reach
- Beyond Skyrim - Bruma
- GLENMORIL
- Konahrik's Accoutrements
- Odyssey of the Dragonborn (WIP)
- Rigmor of Bruma
- Rigmor of Cyrodiil
- Shezarrine - The Fate of Tamriel - Prologue
- Sirenroot
- Skyblivion (WIP)
- Skyrim: Extended Cut (WIP)
- Skywind (WIP)
- Undeath Remastered
- UNSLAAD
- VIGILANT

Looks like I have enough adventures in my backlog to keep me busy for a while!

If you find this list overwhelming and don't know where to start (or whether you even want to try), then just play Enderal. Bigger isn't always better, but Enderal might just be the biggest and the best mod on this list. It's not just a "quest" mod, it's an entirely different game. I've played through it twice, and I'll probably play it again one day with all of these fancy new combat mods. Seriously, just play it.

I'll end with a few mods that provide some quality-of-life improvements rather than big quests. Alternate Start (and the New Beginnings extension) allows you to start the game any number of ways instead of Helgen (you can still start the main quest by traveling to Helgen and inspecting the aftermath). At Your Own Pace tweaks the main quest and faction quests to feel less urgent and not make you the center of attention so much.

- Alternate Start - Live Another Life
- At Your Own Pace
- New Beginnings - Live Another Life Extension

### Patches

Here is the list of patches I currently use. Consider this list an illustrative example -- you should do your own research to figure out the correct patches for your mod list. See the following section on [detecting mod conflicts](#detecting-mod-conflicts).

- Better Third Person Selection - Nordic UI Activation Button Replacer
- QuickLoot EE - NORDIC UI
- Odin - Vokrii Compatibility Patch
- Reverb and Ambiance Overhaul - Alternate Start Patch
- Reverb and Ambiance Overhaul - ELFX Patch
- Window Shadows - ELFX Patch
- Capital Windhelm Expansion - City Entrances Overhaul Patch
- GQ959 - Capital Windhelm Expansion Patch
- Capital Windhelm Expansion Patches
- COTN Dawnstar Patch Collection
- COTN Falkreath Patch Collection
- COTN Morthal Patch Collection
- COTN Winterhold Patch Collection
- COTN Addon - Anga's Mill Patch Collection
- COTN Addon - Half-Moon Mill Patch Collection
- ES ICAIO Patch
- ES RS Children Patch
- ES Terrain Patch
- ES USSEP Patch
- ESD SMIM Patch
- ESD Terrain Patch
- ES ESD Patch
- Palaces and Castles Enhanced Patch Collection
- Quaint Raven Rock Patch Collection
- Quaint Raven Rock - Ghosts of the Tribunal Patch
- The Great Settlement of Darkwater Crossing Patch Collection
- The Great Town of Ivarstead Patch Collection
- The Great Town of Karthwasten Patch Collection
- The Great Town of Shor's Stone Patch Collection
- The Great Village of Kynesgrove Patch Collection
- The Great Village of Mixwater Mill Patch Collection
- The Great Village of Mixwater Mill Interesting NPCs Patch
- The Great Village of Old Hroldan Patch Collection
- Interesting NPCs SE - Cutting Room Floor SSE Patch
- RS Children Patch Compendium
- College of Winterhold - At Your Own Pace
- College of Winterhold - RS Children Overhaul
- Legacy of the Dragonborn Patches
- Legacy of the Dragonborn - Interesting NPCs Patch

Also, here are the patches you would need to use JK's Skyrim and JK's Interiors with everything else:

- JK's Skyrim - Dawn of Skyrim - Patch
- The Great Cities of JK's North - Patch
- JK's Interiors Patch Collection

### What About Creation Club?

The Anniversary Edition of Skyrim comes with all of the Creation Club content, which was partly what motivated me to give Skyrim another go. The CC content is considered canon, and I like to keep up with Elder Scrolls lore, so I decided to buy the AE upgrade and try out the CC addons for myself. So, since we're already going through my mod setup, I'll give you my two cents on Creation Club.

Ultimately, I think most of the CC content is just fine. They are all high-quality mods by skilled modders, but most of them just didn't add much value for me, especially among all the other mods I already have. In future playthoughs, I will probably only keep a few of the Creation Club mods:

- Adventurer's Backpack
- Alternative Armors (all 15 of them)
- Arcane Accessories
- Arcane Archer Pack
- Bittercup
- Camping
- Expanded Crossbow Pack
- Fishing
- Necromantic Grimoire
- Netch Leather Armor
- Nix-Hound
- Rare Curios
- Ruin's Edge
- Shadowrend
- Survival Mode

The Alternative Armors collection was probably my favorite, because all of the armor sets are connected by a commen story, the rise and fall of the Crimson Dirks. It was great fun to find each armor set and learn about the Crimson Dirk who wore it. And while I dropped most of the other weapon and armor mods, I kept Shadowrend in particular because of the... unique combat challenge that it provides.

Many of the other CC mods were dropped because they add artifacts that are already covered by other mods such as Legacy of the Dragonborn, The Gray Cowl of Nocturnal, and There is No Umbra. Additionally, the team behind Skyrim: Extended Cut released an [extended cut of Saints and Seducers](https://www.nexusmods.com/skyrimspecialedition/mods/72772). So far, I have enjoyed these mods more than their CC counterparts.

Here are the CC mods whose artifacts are also added by Legacy of the Dragonborn:

- Bow of Shadows
- Chrysamere
- Dawnfang & Duskfang
- Dead Man's Dread
- Divine Crusader
- Gallows Hall
- Ghosts of the Tribunal
- Goldbrand
- Lord's Mail
- Staff of Hasedoki
- Stendarr's Hammer
- Sunder & Wraithguard
- The Contest

I was actually disappointed by Ghosts of the Tribunal and The Cause, however, because they were hyped as "DLC-sized quest mods", and they really didn't live up to the hype. They were larger than the other CC mods, but the quests just weren't very interesting. I think it's because all of the CC mods reuse vanilla dialogue, so the NPCs say a few brief lines and give you notes for everything else. I enjoyed the nostalgia, like finding potions and gear from Morrowind, but that's all it was -- nostalgia -- and I don't think it worked with the lore.

But, I will say again, all of the CC mods are good mods, and any one of them could make a fine addition to the right playthrough. Depending on your mod setup or character build, you might choose differently from me. Lots of people like to dunk on the Creation Club because they don't like the concept of it, which I understand, but I don't feel strongly about it either way. I'm just very minimalist with mods, especially small mods, so most of the CC content just doesn't make the cut.

(And yes, for the amount of coverage I'm getting, the ~150 mods that I use are pretty minimal!)

### What About Anniversary Edition?

Since we're talking about Skyrim AE, I suppose I should say a few words about whether AE is worth it.

Well, the AE upgrade consists of (1) all of the Creation Club mods and (2) an update to the game engine. The engine update is not significant, and it isn't required to use the CC mods. So, it basically depends on how many CC mods you want. I wanted to try them all, so I was going to buy the AE upgrade either way. Knowing what I know now, the calculation isn't so clear.

Another issue with AE is that the updated game engine broke compatibility with many SKSE plugins. You can read the full story elsewhere, but the bottom line is that many mods now have separate versions for SE and AE, and some mods simply don't work with AE because they haven't been updated. You can check [this page](https://modding.wiki/en/skyrim/users/skse-plugins) to see which SKSE plugins have been updated for AE.

If you have Skyrim AE, you essentially have two options. You can either stick with AE (1.6.x) and use only the mods that have been updated for it, or you can [downgrade your game engine](https://www.nexusmods.com/skyrimspecialedition/mods/57618) to SE (1.5.97) and use whatever mods you want. What's nice about downgrading is that you can keep all of the CC content, allowing you to have the "best of both worlds".

Downgrading and keeping the CC content is exactly what I did. When the AE upgrade was initially released, either option might have been reasonable. Now that there have been several AE updates, each one breaking compatibility with the Address Library for SKSE, I think the clear path forward is to simply disable Steam updates and downgrade to SE (1.5.97) for good. I don't expect modders to keep updating their mods for what appear to be inconsequential game engine updates.

## Detecting Mod Conflicts

Mod conflicts happen when two mods edit the same content. For example, if one mod edits the name of a potion while another mod edits the effects of that potion, the two mods will conflict. In this case, whichever mod is loaded later will overwrite the other mod. A more common example is when two mods edit the same world space, such as a mod that overhauls city and a mod that makes a few changes to that city for a new quest.

Once you go beyond a few mods, you will inevitably have conflicts, so it will be important for you to know how to detect them and resolve them. Now, I come from the world of software engineering, where we already have good tools and processes for resolving conflicts that occur when multiple engineers work on the same codebase. With mods, resolving conflicts is more of an art. I will walk you through some of the strategies that you can use.

1. **Read the mod description for compatibility notes.** This one is the RTFM for modding. If you download a mod from Nexus, for example, always read the **Description** page in its entirety. The mod author will usually include a section on mod compatibility, especially if their mod is popular, and they will say whether a mod is compatible, and if not, if there is a patch.

   Note, however, that the mod author can't test their mod with every other mod in existence. They will usually test the most commonly-used mods that are likely to conflict with theirs, and they might give some rules-of-thumb like "any mod that doesn't edit X location should be compatible". So if they don't mention a particular mod, you'll have to use your best judgement.

2. **Check for compatibility patches.** Beyond the mod description, there are a few easy ways to check for patches.

   - In Nexus, there is a **Requirements** dropdown with a section called **Mods requiring this file**. You can quickly scan this section to see if there are any patches for other mods that you use. You can also check the **Files** section for patches from the mod author, although they usually mention these patches in the mod description.

   - You can use LOOT to search for mod conflicts and patches. While LOOT is primarily used to sort mods, it also has a community-maintained registry of known mod conflicts and patches, and it will flag these for you. I don't even use LOOT for sorting (more on that later). LOOT's registry contains much of the information you would have found on Nexus, so it's a good way to catch anything you missed. That being said, don't let it become a crutch -- you should still always read the mod descriptions.

3. **Understand how different kinds of mods interact.** Ultimately, you'll want to gain an intuition for the different mod "categories" and which kinds of mods are likely to conflict with each other. This intuition can't be taught, but you will learn over time as you research mods. See my earlier section on [mod categories](#selecting-mods). For what it's worth, most of the patches in my mod list are between lighting mods, city overhauls, and quest mods.

## Debugging Crashes

Skyrim can crash for a lot of different reasons, so the solution will depend on the nature of the crash. The [/r/SkyrimMods](https://www.reddit.com/r/skyrimmods/wiki/troubleshooting_guide/) troubleshooting guide is the most comprehensive guide that I have found. In fact, I learned much of what I know through the guides on that subreddit, so I only hope to provide a gentler overview here.

First things first, you should take steps to prevent crashes in the first place:

- When you install a mod, make sure to install all of its dependencies. On Nexus, you can find a mod's dependencies under the **Requirements** dropdown, and Nexus will usually alert you about them anyway when you download a mod.

- Make sure your mod plugins are ordered sensibly: ESMs should be first, plugins should not be missing any required plugins, and plugins should come after their required plugins. In MO2, you can check all of these things under the **Plugins** tab. Plugins will show an alert icon if they are missing any dependencies.

- In general, just follow the mod author's instructions for every mod you download, no matter how tedious it feels. Do it *when you install the mod* -- if you push it off, you are much more likely to forget something. I cannot stress this point enough! It is much harder to debug a crash caused by a misconfigured mod, than it is to install the mod correctly the first time.

Hopefully these measures will save you from 90% of crashes. But, if you are using hundreds of mods, your game will still probably crash from time to time. Even with the best mod hygiene, you still need to know how to debug. So, here are some options:

- You can use the [.NET Script Framework](https://www.nexusmods.com/skyrimspecialedition/mods/21294) to generate an error log whenever your game crashes. It's like a plugin, but for the *game engine* rather than the game world. When your game crashes, you'll find a new error log with a bunch of diagnostic information. The error log can help you find the root cause by identifying plugins that may have contributed to the crash.

- In some cases, you might be able to use context clues to figure out the root cause. Does the game always crash in a particular area? Or at a particular stage in a quest? Or when a particular event happens? If you suspect a particular mod, disable the mod and try to reproduce the crash.

- If all else fails, your final option is to disable and re-enable mods one at a time until you reproduce the crash. It is the "brute force" approach, and it's last because it's the most time-consuming. To save some time, disable half of your mods at a time until the crash doesn't happen. Then, re-enable each mod from the last "half", one at a time, until the crash happens again. This approach should allow you to isolate the cause of just about any other crash.

I learned some of these lessons the hard way. While I did try to install everything correctly, I forgot to scrutinize my plugin order because I thought Mod Organizer was syncing it with my mod order, when in fact these two things are independent. My game still worked for a while, but as I explored more of the world, I began to experience more crashes and other weirdness. I fixed most of these issues by correcting my load order and adding a few patches I had been missing (they were flagged by LOOT). The .NET Script Framework helped me identify a few mods that were consistently causing crashes, and I usually ended up removing these mods.

## Additional Resources

The guides I used:

- [r/skyrimmods Guides](https://www.reddit.com/r/skyrimmods/wiki/index/#wiki_guides)
- [Mern’s Mod Guides](https://www.skyrim-guild.com/guides-collection)

The creators I follow:

- [Camelworks](https://www.youtube.com/@Camelworks)
- [FudgeMuppet](https://www.youtube.com/@FudgeMuppet)
- [Heavy Burns](https://www.youtube.com/@HeavyBurns)
- [Mern](https://www.youtube.com/@Mern)
