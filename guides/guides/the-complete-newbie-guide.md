# The Complete Newbie Guide

## Overview

This page is for people who want to get started with modding GTFO but don't know anything about it.\
If you're a programmer and you want to write actual mods, check out the introduction to [plugins](broken-reference/).

Always remember that the official discord server is not the place to discuss anything modding related. Talk about it in the [modding discord](https://discord.gg/rRMPtv4FAh) instead.

## Prerequisites/Recommendations

Datablocks are all stored in JSON, you need to get familiar with this text format. Basically it's a way to have data as text stored in a way that can be read by both humans and computers. There's an infinite number of guides and ways to learn JSON, but you can start with [w3schools](https://www.w3schools.com/js/js\_json\_intro.asp).

The text files can be edited even with notepad, but for your sanity I recommend using something more advanced. The most common option here is [vscode](https://code.visualstudio.com). It allows you to easily manage entire folders of files at once, provides syntax checking, highlighting, easy searching, replacing, and lots of other good stuff.\
You can also add some vscode extensions for yourself such as [indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow) to further make your life easier. Either way you'll be looking at massive amounts of JSON so best be prepared.

Knowledge of C# or programming in general can definitely help but is not required for modding using datablocks.

RegEx is very helpful for quickly finding and replacing data.

## Introduction

Datablocks (also referred to as blocks or db) are GTFO's way of storing various information about the game. While I'm positive they don't directly edit the files ever, them choosing JSON is a convenient way for modders to read and change that information.\
What is stored in datablocks is completely in devs' control. Sometimes it may seem arbitrary what is stored there and what isn't, so some modders make plugins that allow even more control over the game.

Some examples of what we can find in datablocks:

* The stats of weapons, enemies, and players (HP, speed, damage etc);
* Terminal logs and passwords;
* Enemy population in levels;
* The objectives of levels;
* Level layouts themselves;
* Entire rundowns.

Everything that is stored in datablocks can be edited.\
As previously stated, the developers control what is stored in datablocks, making them limited in some aspects. Some things have set rules that you cannot see in datablocks. Some things may be very hard to get to work as expected. Some things cannot be done using only datablocks. Learning to use them can take a lot of effort, and you will have questions, so don't hesitate to ask in the [datablock development channel](https://discord.com/channels/782438773690597389/782448951839555594).

## Installation/Setup

For a quick, hassle-free setup it's recommended that you use [R2Modman](https://gtfo.thunderstore.io/package/ebkr/r2modman/), a mod manager built to work with the Thunderstore.

### Installation with R2Modman

1. Install the latest version of [R2Modman](https://gtfo.thunderstore.io/package/ebkr/r2modman/)
2. Launch the mod manager and select GTFO
3. Create a new profile and name it
4. Select "Online" and install any mods you would like to play
5. Open `Settings -> Locations -> Change GTFO directory`. Locate and select the install location of GTFO. By default this is `C:\Program Files (x86)\Steam\steamapps\common\GTFO`
6. Hit the "Play Modded" button.
7. You're done!

Best practice is to create one profile per Rundown, as this SIGNIFICANTLY lowers the chances of the game breaking.

You can find the profile folder by going `Settings -> All -> Browse Profile Folder`

### Manual Installation

1. Make sure you have the latest version of GTFO installed. You can verify your game files through Steam just to be sure.
2. Download [Bepinex](https://gtfo.thunderstore.io/package/BepInEx/BepInExPack\_GTFO/) and [MTFO](https://gtfo.thunderstore.io/package/dakkhuza/MTFO/), then follow their installation instructions
3. Once everything is installed, run the game, the datablock files should generate in the following folder:\
   `GTFO\BepInEx\plugins\GameData_XXXXX`\
   `XXXXX` being the latest game version

You can always regenerate the JSON files by deleting the ones you want to refresh.

## Get started

To get some familiarity with editing datablocks, we're going to do 3 things in this section:

1. Change a weapon's stats;
2. Enable a weapon from a previous rundown;
3. Switch the stats of an enemy to those of another.

You can test either after every step or all at once.\
A few tips before we get started:

* [Datablock reference](../../reference/datablocks/) can be used to get a lot of information about blocks.
* `LocalizedText` is a special type that can both point to a text block and be read as a plain string.
* All enums can be passed as numbers or strings. I personally recommend using strings since they often give more information than plain numbers, but both work equally fine.

Remember, after initial generation, all datablocks should be located in GTFO\BepInEx\plugins\GameData\_XXXXX\\

### Changing a weapon's stats

Let's keep this one simple. We're going to find the pistol's stats and change its damage to 100 and firemode to automatic.\
Weapon stats are kept in Archetype datablock. There are multiple ways to determine which block belongs to the pistol, but for now let's "assume" that the correct block is the one with the name "GEAR\_Pistol\_Semi\_v2".

![Pistol archetype block](../../.gitbook/assets/newbie\_guide\_archetype.png)

* Note: lines under 3155 and 3184 are collapsed in vscode editor to reduce clutter. You'll see this used a lot.

Among the fields we can see the ones named "Damage" and "FireMode" (the latter is an enum and will appear as a number if you're not using enums as strings). Change the damage to `100` and firemode to `auto`. Additionally, let's change the public name to "Balanced pistol" so we can see the custom blocks were loaded without having to drop into a level.

![Edited pistol archetype block](../../.gitbook/assets/newbie\_guide\_archetype\_edited.png)

After saving, you can launch the game and test, or you can test after all the changes.

![Balanced pistol in weapon selection](../../.gitbook/assets/newbie\_guide\_balanced\_pistol.png)

### Enabling a weapon from a previous rundown

All datablocks share some fields. One of these fields is called "internalEnabled" and basically determines whether that block exists for the game or not. To enable a previous weapon, the only thing we need to do (assuming the old blocks have not been broken by game updates) is set this field to `true` in the correct places.\
For now we are going to enable the combat shotgun. Open PlayerOfflineGear datablock and find the block named "ShotgunAuto". Set "internalEnabled" to `true` on that block.

![Combat shotgun block](../../.gitbook/assets/newbie\_guide\_offline\_gear.png)

When you save this and launch the game, the combat shotgun should be available under special weapons.

### Switching the stats of an enemy with those of another

Aside from "internalEnabled" there are 2 other fields that are shared by all blocks. One of them is "name" which you don't see used in-game, but it does help identify the block you're looking at. The last shared field is "persistentID". This is the field used by blocks to reference other blocks.\
Note that "persistentID" and "name" cannot repeat in the same file.

Let's change a striker's stats to those of a big striker's using these references.\
The main block of an enemy is Enemy datablock and the stats we're looking for are stored in EnemyBalancing datablock. The reference field is named "BalancingDataId".

![Enemy to EnemyBalancing reference](../../.gitbook/assets/newbie\_guide\_balancing\_reference.png)

To change the stats we just need to find the big striker's balancing data, get its persistentID (in this case it's 16), and set it on the striker data.

![Edited striker data](../../.gitbook/assets/newbie\_guide\_balancing\_edited.png)

And that's it, **wave** strikers now have the balancing stats of a big striker. If you want, you can also change the balancing data of "Striker\_Hibernate" as well for easier testing and more suffering.

* If you want to undo all your changes, you can delete the edited files and let them regenerate.
* If you're wondering what fields do what, you can either interpret the name or check out the [datablock reference](../../reference/datablocks/).
* Most fields that hold references to other blocks are of the type "uint" aka "UInt32".

## Introduction to errors

If you edit datablocks enough, you're bound to run into errors, also called exceptions. There's an infinite number of causes so it's impossible to know all of them, but it's important to know where to start looking for information, at the very least so you can pass on more when looking for help. If you do run into something you can't fix yourself, you can ask in the [tech support channel](https://discord.com/channels/782438773690597389/782451402676109362) in the modding discord.

When launching the game with mods enabled, you'll see the BepInEx console as a separate window. This console is useful for many things, but most importantly for users, it shows errors in red text.\
All logged messages have the type and source as a prefix. E.g. `[Error: MTFO] error message` shows that there was an error caused by the mod MTFO. Most of the time errors are caused by the game itself, in which case you will see `[Error: Unity]` as the prefix. In this case I would always recommend to look for the error in the game logs instead of BepInEx logs. These are located in `%userprofile%\AppData\LocalLow\10 Chambers Collective\GTFO` If you closed the game already, their name will be of the following format: `GTFO.[Date].[Time]_[PlayerNick]_[NetworkStatus]`. If the game is still open, it'll instead be `GTFO.[Date].[Time]_NICKNAME_NETSTATUS`. For the most part you will be looking for the most recent file created.\
While in bepinex console the error message is one line, the game logs provide the stack trace, which is the full source of the error and often provides much more information than just the error message.

Let's take a look at an example.\
BepInEx console shows this error message:

```log
NullReferenceException: Object reference not set to an instance of an object.
```

While the game logs show this:

```log
18:17:44.732 - NullReferenceException: Object reference not set to an instance of an object.
Gear.MeleeWeaponFirstPerson.UpdateInput () (at <00000000000000000000000000000000>:0)
Gear.MeleeWeaponFirstPerson.UpdateLocal () (at <00000000000000000000000000000000>:0)
```

`NullReferenceException` is one of the most common errors that says next to nothing about the cause. All we know from BepInEx console is that an error happened. But the game logs show that the source is from melee weapons. Even if this error doesn't give enough information to you, it will allow other people to find the cause if you ask for help.

Also note that some errors can cause even more errors. When debugging, check the oldest errors first.

## Remarks

* `GameDataBlockBase, trying to save x without being setup` error is most likely caused by errors in your JSON. Check your syntax and if you pass incorrect types, such as string instead of int.
* You can use git to track changes. This allows you to easily see everything you changed at any time, which is useful for many purposes and especially debugging.
* If something doesn't work correctly, check if your mods are up to date. Rundown updates often break them.
* Game logs are useful for more than just finding exceptions, they provide information about what's going on in the game. You can make a desktop shortcut to the logs folder to access them faster.
* Game updates can break existing datablocks. Be careful when using old blocks as reference (and especially careful when enabling disabled blocks). Also remember that blocks you create now may be broken by the game later. This is most common with level layout.

## Recommended content (TODO)

link to datablock reference\
link to regex guide\
link to git guide\
link to another datablocks guide\
link to how to get rundown dev role\
link to how to get dev tools\
link to how to publish to thunderstore
