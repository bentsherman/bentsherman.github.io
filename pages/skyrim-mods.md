# Skyrim Modding Research

I've been a fan of The Elder Scrolls since I was in elementary school. To the extent that I am a gamer, it's mostly because I have sunk thousands of hours into these games. That's why I continue to play these games 10, 15, 20 years after they are released, and I'll probably keep playing them for the rest of my life.

That being said, I have never gone deep with my own mod setup for Skyrim. I installed a few mods from the Steam workshop a few years ago, mostly for a gag playthrough where dragons were trains, mudcrabs had top hats, and my primary weapons were a lightsaber and a Dwemer longrifle. And every time an NPC said something about arrows to the knee, or sweetrolls, or the Cloud District... they received "divine punishment". And a few quest mods, but they mostly turned out to be just okay. Now that I was finally settled in my new home, I decided I was ready to pursue a new mod setup in earnest.

And I must say, Skyrim modding has come an incredibly long way. It has reached heights I did not expect. I was overwhelmed by the vast sea of _really good mods_ out there. Fortunately, I just completed a dissertation, so I was experienced in carrying out long bouts of research. I endeavoured to find the best mods in every category and build my own ultimate modded Skyrim.

Consider this page a "living research report", in which I maintain my knowledge of mods across the various aspects of Skyrim, as well as some notes about modding Skyrim in general, like how to detect potential mod conflicts, how to find patches, how to deal with crashes, etc.

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

TODO

## Debugging Crashes

TODO

## Selecting Mods

In this section, I will try to demonstrate how to pick mods by walking you through my mod setup.

Researching and selecting mods is by far the most time-consuming aspect of modding for me. In case you haven't noticed, there are a lot of mods. _Way too many_ mods to try them all in one go.

More importantly, game saves are fragile. Most mods can't be cleanly removed after they are added, and some mods can't even be cleanly added mid-game. Yes, you can use the [Script Cleaner](https://www.nexusmods.com/skyrimspecialedition/mods/34601) to "clean" a save after removing mods, but in reality, the idea of "cleaning" a save is a delusion, and the only way to cleanly remove a mod is to revert to a save from before before the mod was added. In some cases you might get lucky -- mods that don't add scripts can usually be removed without much issue. But must mods of any interest use scripts, so don't count on it.

The point is, if you care about a save game, you should care about the mods you add to it. Ideally, you should test new mods one at a time and always save before you add a mod. Of course, it's not always so easy in practice. Some mods have wide-ranging effects on the game, you may have to play it for a while before you know whether or not you like it, and you probably won't want to test one mod at a time when you have a bunch of mods that you want to play together. I dealt with all of these problems because I had several years of new mods to evaluate all at once.

### Mod Categories

Navigating the great sea of mods is much easier once you have an idea of the main categories and the choices that you have within each category. Here I will walk you through the main categories that I use to organize my mods. At this point I've mostly converged with the Nexus categories, but I only get as detailed as I need for it to be helpful.

#### Bug Fixes

TODO

#### Audio

TODO

#### Utilities

TODO (?)

#### User Interface

TODO

#### Gameplay: Animation

TODO

#### Gameplay: Combat

TODO

#### Gameplay: Mechanics

TODO

#### Visuals and Lighting

TODO

#### Models and Textures

TODO

#### Environment

TODO

#### NPCs: Body, Face, and Hair

TODO

#### NPCs: Companions

TODO

#### NPCs: Population

TODO

#### Locations

TODO

#### Quests: Existing Locations

TODO

#### Quests: New Locations

TODO

#### Patches

TODO (?)

### What About Creation Club?

The Anniversary Edition of Skyrim (released on the 10-th year anniversary, 11/11/2021) comes with all of the Creation Club content, which was partly what motivated me to give Skyrim another go. The CC content is considered canon, and I like to keep up with TES lore, so I decided to buy the AE upgrade and try out the CC addons for myself. So, since we're already going through my mod setup, I'll give you my two cents on Creation Club.

Ultimately, I think most of the CC content is just fine. They are all high-quality mods by skilled modders, but I found that most of them didn't add much value for me, especially among all the other mods I already had. If I ever play through Skyrim again (e.g. to play a big overhaul mod like Skyrim: Extended Cut), I will probably only keep a few of the Creation Club mods.

I'll sum it up by listing which mods I would keep/drop. Your mileage may vary -- depending on your mod setup or save game, you might choose differently from me.

#### Keep

The Alternative Armors collection was probably my favorite CC content, because of the story that connects all of the armor sets, the rise and fall of the Crimson Dirks. It was great fun to find each armor set and learn about the Crimson Dirk who wore it. And while I dropped most of the other weapon and armor mods, I kept Shadowrend in particular because of the... unique combat situation that it puts you through.

- Adventurer's Backpack
- Alternative Armors (all 15 of them)
- Bittercup
- Camping
- Fishing
- Shadowrend
- Survival Mode

#### Drop

Like I said before, all of these mods are good mods, and any of them would make a fine addition to the right playthrough. Many of the CC mods add artifacts from previous games, artifacts that have already been added by other mods such as [Legacy of the Dragonborn](https://www.nexusmods.com/skyrimspecialedition/mods/11802) (LotD). I have marked these mods as such. In general, I prefer LotD and other mods over the CC versions for how they introduce these artifacts into the game.

- Arcane Archer Pack
- Arms of Chaos
- Bloodchill Manor
- Bone Wolf
- Bow of Shadows (use LotD instead)
- Chrysamere (use LotD instead)
- Civil War Champions
- Dawnfang & Duskfang (use LotD instead)
- Dead Man's Dread (use LotD instead)
- Divine Crusader (use LotD instead)
- Elite Crossbows
- Expanded Crossbow Pack
- Farming
- Fearsome Fists
- Gallows Hall
- Goblins
- Goldbrand (use LotD instead)
- Headman's Cleaver
- Hendraheim
- Horse Armor (lol)
- Lord's Mail (use LotD instead)
- Myrwatch
- Nordic Jewelry
- Pets of Skyrim
- Plague of the Dead
- Redguard Elite Armaments
- Saints & Seducers (use the [Extended Cut](https://www.nexusmods.com/skyrimspecialedition/mods/72772) instead)
- Shadowfoot Sanctum
- Spell Knight Armor
- Staff of Hasedoki (use LotD instead)
- Staves
- Stendarr's Hammer (use LotD instead)
- Sunder & Wraithguard (use LotD instead)
- The Cause
- The Contest (use LotD instead)
- The Gray Cowl Returns! (use [The Gray Cowl of Nocturnal](https://www.nexusmods.com/skyrimspecialedition/mods/4509) instead)
- Tundra Homestead
- Umbra (use [There Is No Umbra](https://www.nexusmods.com/skyrimspecialedition/mods/47302) instead)
- Vigil Enforcer Armor Set
- Wild Horses

#### TBD

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

