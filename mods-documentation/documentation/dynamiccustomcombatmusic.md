---
description: Overcomplicated and unmaintainable
---

# DynamicCustomCombatMusic

### Developer

Discord: Stormpooper#3436

### Prerequisites

User should be familiar with editing datablocks and willing to lose sanity.

The mod provides no music by default, the user should be able to build asset bundles with music clips.

### Additional notes

The [Warmup](https://gtfo.thunderstore.io/package/Untilted/Warmup/) rundown is used as a demonstration of this plugin.

### Description

This mod can play different music based on the current situation - active events (reading wave settings), posted sound events, aggressive enemy count/types/distance. Enemy values are collected into a "threat" value, a score indicating how difficult the situation is.&#x20;

The music is divided into 3 sections hierarchically: music entry, stage, and loop/clip. A music entry is essentially an entire datablock depicting one piece of music. An entry can hold any amount of stages, each of which specifies what to play for a certain threat level. Finally, each stage can hold any amount of loops/clips, which are simply separate audio clips that are part of the same threat level.

2 main PersistentData config files are used by the mod:

* DynamicMusicData.json - defines music entries
* ThreatData.json - defines threat entries

To specify what settings a level should read, modify the "DevInfo" field in RundownDataBlock for the level you need. Write "threatdata\_x" for threat settings, where x is the ID, and the same way "dynamicmusicdata" for music settings. Only one threat value will be read for any level, but any amount of music settings is accepted.

<figure><img src="../../.gitbook/assets/image (7) (3).png" alt=""><figcaption><p>DevInfo with threat and dynamic musid settings specified</p></figcaption></figure>

To export this data with your rundown, refer to [ConfigurableGlobalWaveSettings](configurableglobalwavesettings.md#exporting). The process is the same, simply adapt it to this mod's files and dependencies.

Remember to include the music asset bundle with your rundown.
