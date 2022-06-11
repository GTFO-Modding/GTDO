---
description: GameData_SurvivalWavePopulationDataBlock_bin.json (filled)
---

# SurvivalWavePopulation

This block is used for assigning [eEnemyType](../../enum-types.md#eenemytype) types from [SurvivalWaveSettingsDataBlock](survivalwavesettings.md) to actual enemies using PersistentID from EnemyDataBlock.

## Fields

### WaveRoleWeakling - UInt32 ([EnemyDataBlock](enemy.md))

EnemyDataBlock PersistentID of [eEnemyType](../../enum-types.md#eenemytype) Weakling for this population.

### WaveRoleStandard - UInt32 ([EnemyDataBlock](enemy.md))

EnemyDataBlock PersistentID of [eEnemyType](../../enum-types.md#eenemytype) Standard for this population.

### WaveRoleSpecial - UInt32 ([EnemyDataBlock](enemy.md))

EnemyDataBlock PersistentID of [eEnemyType](../../enum-types.md#eenemytype) Special for this population.

### WaveRoleMiniBoss - UInt32 ([EnemyDataBlock](enemy.md))

EnemyDataBlock PersistentID of [eEnemyType](../../enum-types.md#eenemytype) MiniBoss for this population.

### WaveRoleBoss - UInt32 ([EnemyDataBlock](enemy.md))

EnemyDataBlock PersistentID of [eEnemyType](../../enum-types.md#eenemytype) Boss for this population.

Note that Boss is currently broken in base game.
