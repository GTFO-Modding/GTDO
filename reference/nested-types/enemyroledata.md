---
description: EnemyRoleData
---

# EnemyRoleData

Maps Role/Difficulty matches to enemies using persistentIDs from [EnemyDataBlock](../datablocks/enemy.md).

## Fields

### Role - [eEnemyRole](../enum-types.md#eenemyrole) (enum)

Role match of this entry.

Note that roles have special values, see more information in [EnemySpawningData](enemyspawningdata.md#how-to-pick-enemy-spawns).

### Difficulty - [eEnemyRoleDifficulty](../enum-types.md#eenemyroledifficulty) (enum)

Difficulty match of this entry.

### Enemy - UInt32

Enemy persistentID of this entry.

### Cost - Single

Cost of this entry. Affects how many enemies spawn when this entry is selected.

### Weight - Single

Relative weight of this entry. Affects how likely it is to be selected when several are matched.
