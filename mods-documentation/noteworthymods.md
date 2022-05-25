---
description: >-
  This page lists mods that expand what rundown developers can do in a similar
  fashion to editing datablocks
---

# Noteworthy Mods

## [EEC](https://gtfo.thunderstore.io/package/EEC/EEC\_I/)

EEC aka ExtraEnemyCustomization adds a lot more flexibility for designing enemies.

## [LGTuner](https://gtfo.thunderstore.io/package/Flowaria/LGTuner/)

LGTuner is a plugin that adds support to modify results of LevelGeneration by swapping their tiles and plugs. It allows multiple complexes in a level.

## [MTFO.Ext.PartialData](https://gtfo.thunderstore.io/package/Flowaria/MTFO\_Extension\_PartialData/)

PartialData is a plugin that helps Rundown Developers manage datablocks. It includes the following features:&#x20;

1. &#x20;_**Splitting up datablocks**_. It allows you to, for example, store `LevelLayoutData` for different layers/levels in separate files. Also allows separated files to be stored in different folders, enabling datablock categorization.
2. _**Proxy for**_ `PersistentID` _**management**_. It allows you to use strings, which is more readable and make the datablocks more manageable, as the uint `persistentID`. PartialData will help you map persistentID strings to actual uint IDs and detect duplicate IDs. &#x20;
3. _**Live Editing**_. Something similar to "Hot Reload" in MTFO. The difference is that you don't have to press the "Reload Gamedata" button - PartialData checks and applies those changes immediately after you have edited the datablock file, though for most datablocks you still have to regenerate the level to check the changes.\
   Particularly,  changes of `LightSettings` of a zone will be applied immediately without regenerating the level.&#x20;
