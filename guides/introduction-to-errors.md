---
description: >-
  You will run into some if you play enough modded. You might have already run
  into some without even knowing it. You have already run into some you don't
  even know about.
---

# Introduction to Errors

## Overview

Originally covered in [The Complete Newbie Guide](the-complete-newbie-guide.md), but it deserves its own page. Besides, it's useful for all users.

Errors and exceptions often mean something went wrong either with the game or a mod. There's an infinite number of causes so it's impossible to know all of them, but it's important to know where to start looking for information. At the very least you can pass on more when looking for help. If you do run into something you can't fix yourself, you can ask in the [tech support channel](https://discord.com/channels/782438773690597389/782451402676109362) in the modding discord.

## Important distinctions

* Error/Exception - while in a way they mean the same thing to a user, the distinct difference is that if you see "error", it is printed by programmers, whereas "exception" shows that it came straight from code.
* BepInEx logs/game logs - BepinEx logs are shown in the console window and LogOutput.log, meanwhile game logs are stored in `%userprofile%\AppData\LocalLow\10 Chambers Collective\GTFO`. While some information overlaps, game logs show more useful base game error information, and show a good amount of non-error information as well.

## Viewing errors

When launching the game with mods enabled, you'll see the BepInEx console as a separate window.&#x20;

![BepInEx console window](<../.gitbook/assets/image (13) (2).png>)

This console is useful for many things, but most importantly for users, it shows **most** errors in red text. If it's not a red text error, it can be relevant to rundown developers specifically, so it's not covered here.

{% hint style="info" %}
Not all red text means you have to do something about it. Some mods post meaningless errors on purpose (although they really shouldn't), and some base game errors are meaningless as well.

In the case of mods, the message is probably something intentionally stupid.

In the case of game errors, check the game logs to see if they contain that error. If they don't, you can probably ignore it.
{% endhint %}

All logged messages have the type and source as a prefix. E.g. `[Error: MTFO] error message` shows that there was an error caused by the mod MTFO. Most of the time errors are thrown by the game itself (but the underlying cause can still be a mod), in which case you will see `[Error: Unity]` as the prefix. In this case it is recommended to look for the error in the game logs instead of BepInEx logs. These are located in `%userprofile%\AppData\LocalLow\10 Chambers Collective\GTFO` If you closed the game already, their name will be of the following format: `GTFO.[Date].[Time]_[PlayerNick]_[NetworkStatus]`. If the game is still open (or crashed), it'll instead be `GTFO.[Date].[Time]_NICKNAME_NETSTATUS`. For the most part you will be looking for the most recent file created.

{% hint style="info" %}
It is also possible to see an error coming from something that doesn't match any mod names nor base game (such as Preloader or Detour). Treat it as an error coming from mods in that case.
{% endhint %}

While in BepInEx console the error message is one line, the game logs provide the stack trace, which is the full source of the error and often provides much more information than just the error message.

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

`NullReferenceException` is one of the most common errors that says next to nothing about the cause. All we know from BepInEx console is that an error happened, but the game logs show that the source is from melee weapons. Even if this error doesn't give enough information to you, it will allow other people to find the cause faster if you ask for help.

Also note that some errors can cause even more errors. When debugging, check the oldest errors first.
