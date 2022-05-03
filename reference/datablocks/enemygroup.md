---
description: GameData_EnemyGroupDataBlock_bin.json
---

# EnemyGroup

This datablock is used for setting enemy spawns with a focus on randomization.

{% hint style="info" %}
Spawning enemies is explained in [EnemySpawningData](../nested-types/enemyspawningdata.md#how-to-pick-enemy-spawns).
{% endhint %}

{% hint style="warning" %}
EnemyGroup blocks 37 and 38 are used by birther and birther boss respectively. This can only be changed with mods.
{% endhint %}

## Fields

### Type - [eEnemyGroupType](../enum-types.md#eenemygrouptype) (enum)

Type match of this group.

There are special types, explained in [EnemySpawningData](../nested-types/enemyspawningdata.md#how-to-pick-enemy-spawns).

### Difficulty - [eEnemyRoleDifficulty](../enum-types.md#eenemyroledifficulty) (enum)

Difficulty match of this group.

### SpawnPlacementType - [eSpawnPlacementType](../enum-types.md#espawnplacementtype) (enum)

Defines where enemies are placed in the selected area.

### MaxScore - Single

The score (or population points/cost) of this group.

### ScoreInAreaPaddingMulti - Single

Multiplier for MaxScore when adding to total placed score in area.

The higher the area's score, the less likely it is to be picked for another enemy group.

### RelativeWeight - Single

Relative weight of this group. Affects how likely it is to be selected when several are matched.

### Roles - [List EnemyGroupCompositionData](../nested-types/enemygroupcompositiondata.md) (nested type)

List of roles in this group. Each role will spawn one type of enemy when this group is selected.
