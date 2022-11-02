---
description: If we were in R4, this would be a guide on "optional" error alarms
---

# Adding a secondary sector

## Overview

Finally, the last part of the guide. ~~_level guide using as many mods as possible when?_~~

We have already settled on the objective, but we have to make the sector before we apply it. We're not going to generate a third sector because it's the exact same process.

## Setup

Start with making a new level layout. For a placeholder let's copy the block we have, delete all zones but 0, and clean up all the nightmares we added. Change the alias start to 200, and remember to rename and change ID.

Here's our placeholder layout:

```
  "ZoneAliasStart": 200,
  "Zones": [
    {
      "LocalIndex": 0,
      "AliasOverride": -1,
      "OverrideAliasPrefix": false,
      "SubSeed": 2,
      "MarkerSubSeed": 0,
      "LightsSubSeed": 0,
      "BulkheadDCScanSeed": 0,
      "SubComplex": 2,
      "CustomGeomorph": "",
      "CoverageMinMax": {
        "x": 40.0,
        "y": 45.0
      },
      "BuildFromLocalIndex": 0,
      "StartPosition": 1,
      "StartPosition_IndexWeight": 0.0,
      "StartExpansion": 1,
      "ZoneExpansion": 3,
      "LightSettings": 56,
      "AltitudeData": {
        "AllowedZoneAltitude": 3,
        "ChanceToChange": 0.5
      },
      "EventsOnEnter": [],
      "EventsOnPortalWarp": [],
      "EventsOnApproachDoor": [],
      "EventsOnUnlockDoor": [],
      "EventsOnOpenDoor": [],
      "EventsOnDoorScanStart": [],
      "EventsOnDoorScanDone": [],
      "ProgressionPuzzleToEnter": {
        "PuzzleType": 0,
        "CustomText": 972,
        "PlacementCount": 1,
        "ZonePlacementData": []
      },
      "ChainedPuzzleToEnter": 0,
      "IsCheckpointDoor": false,
      "PlayScannerVoiceAudio": true,
      "SecurityGateToEnter": 0,
      "UseStaticBioscanPointsInZone": false,
      "TurnOffAlarmOnTerminal": false,
      "TerminalPuzzleZone": {
        "LocalIndex": 0,
        "SeedType": 1,
        "TerminalIndex": 0,
        "StaticSeed": 0
      },
      "EventsOnTerminalDeactivateAlarm": [],
      "ActiveEnemyWave": {
        "HasActiveEnemyWave": false,
        "EnemyGroupInfrontOfDoor": 0,
        "EnemyGroupInArea": 0,
        "EnemyGroupsInArea": 0
      },
      "EnemySpawningInZone": [
      ],
      "EnemyRespawning": false,
      "EnemyRespawnRequireOtherZone": true,
      "EnemyRespawnRoomDistance": 2,
      "EnemyRespawnTimeInterval": 10.0,
      "EnemyRespawnCountMultiplier": 1.0,
      "HSUClustersInZone": 0,
      "CorpseClustersInZone": 0,
      "ResourceContainerClustersInZone": 0,
      "GeneratorClustersInZone": 0,
      "CorpsesInZone": 0,
      "GroundSpawnersInZone": 3,
      "HSUsInZone": 0,
      "DeconUnitsInZone": 0,
      "AllowSmallPickupsAllocation": true,
      "AllowResourceContainerAllocation": true,
      "ForceBigPickupsAllocation": true,
      "ConsumableDistributionInZone": 20,
      "BigPickupDistributionInZone": 0,
      "TerminalPlacements": [
        {
          "PlacementWeights": {
            "Start": 1000.0,
            "Middle": 0.0,
            "End": 0.0
          },
          "AreaSeedOffset": 123,
          "MarkerSeedOffset": 123,
          "LocalLogFiles": [
          ],
          "UniqueCommands": [],
          "StartingStateData": {
            "StartingState": 0,
            "AudioEventEnter": 0,
            "AudioEventExit": 0,
            "PasswordProtected": false,
            "PasswordHintText": "Password Required.",
            "GeneratePassword": false,
            "PasswordPartCount": 1,
            "ShowPasswordLength": true,
            "ShowPasswordPartPositions": false,
            "TerminalZoneSelectionDatas": []
          }
        }
      ],
      "ForbidTerminalsInZone": false,
      "PowerGeneratorPlacements": [],
      "DisinfectionStationPlacements": [],
      "HealthMulti": 0.0,
      "HealthPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "WeaponAmmoMulti": 0.0,
      "WeaponAmmoPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "ToolAmmoMulti": 0.0,
      "ToolAmmoPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "DisinfectionMulti": 0.0,
      "DisinfectionPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "StaticSpawnDataContainers": [
      ]
    }
  ],
  "name": "Newbie guide B1 secondary",
  "internalEnabled": true,
  "persistentID": 163
}
```

We already have a placeholder objective, so let's move straight to rundown db.

Enable the secondary layer, set layout, set to build from zone 4 in main layer, set datablock ID to the unsolvable objective.

```
      "SecondaryLayerEnabled": true,
      "SecondaryLayout": 163,
      "BuildSecondaryFrom": {
        "LayerType": 0,
        "Zone": 4
      },
      "SecondaryLayerData": {
        "ZonesWithBulkheadEntrance": [
        ],
        "BulkheadDoorControllerPlacements": [],
        "BulkheadKeyPlacements": [
        ],
        "ObjectiveData": {
          "DataBlockId": 132,
          "WinCondition": 1,
          "ZonePlacementDatas": [
          ]
        },
        "ArtifactData": {
          "ArtifactAmountMulti": 1.0,
          "ArtifactLayerDistributionDataID": 0,
          "ArtifactZoneDistributions": []
        }
      },
```

If you want to lock it with a bulkhead key, all you have to do is add an entry to main layer bulkhead door controller placements and set it to spawn in the same zone as the bulkhead. Remember to also take care of keys in that case. I'll go with secondary always unlocked.

![Bulkhead dc for secondary layer](<../../.gitbook/assets/image (1) (2) (1).png>)

Quick test to see if secondary did spawn and it did. Time to generate the proper layout.

## Layout

Let's keep this small, to reactor basics. The first zone is fine. We're adding a bridge and a reactor geo for a total of 3 zones.

First thing to do here is find the custom geos. Remember you can only spawn something as custom geo if it is in complex resource set custom geos. In rundown db we can see we're using ComplexResourceData 1. Open ComplexResourceSetDataBlock, find ID 1. To make it easier to find what geos we have, I'm going to use breadcrumbs to find the custom geos:

![Breadcrumbs showing custom geos](<../../.gitbook/assets/image (16).png>)

For the most part we care about the Objective block. I'll copy that to a new file to make search easier.

I can see reactor gives 3 results and bridge 0, and I'm not sure the 3 reactor results are actual reactors anyway. Time to consult the [Geomorph sheet](https://docs.google.com/document/d/1iSYUASlQSaP6l7PD3HszsXSAxJ-wb8MAVwYxb9xW92c/edit) (although the search in google docs doesn't seem to be the best search ever).

As suspected, the 3rd result was not an actual reactor geo. I'll take the first reactor (geo\_64x64\_mining\_reactor\_open\_HA\_01) and the classic reactor bridge (geo\_64x64\_mining\_refinery\_I\_HA\_05). I can see that both of these are in complex resource set 1 so I don't have to modify it.

{% hint style="info" %}
If you're wondering whether you could spawn geomorphs from other complexes by messing with complex resource set, the answer is no. Only certain geos are loaded based on the level. The only way to mix complexes is to use mods.
{% endhint %}

Right, so, copy the first zone 2 more times, fix local indexes, add custom geos, and test.

Now this took me a few times with LG being finicky, but I got both geos to spawn in the correct directions. If you want to try for yourself with just pointers, check out how the map generates and adjust start positions and coverage. As I understand (I don't), LG will quit trying if it can't generate what it wants, and it can also skip generating the custom geos if it fills up the coverage size too early (normally when custom geo is set, that's the only thing that generates in the zone, but parts of random-generated geos can carry over from previous zones, filling up the size).

LG is rocket science that deserves its own guide if any poor fool ever bothered to make one, and on top of that it's still changing, so we won't dive too deep into why things happened here.

Anyway here's the level layout I got:

```
{
  "ZoneAliasStart": 200,
  "Zones": [
    {
      "LocalIndex": 0,
      "AliasOverride": -1,
      "OverrideAliasPrefix": false,
      "SubSeed": 2,
      "MarkerSubSeed": 0,
      "LightsSubSeed": 0,
      "BulkheadDCScanSeed": 0,
      "SubComplex": 2,
      "CustomGeomorph": "",
      "CoverageMinMax": {
        "x": 10.0,
        "y": 15.0
      },
      "BuildFromLocalIndex": 0,
      "StartPosition": 1,
      "StartPosition_IndexWeight": 0.0,
      "StartExpansion": 1,
      "ZoneExpansion": 3,
      "LightSettings": 56,
      "AltitudeData": {
        "AllowedZoneAltitude": 3,
        "ChanceToChange": 0.5
      },
      "EventsOnEnter": [],
      "EventsOnPortalWarp": [],
      "EventsOnApproachDoor": [],
      "EventsOnUnlockDoor": [],
      "EventsOnOpenDoor": [],
      "EventsOnDoorScanStart": [],
      "EventsOnDoorScanDone": [],
      "ProgressionPuzzleToEnter": {
        "PuzzleType": 0,
        "CustomText": 972,
        "PlacementCount": 1,
        "ZonePlacementData": []
      },
      "ChainedPuzzleToEnter": 0,
      "IsCheckpointDoor": false,
      "PlayScannerVoiceAudio": false,
      "SecurityGateToEnter": 0,
      "UseStaticBioscanPointsInZone": false,
      "TurnOffAlarmOnTerminal": false,
      "TerminalPuzzleZone": {
        "LocalIndex": 0,
        "SeedType": 1,
        "TerminalIndex": 0,
        "StaticSeed": 0
      },
      "EventsOnTerminalDeactivateAlarm": [],
      "ActiveEnemyWave": {
        "HasActiveEnemyWave": false,
        "EnemyGroupInfrontOfDoor": 0,
        "EnemyGroupInArea": 0,
        "EnemyGroupsInArea": 0
      },
      "EnemySpawningInZone": [
      ],
      "EnemyRespawning": false,
      "EnemyRespawnRequireOtherZone": true,
      "EnemyRespawnRoomDistance": 2,
      "EnemyRespawnTimeInterval": 10.0,
      "EnemyRespawnCountMultiplier": 1.0,
      "HSUClustersInZone": 0,
      "CorpseClustersInZone": 0,
      "ResourceContainerClustersInZone": 0,
      "GeneratorClustersInZone": 0,
      "CorpsesInZone": 0,
      "GroundSpawnersInZone": 3,
      "HSUsInZone": 0,
      "DeconUnitsInZone": 0,
      "AllowSmallPickupsAllocation": true,
      "AllowResourceContainerAllocation": true,
      "ForceBigPickupsAllocation": true,
      "ConsumableDistributionInZone": 20,
      "BigPickupDistributionInZone": 0,
      "TerminalPlacements": [
        {
          "PlacementWeights": {
            "Start": 1000.0,
            "Middle": 0.0,
            "End": 0.0
          },
          "AreaSeedOffset": 123,
          "MarkerSeedOffset": 123,
          "LocalLogFiles": [
          ],
          "UniqueCommands": [],
          "StartingStateData": {
            "StartingState": 0,
            "AudioEventEnter": 0,
            "AudioEventExit": 0,
            "PasswordProtected": false,
            "PasswordHintText": "Password Required.",
            "GeneratePassword": false,
            "PasswordPartCount": 1,
            "ShowPasswordLength": true,
            "ShowPasswordPartPositions": false,
            "TerminalZoneSelectionDatas": []
          }
        }
      ],
      "ForbidTerminalsInZone": false,
      "PowerGeneratorPlacements": [],
      "DisinfectionStationPlacements": [],
      "HealthMulti": 0.0,
      "HealthPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "WeaponAmmoMulti": 0.0,
      "WeaponAmmoPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "ToolAmmoMulti": 0.0,
      "ToolAmmoPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "DisinfectionMulti": 0.0,
      "DisinfectionPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "StaticSpawnDataContainers": [
      ]
    },
    {
      "LocalIndex": 1,
      "AliasOverride": -1,
      "OverrideAliasPrefix": false,
      "SubSeed": 2,
      "MarkerSubSeed": 0,
      "LightsSubSeed": 0,
      "BulkheadDCScanSeed": 0,
      "SubComplex": 2,
      "CustomGeomorph": "Assets/AssetPrefabs/Complex/Mining/Geomorphs/Refinery/geo_64x64_mining_refinery_I_HA_05.prefab",
      "CoverageMinMax": {
        "x": 30.0,
        "y": 30.0
      },
      "BuildFromLocalIndex": 0,
      "StartPosition": 3,
      "StartPosition_IndexWeight": 0.0,
      "StartExpansion": 1,
      "ZoneExpansion": 3,
      "LightSettings": 56,
      "AltitudeData": {
        "AllowedZoneAltitude": 3,
        "ChanceToChange": 0.5
      },
      "EventsOnEnter": [],
      "EventsOnPortalWarp": [],
      "EventsOnApproachDoor": [],
      "EventsOnUnlockDoor": [],
      "EventsOnOpenDoor": [],
      "EventsOnDoorScanStart": [],
      "EventsOnDoorScanDone": [],
      "ProgressionPuzzleToEnter": {
        "PuzzleType": 0,
        "CustomText": 972,
        "PlacementCount": 1,
        "ZonePlacementData": []
      },
      "ChainedPuzzleToEnter": 0,
      "IsCheckpointDoor": false,
      "PlayScannerVoiceAudio": false,
      "SecurityGateToEnter": 0,
      "UseStaticBioscanPointsInZone": false,
      "TurnOffAlarmOnTerminal": false,
      "TerminalPuzzleZone": {
        "LocalIndex": 0,
        "SeedType": 1,
        "TerminalIndex": 0,
        "StaticSeed": 0
      },
      "EventsOnTerminalDeactivateAlarm": [],
      "ActiveEnemyWave": {
        "HasActiveEnemyWave": false,
        "EnemyGroupInfrontOfDoor": 0,
        "EnemyGroupInArea": 0,
        "EnemyGroupsInArea": 0
      },
      "EnemySpawningInZone": [
      ],
      "EnemyRespawning": false,
      "EnemyRespawnRequireOtherZone": true,
      "EnemyRespawnRoomDistance": 2,
      "EnemyRespawnTimeInterval": 10.0,
      "EnemyRespawnCountMultiplier": 1.0,
      "HSUClustersInZone": 0,
      "CorpseClustersInZone": 0,
      "ResourceContainerClustersInZone": 0,
      "GeneratorClustersInZone": 0,
      "CorpsesInZone": 0,
      "GroundSpawnersInZone": 3,
      "HSUsInZone": 0,
      "DeconUnitsInZone": 0,
      "AllowSmallPickupsAllocation": true,
      "AllowResourceContainerAllocation": true,
      "ForceBigPickupsAllocation": true,
      "ConsumableDistributionInZone": 20,
      "BigPickupDistributionInZone": 0,
      "TerminalPlacements": [
        {
          "PlacementWeights": {
            "Start": 1000.0,
            "Middle": 0.0,
            "End": 0.0
          },
          "AreaSeedOffset": 123,
          "MarkerSeedOffset": 123,
          "LocalLogFiles": [
          ],
          "UniqueCommands": [],
          "StartingStateData": {
            "StartingState": 0,
            "AudioEventEnter": 0,
            "AudioEventExit": 0,
            "PasswordProtected": false,
            "PasswordHintText": "Password Required.",
            "GeneratePassword": false,
            "PasswordPartCount": 1,
            "ShowPasswordLength": true,
            "ShowPasswordPartPositions": false,
            "TerminalZoneSelectionDatas": []
          }
        }
      ],
      "ForbidTerminalsInZone": false,
      "PowerGeneratorPlacements": [],
      "DisinfectionStationPlacements": [],
      "HealthMulti": 0.0,
      "HealthPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "WeaponAmmoMulti": 0.0,
      "WeaponAmmoPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "ToolAmmoMulti": 0.0,
      "ToolAmmoPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "DisinfectionMulti": 0.0,
      "DisinfectionPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "StaticSpawnDataContainers": [
      ]
    },
    {
      "LocalIndex": 2,
      "AliasOverride": -1,
      "OverrideAliasPrefix": false,
      "SubSeed": 2,
      "MarkerSubSeed": 0,
      "LightsSubSeed": 0,
      "BulkheadDCScanSeed": 0,
      "SubComplex": 2,
      "CustomGeomorph": "Assets/AssetPrefabs/Complex/Mining/Geomorphs/geo_64x64_mining_reactor_open_HA_01.prefab",
      "CoverageMinMax": {
        "x": 40.0,
        "y": 45.0
      },
      "BuildFromLocalIndex": 1,
      "StartPosition": 1,
      "StartPosition_IndexWeight": 0.0,
      "StartExpansion": 1,
      "ZoneExpansion": 3,
      "LightSettings": 56,
      "AltitudeData": {
        "AllowedZoneAltitude": 3,
        "ChanceToChange": 0.5
      },
      "EventsOnEnter": [],
      "EventsOnPortalWarp": [],
      "EventsOnApproachDoor": [],
      "EventsOnUnlockDoor": [],
      "EventsOnOpenDoor": [],
      "EventsOnDoorScanStart": [],
      "EventsOnDoorScanDone": [],
      "ProgressionPuzzleToEnter": {
        "PuzzleType": 0,
        "CustomText": 972,
        "PlacementCount": 1,
        "ZonePlacementData": []
      },
      "ChainedPuzzleToEnter": 0,
      "IsCheckpointDoor": false,
      "PlayScannerVoiceAudio": false,
      "SecurityGateToEnter": 0,
      "UseStaticBioscanPointsInZone": false,
      "TurnOffAlarmOnTerminal": false,
      "TerminalPuzzleZone": {
        "LocalIndex": 0,
        "SeedType": 1,
        "TerminalIndex": 0,
        "StaticSeed": 0
      },
      "EventsOnTerminalDeactivateAlarm": [],
      "ActiveEnemyWave": {
        "HasActiveEnemyWave": false,
        "EnemyGroupInfrontOfDoor": 0,
        "EnemyGroupInArea": 0,
        "EnemyGroupsInArea": 0
      },
      "EnemySpawningInZone": [
      ],
      "EnemyRespawning": false,
      "EnemyRespawnRequireOtherZone": true,
      "EnemyRespawnRoomDistance": 2,
      "EnemyRespawnTimeInterval": 10.0,
      "EnemyRespawnCountMultiplier": 1.0,
      "HSUClustersInZone": 0,
      "CorpseClustersInZone": 0,
      "ResourceContainerClustersInZone": 0,
      "GeneratorClustersInZone": 0,
      "CorpsesInZone": 0,
      "GroundSpawnersInZone": 3,
      "HSUsInZone": 0,
      "DeconUnitsInZone": 0,
      "AllowSmallPickupsAllocation": true,
      "AllowResourceContainerAllocation": true,
      "ForceBigPickupsAllocation": true,
      "ConsumableDistributionInZone": 20,
      "BigPickupDistributionInZone": 0,
      "TerminalPlacements": [
        {
          "PlacementWeights": {
            "Start": 1000.0,
            "Middle": 0.0,
            "End": 0.0
          },
          "AreaSeedOffset": 123,
          "MarkerSeedOffset": 123,
          "LocalLogFiles": [
          ],
          "UniqueCommands": [],
          "StartingStateData": {
            "StartingState": 0,
            "AudioEventEnter": 0,
            "AudioEventExit": 0,
            "PasswordProtected": false,
            "PasswordHintText": "Password Required.",
            "GeneratePassword": false,
            "PasswordPartCount": 1,
            "ShowPasswordLength": true,
            "ShowPasswordPartPositions": false,
            "TerminalZoneSelectionDatas": []
          }
        }
      ],
      "ForbidTerminalsInZone": false,
      "PowerGeneratorPlacements": [],
      "DisinfectionStationPlacements": [],
      "HealthMulti": 0.0,
      "HealthPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "WeaponAmmoMulti": 0.0,
      "WeaponAmmoPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "ToolAmmoMulti": 0.0,
      "ToolAmmoPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "DisinfectionMulti": 0.0,
      "DisinfectionPlacement": {
        "Start": 0.0,
        "Middle": 0.0,
        "End": 0.0
      },
      "StaticSpawnDataContainers": [
      ]
    }
  ],
  "name": "Newbie guide B1 secondary",
  "internalEnabled": true,
  "persistentID": 163
}
```

Some results:

![Map with bridge and reactor](<../../.gitbook/assets/image (25).png>)

![View from bridge zone to initial zone of secondary layer](<../../.gitbook/assets/image (36).png>)

If you have your own working layout, you don't have to copy mine. Note that there are some questionable terminal placements in there.

## Objective

We've already made the objective, so we just need to apply it in rundown db and test it out. If it works, we don't have to do anything here.

Future me says it works fine. Excellent. The secondary layer is complete.

## Final test

With the nightmare fully assembled, it's time for the last test. Go beat the whole level.

I'd love to insert a full video of me clearing it with Calle QA recording in the background, game muted (except for the combat music mod playing looming dread), ~~cheats enabled~~, but I'm not gonna do that.

## Afterword

Finally done, feels like this took forever to write. Hopefully it wasn't so bad to get through as a reader. I hope you learned something, especially something about how to learn from existing examples and debug. Remember, you're not even limited to base game blocks. If you ask nicely, I'm sure most modders will let you use their blocks as examples.

I also highly recommend checking out the various different mods that expand datablock limitations.

Now if you'll excuse me, I need to go cast this abomination of a level into oblivion and then turn myself in. Good luck on your future endeavors.
