---
description: GameData_EnemyPopulationDataBlock_bin.json (filled)
---

# EnemyPopulation

This datablock is used to select enemies by [EnemyGroupDataBlock](enemygroup.md) through filters.

While technically you can have several population blocks, usually only the first block is used both in-game and by modders.

{% hint style="info" %}
Spawning enemies is explained in [EnemySpawningData](../nested-types/enemyspawningdata.md#how-to-pick-enemy-spawns).
{% endhint %}

## Fields

### RoleDatas - [List EnemyRoleData](../nested-types/enemyroledata.md) (nested type)

List of enemy role entries.
