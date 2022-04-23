---
description: ActiveEnemyWaveData
---

# ActiveEnemyWaveData

Blood door settings.

## Fields

{% hint style="warning" %}
You should always make sure the group type you're spawning is set to "Hunter", otherwise the enemies will not spawn aggressive.
{% endhint %}

### HasActiveEnemyWave - Boolean

Whether the gate to the zone is a blood door.

### EnemyGroupInfrontOfDoor - UInt32

Enemy group to spawn right in front of the door.

### EnemyGroupInArea - UInt32

Enemy group to spawn anywhere in the area.

By the time the door opens, most enemies will have reached the door.

### EnemyGroupsInArea - Int32

Count of EnemyGroupInArea instances to spawn.
