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
- Arcane Archer Pack
- Bittercup
- Camping
- Expanded Crossbow Pack
- Fishing
- Shadowrend
- Survival Mode

#### Drop

Like I said before, all of these mods are good mods, and any of them would make a fine addition to the right playthrough. Many of the CC mods add artifacts from previous games, artifacts that have already been added by other mods such as [Legacy of the Dragonborn](https://www.nexusmods.com/skyrimspecialedition/mods/11802) (LotD). I have marked these mods as such. In general, I prefer LotD and other mods over the CC versions for how they introduce these artifacts into the game.

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
