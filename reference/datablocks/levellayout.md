---
description: GameData_LevelLayoutDataBlock_bin.json (filled)
---

# LevelLayout

Level layout is the main block defining what the level looks like and what you can find in it, including resources, enemies, terminals etc.

## Fields

### ZoneAliasStart - Int32

The number of the first zone as seen in-game. The rest are derived from this and LocalIndex.

### Zones - [List ExpeditionZoneData](../nested-types/expeditionzonedata.md) (nested type)

List containing the data of each zone. Each entry is one zone in the map. The first zone in the list is the entrance/elevator (NOT localindex 0).
