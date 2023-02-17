---
description: Changing fields that have no impact on the game
---

# Editing rundown and level metadata

### Overview

Not all fields have functional use in-game. Some are used just to display something, like level descriptions for example. Now that we have isolated one level in our rundown, let's change some fields to distinguish it from R6B2.

### Naming the blocks

First let's change the "name" fields of both rundown and level layout. As we know, this is one of the fields shared by all datablocks and must be unique in the file. It is never visible in-game without mods, but having good names helps with readability and lets us describe the block. This is especially relevant here since JSON has no comments (although there are ways).

The exact names are up to you. I can only try to give a few tips, whether to follow them is up to you:

* Keep a consistent style of naming.
* Describe what the block is concisely. A longer name is better than a shorter one that has no meaning.
* Don't use abbreviations you might not remember.
* Use practical names; no jokes.
* You can mark unfinished blocks by adding TODO (and even what exactly is unfinished) in the name if you need to remind yourself.
* If you're working on a block that has many entries and you're modifying only a few (e.g. archetype), you can think of a prefix to attach to all names so you know which ones you changed.

Here are the names I chose.

![R6 rundown and level blocks renamed](<../../.gitbook/assets/paveikslas (2).png>)



This is the only field we're changing that's usually invisible to the players.

### Changing data displayed to the player

Remember a lot of text fields are of the LocalizedText type, these can be both numbers and strings. If you want localization in your custom rundown you can use the LocalizedText type, in this guide we'll only use strings. You can always check the original text you're changing by looking for the ID in TextDataBlock.

Let's mark the fields we'll focus on:

* In rundown datablock:
  * "Title" - the displayed title of the rundown;
  * "SurfaceDescription" - displayed when clicking the "intel" button (nobody reads this though);
  * "Prefix" - Mission prefix, in base game always used to specify tier. In old times the devs asked us to distinguish from base game rundowns (e.g. "act-1") but nowadays it doesn't matter;
  * "PublicName" - the name of the mission;
  * "ExpeditionDepth" - Drop cage target depth in expedition details;
  * "ExpeditionDescription" - text displayed under "://Intel\_" in expedition details;
  * "RoleplayedWardenIntel" - text displayed under ":://Interrupted\_Communications\_" in expedition details and when dropping in.
* In level layout:
  * "ZoneAliasStart" - used to calculate zone alias unless overriden. By default a zone's alias is this number + localindex offset.

There are more but this is enough for now.

Since this all has no impact on gameplay (except ZoneAliasStart but that has minimal impact), the values are up to you. Here's what I used:

```
"Title": "Newbie guide rundown"
"SurfaceDescription": "<b>This</b> is a rundown.\nDear God...\nThere's more.\nNo!"
"Prefix": "F"
"PublicName": "Pollutant"
"ExpeditionDepth": 527
"ExpeditionDescription": "This is an example level created for the newbie guide"
"RoleplayedWardenIntel": ">.. Have we been here before?\r\n<size=20%>Yes</size>\r\n<color=red>>..No, you must be going insane..</color>"
"ZoneAliasStart": 100
```

The results:

![Edited Intel screen](<../../.gitbook/assets/paveikslas (4).png>)

![Edited expedition details](<../../.gitbook/assets/image (30) (1).png>)

![Changed zone aliases](<../../.gitbook/assets/paveikslas (3) (1).png>)

There are more fields related to visual data in rundown and level layout but with this we have enough to make unique vanilla-style rundown & level information. We can move on to the 3rd step in the guide.
