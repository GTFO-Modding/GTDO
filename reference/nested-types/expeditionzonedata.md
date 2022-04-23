---
description: ExpeditionZoneData
---

# ExpeditionZoneData

The level layout data of a single zone.

## Fields

{% hint style="warning" %}
The value range of all Subseeds is 0-1022.
{% endhint %}

{% hint style="warning" %}
When changing the seeds of a zone (SubSeed, MarkerSubSeed, etc) keep in mind that there is a high chance subsequent zones will also have their layout affected. It's a good idea to change zone seeds in the order they appear in to avoid unwanted changes.
{% endhint %}

### LocalIndex - [eLocalZoneIndex](../enum-types.md#elocalzoneindex) (enum)

Local index is an identifier, used to refer to this zone from elsewhere. While the enum values are limited, going over the max using underlying int type works fine for most features.

### AliasOverride - Int32

Sets the zone alias to this value.

### OverrideAliasPrefix - Boolean

Whether to use AliasPrefix overrides instead of the default "Z" or "Zone" text.

### AliasPrefixOverride - String

The prefix text when OverrideAliasPrefix is set to true.

### AliasPrefixShortOverride - String

The short prefix ("Z") text when OverrideAliasPrefix is set to true.

### SubSeed - Int32

Rerolls the layout of this zone specifically.&#x20;

### MarkerSubSeed - Int32

Rerolls the markers of this zone.

### LightsSubSeed - Int32

Rerolls the lights of this zone.

### BulkheadDCScanSeed - Int32

If set, will make the scan static.

This setting might be currently broken.

### SubComplex - [SubComplex](../enum-types.md#subcomplex) (enum)

The subcomplex of this zone. Sets which values from resource set are taken.

Note that all complexes have their set of subcomplexes and not all values will work.

### CustomGeomorph - String

If set, will generate only this geomorph in the zone (sometimes tiles from the previous zone can carry over).

Required for exit elevator and certain objectives like reactor and generator cluster.

Sometimes you have to change seeds or zone sizes for this to generate correctly.

Only values set as custom geomorphs in complex resource set can be specified here.

### CoverageMinMax - Vector2

Min-max size of the zone. For predictable zone size these values should be the same.

The coverage of the zone is added up from its areas. Coverage of each area only has specific values assigned:

![Area coverage size values](<../../.gitbook/assets/image (3).png>)

The size of an area is set in prefabs, meaning every area has its size predefined and never changes.

### BuildFromLocalIndex - [eLocalZoneIndex](../enum-types.md#elocalzoneindex) (enum)

The source zone to build this from. Does not matter for the first zone in the list.

### StartPosition - [eZoneBuildFromType](../enum-types.md#ezonebuildfromtype) (enum)

Where in the source zone to try to make the entrance to this zone.

Note that a valid gate may not generate around the set source position/area.

### StartPosition\_IndexWeight - Single

Calculates the source area depending on a value from 0 to 1. With 5 areas, 0.4 should set it to area B (though you might want to set it a little higher thanks to how floats work).

Only used when StartPosition is set to "From\_IndexWeight".

### StartExpansion - [eZoneBuildFromExpansionType](../enum-types.md#ezonebuildfromexpansiontype) (enum)

Towards which direction should the source gate to this zone be.&#x20;

This direction is not dependent on the source zone, it's global. Forward is forward looking from elevator etc.

### ZoneExpansion - [eZoneExpansionType](../enum-types.md#ezoneexpansiontype) (enum)

How should the zone expand.

Directions are not dependent on the source zone. Forward is forward looking from elevator etc.

Collapsed tries to take as little space as possible, expansional does the opposite.

### LightSettings - UInt32

Light settings for this zone. If set, overrides the value set in rundown datablock.

### AltitudeData - [AltitudeData](altitudedata.md) (nested type)

Altitude data defines the desired height of the zone. Only 3 height values exist by default in the game.

Does not make a difference for starting areas of the level/dimension.

### EventsOnEnter - [List LevelEventData](leveleventdata.md) (nested type)

Events to trigger when the door to this zone is opened.

### EventsOnPortalWarp - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

Events to trigger when the portal scan is complete (this is for the source zone, not destination).

### EventsOnApproachDoor - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

Currently seems unused. Events to trigger when a player gets close to the door.

### EventsOnUnlockDoor - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

Events to trigger when door is unlocked.

### EventsOnOpenDoor - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

Events to trigger when the door to this zone is opened.

If you're wondering what the difference is between this and EventsOnEnter, it's the type.

### EventsOnDoorScanStart - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

Events to trigger when the chained puzzle of this zone starts.

### EventsOnDoorScanDone - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

Events to trigger when the chained puzzle of this zone ends.

### EventsOnBossDeath - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

Called when an enemy considered a "boss" dies in this zone. Unfortunately it seems like boss is specific to squidBoss (D1) at the moment.

### EventsOnTrigger - [List WorldEventFromSourceData](worldeventfromsourcedata.md) (nested type)

New in R6.5, used in R6.5DX. Can be used to trigger events when a player approaches an object in a level. Unfortunately what objects act as triggers is defined in the prefabs, making them uneditable from datablocks.

### ProgressionPuzzleToEnter - [ProgressionPuzzleData](progressionpuzzledata.md) (nested type)

Sets the puzzle to enter this zone, e.g. keycard.

### ChainedPuzzleToEnter - UInt32

Sets the chained puzzle (scan) to enter this zone.

### IsCheckpointDoor - Boolean

Whether to put a checkpoint scan here.

### PlayScannerVoiceAudio - Boolean

Whether to play the generic "please enter the bioscan" voicelines.

### SecurityGateToEnter - [eSecurityGateType](../enum-types.md#esecuritygatetype) (enum)

What type of gate should generate to this zone.

### UseStaticBioscanPointsInZone - Boolean

Whether to use the bioscan points defined in prefabs for the scans.

### TurnOffAlarmOnTerminal - Boolean

Whether the alarm of this zone is turned off on a terminal.

### TerminalPuzzleZone - [TerminalZoneSelectionData](terminalzoneselectiondata.md) (nested type)

Terminal data used when TurnOffAlarmOnTerminal is set to true.

### EventsOnTerminalDeactivateAlarm - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

Events to trigger when disable alarm terminal command is called.

### ActiveEnemyWave - [ActiveEnemyWaveData](activeenemywavedata.md) (nested type)

Blood door settings.

### EnemySpawningInZone - [List EnemySpawningData](enemyspawningdata.md) (nested type)

Sleepers in this zone.

### EnemyRespawning - Boolean

Whether enemy respawning is enabled in this zone.

### EnemyRespawnRequireOtherZone - Boolean

Whether the players need to be in another zone for enemies to respawn here.

### EnemyRespawnRoomDistance - Int32

How many areas away does the closest player need to be for enemies to respawn here. 0 means they can respawn in your area.

### EnemyRespawnTimeInterval - Single

How often the respawn check is run. Does not depend on enemies getting killed or player locations, this runs from level start.

### EnemyRespawnCountMultiplier - Single

Multiplier for how many enemies respawn.&#x20;

Does not change progressively. E.g. 0.5 and 20 initially should respawn enemies up to 10 whenever it falls below that number. Above 1 will just most likely cause more enemies to spawn before you even enter the zone for the first time.

### EnemyRespawnExcludeList - List UInt32

List enemy IDs that should not be respawned.

### HSUClustersInZone - Int32

Number of HSU clusters in zone.

### CorpseClustersInZone - Int32

Number of corpse clusters in zone.

### ResourceContainerClustersInZone - Int32

Number of resource container clusters in zone.&#x20;

Not required for resources to spawn.

Might be unused.

### GeneratorClustersInZone - Int32

Number of generator clusters in zone.

### CorpsesInZone - [eZoneDistributionAmount](../enum-types.md#ezonedistributionamount) (enum)

Number of corpses in zone.

### GroundSpawnersInZone - [eZoneDistributionAmount](../enum-types.md#ezonedistributionamount) (enum)

Number of ground spawners (spots for consumables to spawn on the ground, on shelves etc. anywhere that's not in resource containers).

### HSUsInZone - [eZoneDistributionAmount](../enum-types.md#ezonedistributionamount) (enum)

Number of HSUs in zone.

### DeconUnitsInZone - [eZoneDistributionAmount](../enum-types.md#ezonedistributionamount) (enum)

Might be unused.

### AllowSmallPickupsAllocation - Boolean

Does not prevent anything from spawning, only affects LG.

### AllowResourceContainerAllocation - Boolean

Does not prevent anything from spawning, only affects LG.

### ForceBigPickupsAllocation - Boolean

Affects LG.

### ConsumableDistributionInZone - UInt32

Consumable distribution in zone.

### BigPickupDistributionInZone - UInt32

BigPickup distribution in zone.

### TerminalPlacements - [List TerminalPlacementData](terminalplacementdata.md) (nested type)

Teminals in zone.

### ForbidTerminalsInZone - Boolean

If set to true, terminals can't spawn here.

### PowerGeneratorPlacements - [List FunctionPlacementData](functionplacementdata.md) (nested type)

Generators in zone.

### DisinfectionStationPlacements - [List FunctionPlacementData](functionplacementdata.md) (nested type)

Disinfection stations in zone.

### HealthMulti - Single

Multiplier for health resources in this zone. Relative to ExpeditionBalance.

### HealthPlacement - [ZonePlacementWeights](zoneplacementweights.md) (nested type)

Health locations in zone.

### WeaponAmmoMulti - Single

Multiplier for ammo resources in this zone. Relative to ExpeditionBalance.

### WeaponAmmoPlacement - [ZonePlacementWeights](zoneplacementweights.md) (nested type)

Ammo locations in zone.

### ToolAmmoMulti - Single

Multiplier for tool resources in this zone. Relative to ExpeditionBalance.

### ToolAmmoPlacement - [ZonePlacementWeights](zoneplacementweights.md) (nested type)

Tool locations in zone.

### DisinfectionMulti - Single

Multiplier for disinfection resources in this zone. Relative to ExpeditionBalance.

### DisinfectionPlacement - [ZonePlacementWeights](zoneplacementweights.md) (nested type)

Disinfection locations in zone.

### StaticSpawnDataContainers - [List StaticSpawnDataContainer](staticspawndatacontainer.md) (nested type)

Used for static spawns (e.g. spitters).
