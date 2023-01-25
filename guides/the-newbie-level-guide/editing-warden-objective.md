---
description: >-
  If you're looking for a guide that explains events, you've come to the wrong
  place
---

# Editing warden objective

## Overview

Warden objectives are a core part of any level and they're quite ~~convoluted~~ complex just by themselves, especially with the new event system (that we won't look at). Our level is quite a nightmare by now but we're still not done torturing it for science. It's time to change the warden objective.

But seeing how in the next part we're adding a secondary sector, here we're going for 3 objectives:

1. Uplink terminal for main;
2. Empty (unsolvable) objective for secondary;
3. Reactor objective for secondary.

## Uplink terminal

Alright so as you might guess the zone we'll be adding this to is the zone the created, and we're looking for it to land in the 2nd terminal (further down the zone).

Funny enough we just yeeted the uplink objective with original level secondary layer, so let's steal that and steal the text info from an uplink made before localized text became a thing (because we're not looking to deal with localization right now).

{% hint style="info" %}
Remember, using existing blocks is often better than starting from 0, but be careful about which blocks you pick - some might become outdated with game updates. If you can, try to go for the current rundown.
{% endhint %}

Copying objective 117 and Header-GoToWinCondition\_ToMainLayer fields from 79 (and changing ID and name ofc), we get this:

```
{
  "Type": 8,
  "Header": "Terminal Uplink",
  "MainObjective": "Find the <u>Uplink Terminals</u> [ALL_ITEMS] and establish an external uplink from each terminal",
  "WardenObjectiveSpecialUpdateType": 0,
  "GenericItemFromStart": 0,
  "FindLocationInfo": "Gather information about the location of [ALL_ITEMS]",
  "FindLocationInfoHelp": "Access more data in the terminal maintenance system",
  "GoToZone": 0,
  "GoToZoneHelp": 0,
  "InZoneFindItem": 0,
  "InZoneFindItemHelp": 0,
  "SolveItem": "Use [ITEM_SERIAL] to create an uplink to [UPLINK_ADDRESS]",
  "SolveItemHelp": "Use the UPLINK_CONNECT command to establish the connection",
  "GoToWinCondition_Elevator": "Neural Imprinting Protocols retrieved. Return to the point of entrance in [EXTRACTION_ZONE]",
  "GoToWinConditionHelp_Elevator": "Use the navigational beacon and the floor map ([KEY_MAP]) to find the way back",
  "GoToWinCondition_CustomGeo": "Go to the forward exit point in [EXTRACTION_ZONE]",
  "GoToWinConditionHelp_CustomGeo": "Use the navigational beacon and the information in the surroundings to find the exit point",
  "GoToWinCondition_ToMainLayer": "Go back to the main objective and complete the expedition.",
  "GoToWinConditionHelp_ToMainLayer": 0,
  "ShowHelpDelay": 180.0,
  "WavesOnElevatorLand": [],
  "EventsOnElevatorLand": [],
  "WaveOnElevatorWardenIntel": 0,
  "FogTransitionDataOnElevatorLand": 0,
  "FogTransitionDurationOnElevatorLand": 0.0,
  "OnActivateOnSolveItem": false,
  "WavesOnActivate": [
    {
      "WaveSettings": 44,
      "WavePopulation": 1,
      "SpawnDelay": 0.0,
      "TriggerAlarm": true,
      "IntelMessage": 0
    }
  ],
  "EventsOnActivate": [],
  "StopAllWavesBeforeGotoWin": false,
  "WavesOnGotoWin": [],
  "WaveOnGotoWinTrigger": 0,
  "EventsOnGotoWin": [],
  "EventsOnGotoWinTrigger": 0,
  "FogTransitionDataOnGotoWin": 0,
  "FogTransitionDurationOnGotoWin": 0.0,
  "ChainedPuzzleToActive": 10,
  "ChainedPuzzleMidObjective": 0,
  "ChainedPuzzleAtExit": 11,
  "ChainedPuzzleAtExitScanSpeedMultiplier": 0.2,
  "Gather_RequiredCount": -1,
  "Gather_ItemId": 0,
  "Gather_SpawnCount": 0,
  "Gather_MaxPerZone": 0,
  "Retrieve_Items": [],
  "ReactorWaves": [],
  "LightsOnFromBeginning": false,
  "LightsOnDuringIntro": false,
  "LightsOnWhenStartupComplete": false,
  "DoNotSolveObjectiveOnReactorComplete": false,
  "SpecialTerminalCommand": "",
  "SpecialTerminalCommandDesc": "",
  "PostCommandOutput": [],
  "SpecialCommandRule": 0,
  "PowerCellsToDistribute": 0,
  "Uplink_NumberOfVerificationRounds": 4,
  "Uplink_NumberOfTerminals": 2,
  "Uplink_WaveSpawnType": 1,
  "CentralPowerGenClustser_NumberOfGenerators": 0,
  "CentralPowerGenClustser_NumberOfPowerCells": 4,
  "CentralPowerGenClustser_FogDataSteps": [],
  "ActivateHSU_ItemFromStart": 0,
  "ActivateHSU_ItemAfterActivation": 0,
  "ActivateHSU_StopEnemyWavesOnActivation": false,
  "ActivateHSU_ObjectiveCompleteAfterInsertion": false,
  "ActivateHSU_RequireItemAfterActivationInExitScan": false,
  "ActivateHSU_Events": [],
  "Survival_TimeToActivate": 0.0,
  "Survival_TimeToSurvive": 0.0,
  "Survival_TimerTitle": 0,
  "Survival_TimerToActivateTitle": 0,
  "GatherTerminal_SpawnCount": 0,
  "GatherTerminal_RequiredCount": 0,
  "GatherTerminal_Command": "",
  "GatherTerminal_CommandHelp": "",
  "GatherTerminal_DownloadingText": "",
  "GatherTerminal_DownloadCompleteText": "",
  "GatherTerminal_DownloadTime": -1.0,
  "name": "F1 Pollution main - uplink",
  "internalEnabled": true,
  "persistentID": 131
}
```

Let's go through a bit of analysis before we change it. Know that not all fields are relevant and not all fields behave the same on different objectives.

* Type is [eWardenObjectiveType](../../reference/enum-types.md#ewardenobjectivetype). Here it's 8, terminal uplink.
* The info fields are straight-forward and can be easily checked in-game. Pay attention to strings in capitals in \[] clauses, these are special values that get converted in code.
* Waves during uplinks are set to settings 44, population 1. Population is standard, settings are set to standard and special only, single wave (10000 points), 5 enemies per group and 8 seconds between groups.
* WaveOnGotoWinTrigger trigger is 0 (when objective is completed) but WavesOnGotoWin is empty, so there's no extraction alarm.
* ChainedPuzzleToActive is 10 so a team scan is required before uplink starts.
* ChainedPuzzleAtExit is 11 (always is) and speed multiplier is 0.2 (at 1.0 speed I believe it takes around 20 seconds to scan).
* Rounds per uplink is 4 and there's 2 terminals.
* Wave spawn type is 1 (InSuppliedCourseNodeZone), meaning they'll spawn in uplink zone.

The terminal picking and exit condition (elevator or exit geo) are set elsewhere, we'll look at that later.

Pretty much all of these settings are fair enough, we just need to change the uplink count to 1 and increase the exit scan speed.

Now let's configure the objective in rundown db.

![Warden objective edited](<../../.gitbook/assets/image (14) (1).png>)

Only 2 things to change here - the datablock id and the local index, the rest are already correct.

Make sure you edit the ObjectiveData inside MainLayerData.

Note that ZonePlacementDatas is a list of lists. If I recall correctly, the outer list is for different uplinks (if we had kept 2 uplinks for example), the inner list is for different locations for the same uplink (rng between runs).

The only other thing to note is WinCondition. 1 means exit geo. This field only affects info fields to my understanding, and only for the main layer. The actual exit location is always the exit geo if there is one.

{% hint style="info" %}
You can have exit geos in layers, but that means you'll always have to do that layer.

You cannot alternate between several exit geos and/or elevator in the same level.
{% endhint %}

A quick test shows that all went according to plan, just one thing was forgotten - a door towards exit was previously locked until the objective was completed. We can copy that for our uplink objective and edit the text or we can disable the lock. I'll go with the latter and set PuzzleType to 0 on zone 9.

## Empty objective

This is used for times when you don't want to deal with creating an objective but still need one (i.e. while you're still making a level) or when you have other means of completing the objective.

We're looking to make an objective as simple and universal as possible and in my experience the easiest way is a gather small items objective that spawns no items. The only thing you need to do once you have this block is set the objective ID in rundown db and you're done.

The block in question:

```
{
  "Type": 3,
  "Header": "Don't escape",
  "MainObjective": "Don't escape",
  "WardenObjectiveSpecialUpdateType": 0,
  "GenericItemFromStart": 0,
  "FindLocationInfo": "",
  "FindLocationInfoHelp": "",
  "GoToZone": 0,
  "GoToZoneHelp": 0,
  "InZoneFindItem": 0,
  "InZoneFindItemHelp": 0,
  "SolveItem": 0,
  "SolveItemHelp": 0,
  "GoToWinCondition_Elevator": "",
  "GoToWinConditionHelp_Elevator": 0,
  "GoToWinCondition_CustomGeo": "",
  "GoToWinConditionHelp_CustomGeo": 0,
  "GoToWinCondition_ToMainLayer": "",
  "GoToWinConditionHelp_ToMainLayer": 0,
  "ShowHelpDelay": 180.0,
  "WavesOnElevatorLand": [],
  "EventsOnElevatorLand": [],
  "WaveOnElevatorWardenIntel": 0,
  "FogTransitionDataOnElevatorLand": 0,
  "FogTransitionDurationOnElevatorLand": 0.0,
  "OnActivateOnSolveItem": false,
  "WavesOnActivate": [],
  "EventsOnActivate": [],
  "StopAllWavesBeforeGotoWin": false,
  "WavesOnGotoWin": [
  ],
  "WaveOnGotoWinTrigger": 1,
  "EventsOnGotoWin": [],
  "EventsOnGotoWinTrigger": 0,
  "FogTransitionDataOnGotoWin": 0,
  "FogTransitionDurationOnGotoWin": 0.0,
  "ChainedPuzzleToActive": 0,
  "ChainedPuzzleMidObjective": 0,
  "ChainedPuzzleAtExit": 11,
  "ChainedPuzzleAtExitScanSpeedMultiplier": 0.5,
  "Gather_RequiredCount": 1,
  "Gather_ItemId": 149,
  "Gather_SpawnCount": 0,
  "Gather_MaxPerZone": 1,
  "Retrieve_Items": [],
  "ReactorWaves": [],
  "LightsOnFromBeginning": false,
  "LightsOnDuringIntro": false,
  "LightsOnWhenStartupComplete": false,
  "DoNotSolveObjectiveOnReactorComplete": false,
  "SpecialTerminalCommand": "",
  "SpecialTerminalCommandDesc": "",
  "PostCommandOutput": [],
  "SpecialCommandRule": 0,
  "PowerCellsToDistribute": 0,
  "Uplink_NumberOfVerificationRounds": 0,
  "Uplink_NumberOfTerminals": 1,
  "Uplink_WaveSpawnType": 1,
  "CentralPowerGenClustser_NumberOfGenerators": 0,
  "CentralPowerGenClustser_NumberOfPowerCells": 4,
  "CentralPowerGenClustser_FogDataSteps": [],
  "ActivateHSU_ItemFromStart": 0,
  "ActivateHSU_ItemAfterActivation": 0,
  "ActivateHSU_StopEnemyWavesOnActivation": false,
  "ActivateHSU_ObjectiveCompleteAfterInsertion": false,
  "ActivateHSU_RequireItemAfterActivationInExitScan": false,
  "ActivateHSU_Events": [],
  "Survival_TimeToActivate": 0.0,
  "Survival_TimeToSurvive": 0.0,
  "Survival_TimerTitle": 0,
  "Survival_TimerToActivateTitle": 0,
  "GatherTerminal_SpawnCount": 0,
  "GatherTerminal_RequiredCount": 0,
  "GatherTerminal_Command": "",
  "GatherTerminal_CommandHelp": "",
  "GatherTerminal_DownloadingText": "",
  "GatherTerminal_DownloadCompleteText": "",
  "GatherTerminal_DownloadTime": -1.0,
  "name": "Unsolvable objective",
  "internalEnabled": true,
  "persistentID": 132
}
```

We'll try this out once we get to making the secondary sector.

## Reactor

Reminder that you shouldn't make objectives before you have the level.

Before we get into any specifics, remember that reactor is an objective heavily relying on waves. If you've read the heat explanation in the mod [ConfigurableGlobalWaveSettings](../../mods-documentation/documentation/configurableglobalwavesettings.md), you'll know there's a heat bug in base game and reactors will definitely mess with that, so you not only have to build your waves around the bug, it'll also affect the rest of the level and all other attempts until the game is restarted.

Let's steal R6D1 objective and text info from elsewhere. Reactor blocks are pretty huge thanks to each reactor wave defined separately, and this one also has a bunch of events. We'll have to analyze it in parts. Here's the whole block before editing:

```
{
  "Type": 1,
  "Header": "Reactor Startup",
  "MainObjective": "Find the main reactor for the floor and make sure it is back online.",
  "WardenObjectiveSpecialUpdateType": 0,
  "GenericItemFromStart": 0,
  "FindLocationInfo": "Gather information about the location of the Reactor",
  "FindLocationInfoHelp": 0,
  "GoToZone": "Navigate to [ITEM_ZONE] and start the Reactor",
  "GoToZoneHelp": 0,
  "InZoneFindItem": "Find the reactor control panel and initiate the startup",
  "InZoneFindItemHelp": 0,
  "SolveItem": "Make sure the Reactor is fully started before leaving",
  "SolveItemHelp": 0,
  "GoToWinCondition_Elevator": "Return to the point of entrance in [EXTRACTION_ZONE]",
  "GoToWinConditionHelp_Elevator": 0,
  "GoToWinCondition_CustomGeo": 0,
  "GoToWinConditionHelp_CustomGeo": 0,
  "GoToWinCondition_ToMainLayer": "Go back to the main objective and complete the expedition.",
  "GoToWinConditionHelp_ToMainLayer": 0,
  "ShowHelpDelay": 180.0,
  "WavesOnElevatorLand": [],
  "EventsOnElevatorLand": [
    {
      "Type": 3,
      "Trigger": 0,
      "ChainPuzzle": 0,
      "UseStaticBioscanPoints": false,
      "Layer": 0,
      "DimensionIndex": 0,
      "LocalIndex": 0,
      "Delay": 0.0,
      "Duration": 0.0,
      "ClearDimension": false,
      "WardenIntel": 0,
      "CustomSubObjectiveHeader": 0,
      "CustomSubObjective": 0,
      "SoundID": 0,
      "DialogueID": 0,
      "FogSetting": 0,
      "FogTransitionDuration": 0.0,
      "EnemyWaveData": {
        "WaveSettings": 0,
        "WavePopulation": 0,
        "SpawnDelay": 0.0,
        "TriggerAlarm": false,
        "IntelMessage": 0
      },
      "Position": {
        "x": 0.0,
        "y": 0.0,
        "z": 0.0,
        "magnitude": 0.0,
        "sqrMagnitude": 0.0
      },
      "Count": 0,
      "Enabled": false
    },
    {
      "Type": 11,
      "Trigger": 0,
      "ChainPuzzle": 0,
      "UseStaticBioscanPoints": false,
      "Layer": 0,
      "DimensionIndex": 0,
      "LocalIndex": 0,
      "Delay": 0.0,
      "Duration": 0.0,
      "ClearDimension": false,
      "WardenIntel": 1450,
      "CustomSubObjectiveHeader": 0,
      "CustomSubObjective": 1542,
      "SoundID": 0,
      "DialogueID": 0,
      "FogSetting": 0,
      "FogTransitionDuration": 0.0,
      "EnemyWaveData": {
        "WaveSettings": 0,
        "WavePopulation": 0,
        "SpawnDelay": 0.0,
        "TriggerAlarm": false,
        "IntelMessage": 0
      },
      "Position": {
        "x": 0.0,
        "y": 0.0,
        "z": 0.0,
        "magnitude": 0.0,
        "sqrMagnitude": 0.0
      },
      "Count": 0,
      "Enabled": false
    }
  ],
  "WaveOnElevatorWardenIntel": 0,
  "FogTransitionDataOnElevatorLand": 0,
  "FogTransitionDurationOnElevatorLand": 0.0,
  "OnActivateOnSolveItem": true,
  "WavesOnActivate": [],
  "EventsOnActivate": [
    {
      "Type": 2,
      "Trigger": 0,
      "ChainPuzzle": 0,
      "UseStaticBioscanPoints": false,
      "Layer": 0,
      "DimensionIndex": 0,
      "LocalIndex": 7,
      "Delay": 0.0,
      "Duration": 0.0,
      "ClearDimension": false,
      "WardenIntel": 1166,
      "CustomSubObjectiveHeader": 0,
      "CustomSubObjective": 0,
      "SoundID": 0,
      "DialogueID": 0,
      "FogSetting": 0,
      "FogTransitionDuration": 0.0,
      "EnemyWaveData": {
        "WaveSettings": 0,
        "WavePopulation": 0,
        "SpawnDelay": 0.0,
        "TriggerAlarm": false,
        "IntelMessage": 0
      },
      "Position": {
        "x": 0.0,
        "y": 0.0,
        "z": 0.0,
        "magnitude": 0.0,
        "sqrMagnitude": 0.0
      },
      "Count": 0,
      "Enabled": false
    },
    {
      "Type": 0,
      "Trigger": 0,
      "ChainPuzzle": 0,
      "UseStaticBioscanPoints": false,
      "Layer": 0,
      "DimensionIndex": 0,
      "LocalIndex": 0,
      "Delay": 0.0,
      "Duration": 0.0,
      "ClearDimension": false,
      "WardenIntel": 0,
      "CustomSubObjectiveHeader": 0,
      "CustomSubObjective": 1444,
      "SoundID": 0,
      "DialogueID": 0,
      "FogSetting": 0,
      "FogTransitionDuration": 0.0,
      "EnemyWaveData": {
        "WaveSettings": 0,
        "WavePopulation": 0,
        "SpawnDelay": 0.0,
        "TriggerAlarm": false,
        "IntelMessage": 0
      },
      "Position": {
        "x": 0.0,
        "y": 0.0,
        "z": 0.0,
        "magnitude": 0.0,
        "sqrMagnitude": 0.0
      },
      "Count": 0,
      "Enabled": false
    },
    {
      "Type": 10,
      "Trigger": 0,
      "ChainPuzzle": 0,
      "UseStaticBioscanPoints": false,
      "Layer": 0,
      "DimensionIndex": 0,
      "LocalIndex": 0,
      "Delay": 0.0,
      "Duration": 0.0,
      "ClearDimension": false,
      "WardenIntel": 0,
      "CustomSubObjectiveHeader": 0,
      "CustomSubObjective": 0,
      "SoundID": 0,
      "DialogueID": 0,
      "FogSetting": 0,
      "FogTransitionDuration": 0.0,
      "EnemyWaveData": {
        "WaveSettings": 0,
        "WavePopulation": 0,
        "SpawnDelay": 0.0,
        "TriggerAlarm": false,
        "IntelMessage": 0
      },
      "Position": {
        "x": 0.0,
        "y": 0.0,
        "z": 0.0,
        "magnitude": 0.0,
        "sqrMagnitude": 0.0
      },
      "Count": 0,
      "Enabled": false
    }
  ],
  "StopAllWavesBeforeGotoWin": false,
  "WavesOnGotoWin": [],
  "WaveOnGotoWinTrigger": 0,
  "EventsOnGotoWin": [],
  "EventsOnGotoWinTrigger": 0,
  "FogTransitionDataOnGotoWin": 0,
  "FogTransitionDurationOnGotoWin": 0.0,
  "ChainedPuzzleToActive": 10,
  "ChainedPuzzleMidObjective": 0,
  "ChainedPuzzleAtExit": 11,
  "ChainedPuzzleAtExitScanSpeedMultiplier": 2.0,
  "Gather_RequiredCount": -1,
  "Gather_ItemId": 0,
  "Gather_SpawnCount": 0,
  "Gather_MaxPerZone": 0,
  "Retrieve_Items": [],
  "ReactorWaves": [
    {
      "Warmup": 40.0,
      "WarmupFail": 20.0,
      "Wave": 80.0,
      "Verify": 60.0,
      "VerifyFail": 60.0,
      "VerifyInOtherZone": false,
      "ZoneForVerification": 0,
      "EnemyWaves": [
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.0,
          "SpawnType": 0
        },
        {
          "WaveSettings": 22,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.25,
          "SpawnType": 0
        },
        {
          "WaveSettings": 7,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.45,
          "SpawnType": 0
        },
        {
          "WaveSettings": 9,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.55,
          "SpawnType": 0
        }
      ],
      "Events": []
    },
    {
      "Warmup": 55.0,
      "WarmupFail": 20.0,
      "Wave": 90.0,
      "Verify": 60.0,
      "VerifyFail": 60.0,
      "VerifyInOtherZone": false,
      "ZoneForVerification": 0,
      "EnemyWaves": [
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.0,
          "SpawnType": 0
        },
        {
          "WaveSettings": 129,
          "WavePopulation": 35,
          "SpawnTimeRel": 0.2,
          "SpawnType": 0
        },
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.35,
          "SpawnType": 0
        },
        {
          "WaveSettings": 9,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.45,
          "SpawnType": 0
        },
        {
          "WaveSettings": 23,
          "WavePopulation": 10,
          "SpawnTimeRel": 0.65,
          "SpawnType": 0
        }
      ],
      "Events": []
    },
    {
      "Warmup": 60.0,
      "WarmupFail": 20.0,
      "Wave": 110.0,
      "Verify": 60.0,
      "VerifyFail": 60.0,
      "VerifyInOtherZone": false,
      "ZoneForVerification": 0,
      "EnemyWaves": [
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.0,
          "SpawnType": 0
        },
        {
          "WaveSettings": 22,
          "WavePopulation": 10,
          "SpawnTimeRel": 0.15,
          "SpawnType": 0
        },
        {
          "WaveSettings": 129,
          "WavePopulation": 35,
          "SpawnTimeRel": 0.25,
          "SpawnType": 0
        },
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.35,
          "SpawnType": 0
        },
        {
          "WaveSettings": 9,
          "WavePopulation": 10,
          "SpawnTimeRel": 0.5,
          "SpawnType": 0
        },
        {
          "WaveSettings": 128,
          "WavePopulation": 35,
          "SpawnTimeRel": 0.7,
          "SpawnType": 0
        }
      ],
      "Events": []
    },
    {
      "Warmup": 60.0,
      "WarmupFail": 20.0,
      "Wave": 120.0,
      "Verify": 60.0,
      "VerifyFail": 60.0,
      "VerifyInOtherZone": false,
      "ZoneForVerification": 0,
      "EnemyWaves": [
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.0,
          "SpawnType": 0
        },
        {
          "WaveSettings": 22,
          "WavePopulation": 10,
          "SpawnTimeRel": 0.1,
          "SpawnType": 0
        },
        {
          "WaveSettings": 129,
          "WavePopulation": 35,
          "SpawnTimeRel": 0.35,
          "SpawnType": 0
        },
        {
          "WaveSettings": 23,
          "WavePopulation": 10,
          "SpawnTimeRel": 0.4,
          "SpawnType": 0
        },
        {
          "WaveSettings": 128,
          "WavePopulation": 35,
          "SpawnTimeRel": 0.75,
          "SpawnType": 0
        },
        {
          "WaveSettings": 30,
          "WavePopulation": 16,
          "SpawnTimeRel": 0.95,
          "SpawnType": 0
        }
      ],
      "Events": [
        {
          "Type": 5,
          "Trigger": 1,
          "ChainPuzzle": 0,
          "UseStaticBioscanPoints": false,
          "Layer": 0,
          "DimensionIndex": 0,
          "LocalIndex": 6,
          "Delay": 171.0,
          "Duration": 0.0,
          "ClearDimension": false,
          "WardenIntel": 0,
          "CustomSubObjectiveHeader": 0,
          "CustomSubObjective": 0,
          "SoundID": 2134610730,
          "DialogueID": 0,
          "FogSetting": 0,
          "FogTransitionDuration": 0.0,
          "EnemyWaveData": {
            "WaveSettings": 0,
            "WavePopulation": 0,
            "SpawnDelay": 0.0,
            "TriggerAlarm": false,
            "IntelMessage": 0
          },
          "Position": {
            "x": 0.0,
            "y": 0.0,
            "z": 0.0,
            "magnitude": 0.0,
            "sqrMagnitude": 0.0
          },
          "Count": 0,
          "Enabled": false
        }
      ]
    }
  ],
  "LightsOnFromBeginning": false,
  "LightsOnDuringIntro": false,
  "LightsOnWhenStartupComplete": true,
  "DoNotSolveObjectiveOnReactorComplete": true,
  "SpecialTerminalCommand": "",
  "SpecialTerminalCommandDesc": "",
  "PostCommandOutput": [],
  "SpecialCommandRule": 0,
  "PowerCellsToDistribute": 0,
  "Uplink_NumberOfVerificationRounds": 0,
  "Uplink_NumberOfTerminals": 1,
  "Uplink_WaveSpawnType": 1,
  "CentralPowerGenClustser_NumberOfGenerators": 0,
  "CentralPowerGenClustser_NumberOfPowerCells": 4,
  "CentralPowerGenClustser_FogDataSteps": [],
  "ActivateHSU_ItemFromStart": 0,
  "ActivateHSU_ItemAfterActivation": 0,
  "ActivateHSU_StopEnemyWavesOnActivation": false,
  "ActivateHSU_ObjectiveCompleteAfterInsertion": false,
  "ActivateHSU_RequireItemAfterActivationInExitScan": false,
  "ActivateHSU_Events": [],
  "Survival_TimeToActivate": 0.0,
  "Survival_TimeToSurvive": 0.0,
  "Survival_TimerTitle": 0,
  "Survival_TimerToActivateTitle": 0,
  "GatherTerminal_SpawnCount": 0,
  "GatherTerminal_RequiredCount": 0,
  "GatherTerminal_Command": "",
  "GatherTerminal_CommandHelp": "",
  "GatherTerminal_DownloadingText": "",
  "GatherTerminal_DownloadCompleteText": "",
  "GatherTerminal_DownloadTime": -1.0,
  "name": "F1 Pollution secondary - reactor",
  "internalEnabled": true,
  "persistentID": 133
}
```

Reactor objective type is 1; text fields are self-explanatory so we'll skip them.

Immediately on landing (EventsOnElevatorLand) we have 2 events, the first turns the lights off and the second adds a subobjective. We don't need either so we'll remove those events.

Then we have EventsOnActivate, I believe run upon completing the scan after inputting the startup command. Weirdly enough only one event seems relevant here - turning the lights on. The others don't seem like they would do anything - the 2nd event is type 0 (none) and the last is type 10 (StopEnemyWaves) but there are no waves to stop as far as I know. Maybe I misremember, or maybe there have been some changes to the level during development and they didn't get cleaned up properly. Either way we need none of these so we'll remove them as well.

Since we're on events, let's check the last remaining event in this block as well - "Events" under the 4th reactor wave. Usually the zone-unlock events for verification would be here, but R6D1 doesn't do that. Here we have one event - type 5 with trigger 1 - sound on start, with a timed delay. Looks like this is the tank spawn roar. We're removing it.

One last thing before we look at reactor waves - DoNotSolveObjectiveOnReactorComplete. This is used to make R6D1 seem like it's a terminal command objective when it's actually a reactor. Set this to false so the objective is completed after reactor.

Alright, reactor waves it is. Here's the first block:

```
    {
      "Warmup": 40.0,
      "WarmupFail": 20.0,
      "Wave": 80.0,
      "Verify": 60.0,
      "VerifyFail": 60.0,
      "VerifyInOtherZone": false,
      "ZoneForVerification": 0,
      "EnemyWaves": [
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.0,
          "SpawnType": 0
        },
        {
          "WaveSettings": 22,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.25,
          "SpawnType": 0
        },
        {
          "WaveSettings": 7,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.45,
          "SpawnType": 0
        },
        {
          "WaveSettings": 9,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.55,
          "SpawnType": 0
        }
      ],
      "Events": []
    },
```

The first settings are all about time. Time for warmup, wave, and verify phases, as well as for repeat phases marked as "fail".

VerifyInOtherZone determines if you get the code on HUD or if you have to find it on a terminal. ZoneForVerification is the local index of the zone to place the code in. No placement data here, which means we don't get to choose weights.

There's 4 waves total here - settings, population, and spawn type are all familiar at this point. The only thing new is "SpawnTimeRel" - when to start spawning the wave. Say, 0.55 would result in 80 \* 0.55 = at 44 seconds into the wave. Remember that settings can delay spawn, groups don't all spawn instantly, spawn cap exists etc. so you have to be careful about not overdoing the waves, otherwise people will have to fight through the verify time.

I won't dive deep into the settings and population. I can guess that they'll mostly be very specific in spawn timing, enemies, and especially population points.

The other 3 blocks are the exact same thing, just different numbers, so there's no need to analyze them for me. This is all up to level design and balancing, and we don't do that here. I'll delete the 4th wave and leave everything as-is.

Here's the final block:

```
{
  "Type": 1,
  "Header": "Reactor Startup",
  "MainObjective": "Find the main reactor for the floor and make sure it is back online.",
  "WardenObjectiveSpecialUpdateType": 0,
  "GenericItemFromStart": 0,
  "FindLocationInfo": "Gather information about the location of the Reactor",
  "FindLocationInfoHelp": 0,
  "GoToZone": "Navigate to [ITEM_ZONE] and start the Reactor",
  "GoToZoneHelp": 0,
  "InZoneFindItem": "Find the reactor control panel and initiate the startup",
  "InZoneFindItemHelp": 0,
  "SolveItem": "Make sure the Reactor is fully started before leaving",
  "SolveItemHelp": 0,
  "GoToWinCondition_Elevator": "Return to the point of entrance in [EXTRACTION_ZONE]",
  "GoToWinConditionHelp_Elevator": 0,
  "GoToWinCondition_CustomGeo": 0,
  "GoToWinConditionHelp_CustomGeo": 0,
  "GoToWinCondition_ToMainLayer": "Go back to the main objective and complete the expedition.",
  "GoToWinConditionHelp_ToMainLayer": 0,
  "ShowHelpDelay": 180.0,
  "WavesOnElevatorLand": [],
  "EventsOnElevatorLand": [
  ],
  "WaveOnElevatorWardenIntel": 0,
  "FogTransitionDataOnElevatorLand": 0,
  "FogTransitionDurationOnElevatorLand": 0.0,
  "OnActivateOnSolveItem": true,
  "WavesOnActivate": [],
  "EventsOnActivate": [
  ],
  "StopAllWavesBeforeGotoWin": false,
  "WavesOnGotoWin": [],
  "WaveOnGotoWinTrigger": 0,
  "EventsOnGotoWin": [],
  "EventsOnGotoWinTrigger": 0,
  "FogTransitionDataOnGotoWin": 0,
  "FogTransitionDurationOnGotoWin": 0.0,
  "ChainedPuzzleToActive": 10,
  "ChainedPuzzleMidObjective": 0,
  "ChainedPuzzleAtExit": 11,
  "ChainedPuzzleAtExitScanSpeedMultiplier": 2.0,
  "Gather_RequiredCount": -1,
  "Gather_ItemId": 0,
  "Gather_SpawnCount": 0,
  "Gather_MaxPerZone": 0,
  "Retrieve_Items": [],
  "ReactorWaves": [
    {
      "Warmup": 40.0,
      "WarmupFail": 20.0,
      "Wave": 80.0,
      "Verify": 60.0,
      "VerifyFail": 60.0,
      "VerifyInOtherZone": false,
      "ZoneForVerification": 0,
      "EnemyWaves": [
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.0,
          "SpawnType": 0
        },
        {
          "WaveSettings": 22,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.25,
          "SpawnType": 0
        },
        {
          "WaveSettings": 7,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.45,
          "SpawnType": 0
        },
        {
          "WaveSettings": 9,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.55,
          "SpawnType": 0
        }
      ],
      "Events": []
    },
    {
      "Warmup": 55.0,
      "WarmupFail": 20.0,
      "Wave": 90.0,
      "Verify": 60.0,
      "VerifyFail": 60.0,
      "VerifyInOtherZone": false,
      "ZoneForVerification": 0,
      "EnemyWaves": [
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.0,
          "SpawnType": 0
        },
        {
          "WaveSettings": 129,
          "WavePopulation": 35,
          "SpawnTimeRel": 0.2,
          "SpawnType": 0
        },
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.35,
          "SpawnType": 0
        },
        {
          "WaveSettings": 9,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.45,
          "SpawnType": 0
        },
        {
          "WaveSettings": 23,
          "WavePopulation": 10,
          "SpawnTimeRel": 0.65,
          "SpawnType": 0
        }
      ],
      "Events": []
    },
    {
      "Warmup": 60.0,
      "WarmupFail": 20.0,
      "Wave": 110.0,
      "Verify": 60.0,
      "VerifyFail": 60.0,
      "VerifyInOtherZone": false,
      "ZoneForVerification": 0,
      "EnemyWaves": [
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.0,
          "SpawnType": 0
        },
        {
          "WaveSettings": 22,
          "WavePopulation": 10,
          "SpawnTimeRel": 0.15,
          "SpawnType": 0
        },
        {
          "WaveSettings": 129,
          "WavePopulation": 35,
          "SpawnTimeRel": 0.25,
          "SpawnType": 0
        },
        {
          "WaveSettings": 23,
          "WavePopulation": 6,
          "SpawnTimeRel": 0.35,
          "SpawnType": 0
        },
        {
          "WaveSettings": 9,
          "WavePopulation": 10,
          "SpawnTimeRel": 0.5,
          "SpawnType": 0
        },
        {
          "WaveSettings": 128,
          "WavePopulation": 35,
          "SpawnTimeRel": 0.7,
          "SpawnType": 0
        }
      ],
      "Events": []
    }
  ],
  "LightsOnFromBeginning": false,
  "LightsOnDuringIntro": false,
  "LightsOnWhenStartupComplete": true,
  "DoNotSolveObjectiveOnReactorComplete": false,
  "SpecialTerminalCommand": "",
  "SpecialTerminalCommandDesc": "",
  "PostCommandOutput": [],
  "SpecialCommandRule": 0,
  "PowerCellsToDistribute": 0,
  "Uplink_NumberOfVerificationRounds": 0,
  "Uplink_NumberOfTerminals": 1,
  "Uplink_WaveSpawnType": 1,
  "CentralPowerGenClustser_NumberOfGenerators": 0,
  "CentralPowerGenClustser_NumberOfPowerCells": 4,
  "CentralPowerGenClustser_FogDataSteps": [],
  "ActivateHSU_ItemFromStart": 0,
  "ActivateHSU_ItemAfterActivation": 0,
  "ActivateHSU_StopEnemyWavesOnActivation": false,
  "ActivateHSU_ObjectiveCompleteAfterInsertion": false,
  "ActivateHSU_RequireItemAfterActivationInExitScan": false,
  "ActivateHSU_Events": [],
  "Survival_TimeToActivate": 0.0,
  "Survival_TimeToSurvive": 0.0,
  "Survival_TimerTitle": 0,
  "Survival_TimerToActivateTitle": 0,
  "GatherTerminal_SpawnCount": 0,
  "GatherTerminal_RequiredCount": 0,
  "GatherTerminal_Command": "",
  "GatherTerminal_CommandHelp": "",
  "GatherTerminal_DownloadingText": "",
  "GatherTerminal_DownloadCompleteText": "",
  "GatherTerminal_DownloadTime": -1.0,
  "name": "F1 Pollution secondary - reactor",
  "internalEnabled": true,
  "persistentID": 133
}
```

Time to finish this.
