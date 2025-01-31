---
description: GameData_GearCategoryDataBlock_bin.json (filled)
---

# GearCategory

This datablock collects several different DataBlock entries and types of metadata and integrates them into a single entry that can be referenced in the [PlayerOfflineGearDatablock](playerofflinegear.md):

* An [ItemDataBlock](item.md) entry ([BaseItem](gearcategory.md#baseitem-uint32-itemdatablock), defining what kind of item something is)
* 4 [ArchetypeDataBlock](archetype.md) fire modes (for projectile weapons)
* A Melee attack mode (also from [ArchetypeDataBlock](archetype.md), for Melee weapons)
* A priority list for Part alignments, used when a weapon is assembled in [PlayerOfflineGearDataBlock](playerofflinegear.md)

## Fields

### PublicName - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

In-game name, not used for weapons.

### Description - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

Lobby description, not used by weapons.

### BaseItem - UInt32 ([ItemDataBlock](item.md))

PersistentID of an entry in ItemDataBlock.

### HUDIcon - String

No description provided.

### IconRotationOffset - Single

No description provided.

### IconZoomOffset - Single

No description provided.

### FPSArmPoseName - String

No description provided.

### ThirdPersonFullbodyMovement - [eFullbodyPlayerMovementSet](../../enum-types.md#efullbodyplayermovementset) (enum)

Third-person animation set this item uses.

### SemiArchetype - UInt32 ([ArchetypeDataBlock](archetype.md))

A reference to an [ArchetypeDataBlock ](archetype.md)entry, 0th field in fire mode selection.

Does not determine a weapon's actual fire/usage mode, that determination is made in a weapon's [PlayerOfflineGearDataBlock ](playerofflinegear.md)GearJSON.

### BurstArchetype - UInt32 ([ArchetypeDataBlock](archetype.md))

A reference to an [ArchetypeDataBlock ](archetype.md)entry, 1st field in fire mode selection.

Does not determine a weapon's actual fire/usage mode, that determination is made in a weapon's [PlayerOfflineGearDataBlock ](playerofflinegear.md)GearJSON.

### AutoArchetype - UInt32 ([ArchetypeDataBlock](archetype.md))

A reference to an [ArchetypeDataBlock ](archetype.md)entry, 2nd field in fire mode selection.

Does not determine a weapon's actual fire/usage mode, that determination is made in a weapon's [PlayerOfflineGearDataBlock ](playerofflinegear.md)GearJSON.

### SemiBurstArchetype - UInt32 ([ArchetypeDataBlock](archetype.md))

A reference to an [ArchetypeDataBlock ](archetype.md)entry, 3rd field in fire mode selection.

Does not determine a weapon's actual fire/usage mode, that determination is made in a weapon's [PlayerOfflineGearDataBlock ](playerofflinegear.md)GearJSON.

### MeleeArchetype - UInt32 ([MeleeArchetypeDataBlock](meleearchetype.md))

No description provided.

### PartAlignPriority - [List GearPartAlignPriority](../../nested-types/gearpartalignpriority.md) (nested type)

Determines how parts with conflicting aligns behave.

### name - String

Internal name string for this DataBlock entry.

Not used in-game.
