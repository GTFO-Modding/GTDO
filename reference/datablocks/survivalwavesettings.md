---
description: GameData_SurvivalWaveSettingsDataBlock_bin.json
---

# SurvivalWaveSettings

Provides the settings for alarms, scout waves and similar types of waves (all referred to as "alarm" in sections below).

## Fields

{% hint style="warning" %}
SurvivalWaveSettings is the only known type where persistentID value range is changed from default to 0-255
{% endhint %}

&#x20;All time-related settings are specified in seconds.

### m\_pauseBeforeStart - Single

Delay before waves start spawning after alarm start.

### m\_pauseBetweenGroups - Single

Delay between enemy groups.

### m\_wavePauseMin\_atCost - Single

Minimum score boundary for pauses between waves.

### m\_wavePauseMax\_atCost - Single

Maximum score boundary for pauses between waves.

Above this threshold, the timer for a new wave doesn't move.

Anywhere in-between min and max, the timer speed is lerped.

### m\_wavePauseMin - Single

Delay between waves at or below minimum score boundary.

### m\_wavePauseMax - Single

Delay between waves at maximum score boundary.

### m\_populationFilter - [List eEnemyType](../enum-types.md#eenemytype) (enum)

List of enemy types in filter.

### m\_filterType - [eEnemyFilterType](../enum-types.md#eenemyfiltertype) (enum)

Whether to spawn only, or spawn all but the types included in population filter.

### m\_chanceToRandomizeSpawnDirectionPerWave - Single

Chance for spawn direction to change between waves.

### m\_chanceToRandomizeSpawnDirectionPerGroup - Single

Change for spawn direction to change between groups.

### m\_overrideWaveSpawnType - Boolean

Whether to override spawn type set in code.

### m\_survivalWaveSpawnType - [SurvivalWaveSpawnType](../enum-types.md#survivalwavespawntype) (enum)

The spawn type when override is set to true.

### m\_populationPointsTotal - Single

The total population points for waves. The alarm automatically stops if this runs out. -1 is infinite.

### m\_populationPointsPerWaveStart - Single

Population points for a wave at start ramp.

### m\_populationPointsPerWaveEnd - Single

Population points for a wave at end ramp.

### m\_populationPointsMinPerGroup - Single

Minimum required cost for a group to spawn. This setting is related to the soft cap of enemies.

### m\_populationPointsPerGroupStart - Single

Population points for a group at start ramp.

### m\_populationPointsPerGroupEnd - Single

Population points for a group at end ramp.

### m\_populationRampOverTime - Single

Lerp over time for start-end population point settings.

## Regarding population points and soft cap

By default the game has some hardcoded values set that are used for score settings - cost of an enemy and soft cap.

Enemy costs per type are the following: 0.75 1 1 2 2.

Soft cap (MaxAllowedCost) is 25.

All aggressive enemies count towards cap. If the remaining allowed cost is lower than the minimum required cost of a group, the group cannot spawn and the wave pauses until enough points are available. The enemy type here is determined in [EnemyDataBlock](enemy.md#enemytype-eenemytype-enum).

The enemy type for wave population point cost is determined by wave settings.
