---
description: >-
  Shows where you can see the finished datablocks and the changes made since
  then
---

# Final datablocks version

Since R6 is gone now and so are the source blocks, some things have changed and the guide may be hard to follow. You may want to see what blocks were used when originally developing the guide, or perhaps you just want to check/copy a specific block. Either way, the guide blocks are now stored on git:

{% embed url="https://github.com/UntiIted/GTFO-NewbieLevelGuide" %}

You can also check out the commits to see any changes made since initial release. I will also cover some changes here as well.

### R7 update

Since MTFO now supports loading only specific blocks (also to fix some crap broken by R7 like players' shoes, shooters with pouncer stance and so on), the blocks have been minimized.

Additionally, the exit zone size has been changed so the max size isn't reached before exit geomorph is generated.

Here's the new map:

![Updated map in R7](<../../.gitbook/assets/map updated.png>)

### R1 ALT update

Now that devs have confirmed they're officially killing the game (and keeping old rundowns), code-wise it shouldn't change much, which means less maintenance work for rundown developers.

With this update, there's only 2 things to do to get old levels to work:

1. Change [GameSetup](../../reference/datablocks/rarely-edited/gamesetup.md) rundown ids to load into a list
2. Add the tutorial rundown (its reference is hardcoded so we can't get rid of it)

That's it. The layout doesn't even reroll. Unless you were using some mods that are now broken (this guide only uses MTFO), the level should be fully functional.
