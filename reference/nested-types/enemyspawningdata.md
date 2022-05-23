---
description: EnemySpawningData
---

# EnemySpawningData

Defines sleeper spawns.

## Fields

### GroupType - [eEnemyGroupType](../enum-types.md#eenemygrouptype) (enum)

Type of enemy group to match in [EnemyGroupDataBlock](../datablocks/enemygroup.md).

Hunter is made for blood doors.

Patrol is broken.

Rest of valid values result in hibernate, and invalid values result in no spawns.

### Difficulty - [eEnemyRoleDifficulty](../enum-types.md#eenemyroledifficulty) (enum)

Difficulty of enemy group (and further along - role) to match in EnemyGroupDataBlock and [EnemyPopulationDataBlock](../datablocks/enemypopulation.md).

### Distribution - [eEnemyZoneDistribution](../enum-types.md#eenemyzonedistribution) (enum)

Distribution mode.

Force\_One will always spawn exactly one group.

Rel\_Value will use score system.

### DistributionValue - Single

When Distribution is set to Rel\_Value, the score multiplier for the value set in [ExpeditionBalancing](../datablocks/expeditionbalance.md).

## How to pick enemy spawns

### Enemy spawning system

Enemy spawns in this system are quite roundabout. The system for picking what enemy to spawn can be visualized like this:

![The process for picking what sleepers to spawn.](<../../.gitbook/assets/image (2).png>)

There are several layers of randomization present here. The process for each EnemySpawningData entry is as follows:

1. Select an EnemyGroup entry matching GroupType and Difficulty settings randomly (using weights);
2. Deduct MaxScore from remaining distribution for this EnemySpawningData entry (if not forced);
3. For each role, match an EnemyPopulation entry using Difficulty and Role settings randomly (using weights);
4. Spawn selected population entry's Enemy matching EnemyDataBlock PersistentID. Number of enemies spawned is MaxScore \* RoleDistribution / Cost (e.g. using settings seen in picture - `12 * 1 / 1 = 12`. Function used for rounding is [RoundToInt](https://docs.unity3d.com/ScriptReference/Mathf.RoundToInt.html);
5. Repeat the process until remaining population score is equal to or below 3.

In practice, MaxScore has a hardcoded random multiplier of 1-1.2. In the above example, you might end up with up to 14 strikers (score deducted from remaining distribution is also adjusted). If you want exact counts of enemies, you'll have to use Force\_One settings.

{% hint style="warning" %}
EnemyGroup Type "Hunter" is special - always spawns aggressive enemies. Use it only for blood doors.

EnemyPopulation Role "Scout" is special - it spawns enemies in scout mode. Use it only for scouts.

EnemyPopulation Role "Patroller" is special but broken - don't use it.
{% endhint %}

### Simplifying the process

The enemy selections are randomized by both enemy group and enemy population. This can be considered overkill, and some modders simplify selection by sticking to specific rules they set for themselves.

For example, you can set rules for EnemyGroup Type:

1. Use "Hunter" type for blood doors (naturally, since this is required for blood doors);
2. Always use type 0 when randomizing spawns, only relying on difficulty to filter;
3. Use type 1 and difficulty matching enemy persistentID when forcing specific enemies to spawn.

The reason we don't just use type and difficulty both matching enemy persistentID is because the game is hardcoded to check for specific types and not spawn anything if it doesn't match. Difficulty has no checks to it.
