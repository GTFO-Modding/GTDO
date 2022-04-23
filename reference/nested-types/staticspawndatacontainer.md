---
description: StaticSpawnDataContainer
---

# StaticSpawnDataContainer

Defines [static spawn](../datablocks/staticspawn.md#fields) placements.

## Fields

### Count - Int32

Count to spawn.

### DistributionWeightType - [LG\_StaticDistributionWeightType](../enum-types.md#lg\_staticdistributionweighttype) (enum)

Defines random distribution type.

Weight\_is\_zeroToOne\_startToEnd - scales DistributionWeight from zero to one by area.

Weight\_is\_exact\_node\_index - clamps DistributionWeight to area index.

### DistributionWeight - Single

Weight value for distribution.

### DistributionRandomBlend - Single

How much (0-1) session seed is allowed to affect weight.

### DistributionResultPow - Single

Raises distribution result to this power.

### StaticSpawnDataId - UInt32

Static spawn ID.

### FixedSeed - Int32

Defines fixed seed. Used when static spawn RandomType is set to fixed seed.
