---
description: GameData_RundownDataBlock_bin.json
---

# Rundown

The rundown datablock defines everything within the entire rundown, including levels, weapons, enemies, and more. Only one rundown can be loaded at a time, and it is chosen in the [GameSetup](gamesetup.md) datablock.

## Fields

### **UseTierUnlockRequirements -** Boolean

Whether or not to use unlock requirements for this rundown.

### ReqToReachTierB - [RundownTierProgressionData](../nested-types/rundowntierprogressiondata.md) (Nested Type)

Progression data to reach tier B of the rundown.

### ReqToReachTier**C** - [RundownTierProgressionData](../nested-types/rundowntierprogressiondata.md) (Nested Type)

Progression data to reach tier C of the rundown.

### ReqToReachTierD - [RundownTierProgressionData](../nested-types/rundowntierprogressiondata.md) (Nested Type)

Progression data to reach tier D of the rundown.

### ReqToReachTierE - [RundownTierProgressionData](../nested-types/rundowntierprogressiondata.md) (Nested Type)

Progression data to reach tier E of the rundown.

### StorytellingData - [RundownStorytellingData](../nested-types/rundownstorytellingdata.md) (Nested Type)

Data for title, visuals, and description of the rundown.

### **VanityItemLayerDropDataBlock -** UInt32

The id for the [vanity item datablock](vanityitemslayerdrops.md) for this rundown.

### TierA - List [ExpeditionInTierData](../nested-types/expeditionintierdata.md) (Nested Type)

Expedition data for all levels in tier A of this rundown.

### TierB - List [ExpeditionInTierData](../nested-types/expeditionintierdata.md) (Nested Type)

Expedition data for all levels in tier B of this rundown.

### TierC - List [ExpeditionInTierData](../nested-types/expeditionintierdata.md) (Nested Type)

Expedition data for all levels in tier C of this rundown.

### TierD - List [ExpeditionInTierData](../nested-types/expeditionintierdata.md) (Nested Type)

Expedition data for all levels in tier D of this rundown.

### TierE - List [ExpeditionInTierData](../nested-types/expeditionintierdata.md) (Nested Type)

Expedition data for all levels in tier E of this rundown.

