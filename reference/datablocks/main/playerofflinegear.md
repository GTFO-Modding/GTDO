---
description: GameData_PlayerOfflineGearDataBlock_bin.json (filled)
---

# PlayerOfflineGear

Defines mostly various weapon parts (references to various gear datablocks) and some other data.

Probably the worst datablock in the game.

## Fields

### Type - [eOfflineGearType](../../enum-types.md#eofflinegeartype) (enum)

The only known use and difference here is "RundownSpecificInventory" which simply changes the text displayed in lobby.

### GearJSON - String

This innocent little string here contains an absurd amount of information in an even more absurd format. It's most likely this way because it's sent over networking and devs didn't care enough to make it more readable in datablocks.

This JSON and its meaning (including various related datablocks) is covered in the weapons guide in [External Guides](../../../guides/external-guides.md#weapon-guide).
