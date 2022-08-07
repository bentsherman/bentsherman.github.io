# Skyrim Modding Research

I have been a fan of The Elder Scrolls since I was in elementary school. To the extent that I am a gamer, it's mostly because I have sunk thousands of hours into these games. That is why I continue to play these games 10, 15, 20 years after they are released, and I'll probably keep playing them for the rest of my life.

That being said, I have never gone deep with my own mod setup for Skyrim. I installed a few mods from the Steam workshop a few years ago, mostly for a gag playthrough where dragons where trains, mudcrabs had top hats, and my primary weapons were a lightsaber and a Dwemer longrifle. And every time an NPC said something about arrows to the knee, or sweetrolls, or the Cloud District... they received "divine punishment". And a few quest mods, but they mostly turned out to be just okay. Now that I was finally settled in my new home, I decided I was ready to pursue a new mod setup in earnest.

And I must say, Skyrim modding has come an incredibly long way. It has reached heights I did not expect. I was overwhelmed by the vast sea of _really good mods_ out there. Fortunately, I just completed a dissertation, so I was experienced in carrying out long bouts of research. I endeavoured to find the best mods in every category and build my own ultimate modded Skyrim.

Consider this page a "living research report", in which I maintain my knowledge of mods across the various aspects of Skyrim, as well as some notes about modding Skyrim in general, like how to detect potential mod conflicts, how to find patches, how to deal with crashes, etc.

## Tooling

It's not just the mods themselves that are better, it's the tools as well. Here's a list of which tools to use for which purpose, to the best of my understanding:

- Use Mod Organizer 2 to install and manage mods
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
