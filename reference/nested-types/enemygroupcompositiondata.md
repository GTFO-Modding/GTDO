---
description: EnemyGroupCompositionData
---

# EnemyGroupCompositionData

Defines entries in [EnemyGroup](../datablocks/enemygroup.md), each matching one [EnemyPopulation](../datablocks/enemypopulation.md) entry when selected.

## Fields

### Role - [eEnemyRole](../enum-types.md#eenemyrole) (enum)

The role match of this entry.

Note that roles have special values, see more information in [EnemySpawningData](enemyspawningdata.md#how-to-pick-enemy-spawns).

### Distribution - [eEnemyRoleDistribution](../enum-types.md#eenemyroledistribution) (enum)

Multiplier for MaxScore, setting how much score this role will get. Affects how many enemies spawn.

E.g. Rel\_50 and MaxScore 10 will give this role 5 score. Assuming selected EnemyPopulation entry has a cost of 1.0, 5 enemies will spawn.

Force\_One will spawn exactly one enemy.
