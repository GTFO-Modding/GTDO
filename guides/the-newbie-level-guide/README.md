---
description: >-
  This guide should cover level editing enough to get you started making your
  own levels
---

# The Newbie Level Guide

## Overview

{% hint style="danger" %}
The rundown currently out is R6.5, revision 29742. If you're reading afterwards, you may have to adjust. If we're lucky R7 blocks will be mostly compatible with R6.

Be aware that game updates can break datablocks, and levels/rundowns usually suffer the most from this. Rundown developers often don't even port their rundowns after some updates.
{% endhint %}

As you probably already know, levels in GTFO are generated, and their data is stored in datablocks. In terms of difficulty, editing levels is between intermediate and one of the most advanced things in datablocks. This guide is not meant to teach all thing related to level editing, but it will hopefully give you enough to get you going in creating your own levels.

This goes without saying, but if you're looking to learn, I highly recommend editing and testing the blocks yourself as you read along.

Throughout the guide, I'll be posting datablocks or parts of them. If you move along, you won't have to copy-paste them, but you can verify they match using [Diffchecker](https://www.diffchecker.com/) for example.

## Prerequisites

At this point you should be familiar with JSON, datablocks, and the following:

* [The Complete Newbie Guide](../the-complete-newbie-guide.md)
* [Datablocks reference](../../reference/datablocks/)
* [Enum types](../../reference/enum-types.md)
* VS Code editor (technically not required but guide assumes you use it)

Recommended:

* [VS Code tips](../vs-code-tips.md)
* Enable MTFO hot reload (TODO)
* [Dev Toolbelt](https://gtfo.thunderstore.io/package/Endskill/Dev\_Toolbelt/) or some alternative for testing (Don't mind it being deprecated)

## Guide content

The guide is made of 5 parts:

1. Isolating a level
2. Editing rundown and level metadata
3. Adding and editing zones
4. Editing warden objective
5. Adding a secondary sector

The datablocks we work with in this guide:

* Main:
  1. RundownDataBlock
  2. LevelLayoutDataBlock
  3. WardenObjectiveDataBlock
* Edited:
  1. ExpeditionBalanceDataBlock
  2. EnemyGroupDataBlock
  3. EnemyPopulationDataBlock
  4. FogSettingsDataBlock
  5. SurvivalWaveSettingsDataBlock
* Touched:
  1. LightSettingsDataBlock
  2. ConsumableDistributionDataBlock
  3. StaticSpawnDataBlock
  4. BigPickupDistributionDataBlock
  5. ComplexResourceSetDataBlock

## Useful links

* [TypeList](https://github.com/UntiIted/OriginalDataBlocks) (OriginalDataBlocks)
* [Datablock Editor](https://gtfo-modding.github.io/DatablockEditor/) (but actually just level layout editor)
* [Geomorph sheet](https://docs.google.com/document/d/1iSYUASlQSaP6l7PD3HszsXSAxJ-wb8MAVwYxb9xW92c/edit)
* [Diffchecker](https://www.diffchecker.com/)
