---
description: GameData_WardenObjectiveDataBlock_bin.json
---

# WardenObjectiveDataBlock

No description provided.

***

## Fields

### Type - [eWardenObjectiveType](../../enum-types.md#ewardenobjectivetype) (enum)

No description provided.

### Header - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### MainObjective - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### WardenObjectiveSpecialUpdateType - [eWardenObjectiveSpecialUpdateType](../../enum-types.md#ewardenobjectivespecialupdatetype) (enum)

No description provided.

### GenericItemFromStart - UInt32 ([ItemDataBlock](../main/item.md))

No description provided.

### FindLocationInfo - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### FindLocationInfoHelp - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GoToZone - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GoToZoneHelp - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### InZoneFindItem - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### InZoneFindItemHelp - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### SolveItem - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### SolveItemHelp - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GoToWinCondition_Elevator - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GoToWinConditionHelp_Elevator - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GoToWinCondition_CustomGeo - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GoToWinConditionHelp_CustomGeo - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GoToWinCondition_ToMainLayer - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GoToWinConditionHelp_ToMainLayer - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### ShowHelpDelay - Single

No description provided.

### WavesOnElevatorLand - [List GenericEnemyWaveData](../../nested-types/genericenemywavedata.md) (nested type)

No description provided.

### EventsOnElevatorLand - [List WardenObjectiveEventData](../../nested-types/wardenobjectiveeventdata.md) (nested type)

No description provided.

### WaveOnElevatorWardenIntel - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### FogTransitionDataOnElevatorLand - UInt32 ([FogSettingsDataBlock](../main/fogsettings.md))

No description provided.

### FogTransitionDurationOnElevatorLand - Single

No description provided.

### OnActivateOnSolveItem - Boolean

No description provided.

### WavesOnActivate - [List GenericEnemyWaveData](../../nested-types/genericenemywavedata.md) (nested type)

No description provided.

### EventsOnActivate - [List WardenObjectiveEventData](../../nested-types/wardenobjectiveeventdata.md) (nested type)

No description provided.

### StopAllWavesBeforeGotoWin - Boolean

No description provided.

### WavesOnGotoWin - [List GenericEnemyWaveData](../../nested-types/genericenemywavedata.md) (nested type)

No description provided.

### WaveOnGotoWinTrigger - [eRetrieveExitWaveTrigger](../../enum-types.md#eretrieveexitwavetrigger) (enum)

No description provided.

### EventsOnGotoWin - [List WardenObjectiveEventData](../../nested-types/wardenobjectiveeventdata.md) (nested type)

No description provided.

### EventsOnGotoWinTrigger - [eRetrieveExitWaveTrigger](../../enum-types.md#eretrieveexitwavetrigger) (enum)

No description provided.

### FogTransitionDataOnGotoWin - UInt32 ([FogSettingsDataBlock](../main/fogsettings.md))

No description provided.

### FogTransitionDurationOnGotoWin - Single

No description provided.

### ChainedPuzzleToActive - UInt32 ([ChainedPuzzleDataBlock](../main/chainedpuzzle.md))

No description provided.

### ChainedPuzzleMidObjective - UInt32 ([ChainedPuzzleDataBlock](../main/chainedpuzzle.md))

No description provided.

### ChainedPuzzleAtExit - UInt32 ([ChainedPuzzleDataBlock](../main/chainedpuzzle.md))

No description provided.

### ChainedPuzzleAtExitScanSpeedMultiplier - Single

No description provided.

### Gather_RequiredCount - Int32

No description provided.

### Gather_ItemId - UInt32 ([ItemDataBlock](../main/item.md))

No description provided.

### Gather_SpawnCount - Int32

No description provided.

### Gather_MaxPerZone - Int32

No description provided.

### Retrieve_Items - List UInt32 ([ItemDataBlock](../main/item.md))

No description provided.

### ReactorWaves - [List ReactorWaveData](../../nested-types/reactorwavedata.md) (nested type)

No description provided.

### LightsOnFromBeginning - Boolean

No description provided.

### LightsOnDuringIntro - Boolean

No description provided.

### LightsOnWhenStartupComplete - Boolean

No description provided.

### DoNotSolveObjectiveOnReactorComplete - Boolean

No description provided.

### SpecialTerminalCommand - String

No description provided.

### SpecialTerminalCommandDesc - String

No description provided.

### PostCommandOutput - List String

No description provided.

### SpecialCommandRule - [TERM_CommandRule](../../enum-types.md#term_commandrule) (enum)

No description provided.

### PowerCellsToDistribute - Int32

No description provided.

### Uplink_NumberOfVerificationRounds - Int32

No description provided.

### Uplink_NumberOfTerminals - Int32

No description provided.

### Uplink_WaveSpawnType - [SurvivalWaveSpawnType](../../enum-types.md#survivalwavespawntype) (enum)

No description provided.

### CentralPowerGenClustser_NumberOfGenerators - Int32

No description provided.

### CentralPowerGenClustser_NumberOfPowerCells - Int32

No description provided.

### CentralPowerGenClustser_FogDataSteps - [List GeneralFogDataStep](../../nested-types/generalfogdatastep.md) (nested type)

No description provided.

### ActivateHSU_ItemFromStart - UInt32 ([ItemDataBlock](../main/item.md))

No description provided.

### ActivateHSU_ItemAfterActivation - UInt32 ([ItemDataBlock](../main/item.md))

No description provided.

### ActivateHSU_StopEnemyWavesOnActivation - Boolean

No description provided.

### ActivateHSU_ObjectiveCompleteAfterInsertion - Boolean

No description provided.

### ActivateHSU_RequireItemAfterActivationInExitScan - Boolean

No description provided.

### ActivateHSU_Events - [List WardenObjectiveEventData](../../nested-types/wardenobjectiveeventdata.md) (nested type)

No description provided.

### Survival_TimeToActivate - Single

No description provided.

### Survival_TimeToSurvive - Single

No description provided.

### Survival_TimerTitle - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### Survival_TimerToActivateTitle - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

No description provided.

### GatherTerminal_SpawnCount - Int32

No description provided.

### GatherTerminal_RequiredCount - Int32

No description provided.

### GatherTerminal_Command - String

No description provided.

### GatherTerminal_CommandHelp - String

No description provided.

### GatherTerminal_DownloadingText - String

No description provided.

### GatherTerminal_DownloadCompleteText - String

No description provided.

### GatherTerminal_DownloadTime - Single

No description provided.
