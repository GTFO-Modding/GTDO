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

This innocent little string here contains an absurd amount of information in an even more absurd format (it's JSON embedded into JSON). It's most likely this way because it's sent over the network to all other players, so the devs didn't make it more readable in a DataBlock.

This JSON and its meaning (including various related DataBlocks) is covered in the [Creating Custom Weapons guide](../../../guides/creating-custom-weapons.md).
