---
description: GameData_WardenObjectiveDataBlock_bin.json (filled)
---

# WardenObjective

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

## Additional docs

All expeditions require at least 1 Warden Objective (for Main specifically), which determines if the objective for the level (or one of the layers within the level) is Reactor Startup, Central Generator Cluster and all that.

To begin with, you can find any of the DBs in `GameData_WardenObjectiveDatablock.json` as your base reference.

At first glance it looks quite intimidating, right? Don’t worry. Let’s do some categorizations and split those fields up. To make it more succinct, I will use one of the datablock copy-pasted from `GameData_WardenObjectiveDatablock.json`, but remove some redundant parts and add some comments where necessary.

### General fields

```json
// The following are common fields used by all objective types.
// Enum that determines what type of the objective is. 
// All objective types are listed above. 
"Type": 6,

// Probably a useless field :)
"Header": "Retrieve Essential Items", 

// Text that describes the objective. Here it’s simply a string, but for most WardenObjective in Rundown 6 it is reference to DB in TextDatablock. 
"MainObjective": "Find the reactor for the floor and make sure it is back online.", 

// Not quite sure… awaiting supplements :)
"WardenObjectiveSpecialUpdateType": 0,

// The following fields are all Text fields 
// that work analogously as "MainObjective".
"FindLocationInfo": 0, 
"FindLocationInfoHelp": 0, 
"GoToZone": 0,
"GoToZoneHelp": 0,
"InZoneFindItem": 0,
"InZoneFindItemHelp": 0,
"SolveItem": 0,
"SolveItemHelp": 0,

// The following Text fields will be displayed upon objective completion. 
// Fields ending with "_Elevator" and "_CustomGeo" are 
// typically  used by Main Objective. If you make the 
// extraction point in the elevator zone, the former ones 
// will be applied, otherwise (implying that you 
// are using forward exit) the latter ones.
// Fields ending with "_ToMainLayer" are typically 
// used by Secondary or Overload. 
// However, for the case of forward exit being set 
// in either Secondary or Overload, 
// I’m not pretty sure… awaiting supplements :)
"GoToWinCondition_Elevator": 0,
"GoToWinConditionHelp_Elevator": 0,
"GoToWinCondition_CustomGeo": 0,
"GoToWinConditionHelp_CustomGeo": 0,
"GoToWinCondition_ToMainLayer": 0,
"GoToWinConditionHelp_ToMainLayer": 0,
"ShowHelpDelay": 180.0,
```

### Waves / Events / Fog / Chained Puzzle fields

These fields tells the objective manager to spawn enemy waves and execute events at given point.

#### On Elevator Land

Literally on elevator land (upon cage drop). The fields are all self-clarifying.

```json
"WavesOnElevatorLand": [],
"WaveOnElevatorWardenIntel": 0,
"EventsOnElevatorLand": [],

// Firstly used in R4E1, which combos with Tank Error Alarm. 
// This 2 fields could be easily replaced 
// by a "SetFogSettings" Event in "EventsOnElevatorLand"
"FogTransitionDataOnElevatorLand": 0,
"FogTransitionDurationOnElevatorLand": 0.0, 
```

#### On Activate

At first glance it's rather perplexing that what is "On Activate". Sadly, I have no idea how to describe it clearly ; )

For now, you may refer to its usage in different objective type get some hints. "WavesOnActivate" and "EventsOnActivate" are not used as frequently as "WavesOnGotoWin" and "EventsOnGotoWin"; in addition, the first part, which is the explanation for field "OnActivateOnSolveItem", is quite long.  So if you feel hard to understand this part, I suggest you skip this part and read "On Goto Win" first

```json
// The following explanation is copy-pasted from @FlowAria's message in 
// channel "modding-general". I'll do some extension basing on this.
//
// OnActivateOnSolveItem tells ObjectiveManager to trigger EventsOnActivate 
// for each objective item "solved", this include:
// 1. Picking up Objective gather item (Once for each) 
// 2. Retrieve Item (Once for each, have some checkpoint bug)
// 3. Input gather terminal command (Could be triggered as you want per single terminal, buggy)
// 4. Plug powercell to objective generator (Generator Distribution / Generator Cluster)
// 5. Established Uplink (per each terminals)
// 6. Collected DNA from HSU
// 7. Fully finish generator cluster
// 8. Fully startup/shutdown reactor
// 9. Finished Special command objective terminal 
// 
// The followings are my opinions, feel free to correct them if they are wrong.
// -> Considering 4. and 7., you could find that "OnActivateOnSolveItem"
//    works awkwardly on Generator-Cluster. 
//    To my knowledge, Modulation C3 Secondary has taken this into good use, 
//    you may use that as an example.
// -> For 8., by setting the field below "DoNotSolveObjectiveOnReactorComplete",
//    to "false", it is possible that you set multiple Reactors all in the same 
//    layer of the level and trigger different sequences of events upon
//    finishing each startup/shutdown, and finally use 
//    a "ForceWin" event to complete the layer.
"OnActivateOnSolveItem": false,

// "WavesOnActivate" is only used by several objective types. 
// -> Terminal Uplink / Corrupted Uplink 
//    (spawn enemy wave on uplink establishment 
//     and end them on verifications complete)
// -> Special terminal commands 
//    (after the activation scan, spawn enemy waves at given points.)
// -> Survival 
//    (spawn enemy waves at given points.)
// -> Activate HSU 
//    (not sure)
"WavesOnActivate": [],

// If "OnActivateOnSolveItem" is set to "true", refer to the doc above.
// Otherwise, refer to the following.
// "EventsOnActivate" is only used by several objective types.
// -> Special terminal commands 
//    (after the activation scan, execute events at given points.)
// -> Survival 
//    (execute events at given points.)
"EventsOnActivate": [],

// R5B3 Main and R5C2 Overload are good examples for good 
// use of "WavesOnActivate" and "EventsOnActivate"
```

#### On Goto Win

By "Goto Win", it means objective completion.

```json
// Stop all waves upon objective completion.
// This can be replaced by a "StopEnemyWave" event 
// in "EventsOnGotoWin"
"StopAllWavesBeforeGotoWin": false,

// For "WaveOnGotoWinTrigger" and "EventsOnGotoWinTrigger",
// they are both enum that acceot the following 2 values. 
// 0 - OnObjectiveCompleted,
// 1 - WhenExitScanMakesProgress
// Note: I'm not sure if "EventsOnGotoWinTrigger" works properly. 
//       Awaiting confirmation :) 
"WavesOnGotoWin": [],
"WaveOnGotoWinTrigger": 0,
"EventsOnGotoWin": [],
"EventsOnGotoWinTrigger": 0,

// Set Fog transition upon objective completion. 
// This can be replaced by a "SetFogSetting" event in "EventsOnGotoWin"
"FogTransitionDataOnGotoWin": 0,
"FogTransitionDurationOnGotoWin": 0.0,
```

### Objective Chained Puzzle

```json
// Used by: 
// -> HSU_CollectDNASample 
// -> Reactor Startup/Shutdown (to initiate their verification sequences)
// -> Special Terminal Command 
// -> Terminal Uplink (after CONNECT, before VERIFY)
// This chained puzzle is usually a Security Scan without alarm,
// but of course, you can make it an alarm if you want :)
"ChainedPuzzleToActive": 0, // typical value: 4, 10

// Used by CentralGeneratorCluster, ReactorShutdown and SpecialTerminalCommand
// This is the chained puzzle the team would be required to complete
// after plugging in all powercell / input shutdown verification code / input special terminal command 
"ChainedPuzzleMidObjective": 0,   

// Extraction scan. If the objective you are editing is 
// not a Main layer objective, and does not require retrieving Big Pickup Item(s)  
// to the extraction scan, feel free to left this field unchanged.
"ChainedPuzzleAtExit": 11, // typical value: 11.

// All vanilla levels use the same extraction scan puzzle.
// So changing the multiplier below could 
// change the extraction scan speed for different levels.
"ChainedPuzzleAtExitScanSpeedMultiplier": 1.0,
```

### Objective-specific fields

The following fields are all Objective Specific. You can remove those irrelevant fields given your objective type.

Some objective types don't have their own objective-specific fields.

Some may require you to spawn certain item(s) in certain zone(s) in `LevelLayoutDatablock` to make the objective work properly.

#### **3 - Gather Small Item**

Objective Type for R6C1 and R6D4.

```json
// Gather Small Item
"Gather_RequiredCount": -1,
// reference to ItemDataBlock
"Gather_ItemId": 133, 
"Gather_SpawnCount": 0,
"Gather_MaxPerZone": 0,
```

#### **6 - Retrieve Big Item**

Objective Type for R6A1 and R6C2 Secondary.

Note: for zones that spawn those Big Pickup Items (no matter if they are objective item or not), don't forget to set `"BigPickupDistribution"` in `LevelLayoutDatablock` to "true"

```json
// Retrieve Big Item 
"Retrieve_Items": [ 
  // references to ItemDatablock. 
  133,
  133
],
```

#### **1/2 - Reactor Startup/Shutdown**

Geomorph-tied objective type. To make a Reactor Startup / Shutdown work properly, you must set certain geomorph in the level.

Here's a list of the name of Reactor geomorph (use Ctrl + F in the doc '_**All Geomorph**_' to see what they look like):

* **Mining Reactor Open HA 1**\
  ****"Assets/AssetPrefabs/Complex/Mining/Geomorphs/geo\_64x64\_mining\_reactor\_open\_HA\_01.prefab"
* **Mining Reactor HA 2**\
  ****"Assets/AssetPrefabs/Complex/Mining/Geomorphs/geo\_64x64\_mining\_reactor\_HA\_02.prefab"
* **Lab Reactor HA 1**\
  ****"Assets/AssetPrefabs/Complex/Tech/Geomorphs/geo\_64x64\_lab\_reactor\_HA\_01.prefab"
* **Lab Reactor HA 2**\
  ****"Assets/AssetPrefabs/Complex/Tech/Geomorphs/geo\_64x64\_lab\_reactor\_HA\_02.prefab"

Note: For Reactor Shutdown, you can only use the **Mining Reactor HA 2** as your Reactor Geomorph. Without aid of a plugin, Reactor Shutdown would be broken if using the other 3 geomorphs.

Finally, there's no Floodway Reactor so far.

```json
// -------------------------------------
// Reactor Startup/Shutdown

// Note that if it is Reactor Shutdown, you need to 
// leave at least 1 empty wave data in "ReactorWaves" to make the objective 
// work properly (otherwise there will be 
// no verification code for the shutdown)

// Probably the most complicated, long field. 
// Used by both Reactor Startup and Shutdown.
// For Reactor Shutdown, it's used only for verification code generation.
// This field serves mostly for Reactor Startup.
"ReactorWaves": [
// Array of wave information.
// For conciseness, the example here only contains 1 wave. 
// To create multiple waves, copy-pasted the first wave and edit 
// the fields as needed. 

{ // 1st reactor wave.
    "Warmup": 30.0,        // First Warmup time
    "WarmupFail": 30.0,    // Warmup time if last wave faild to verify
    "Wave": 120.0,         // Defense time
    "Verify": 285.0,       // First Verify time
    "VerifyFail": 60.0,    // Verify time if last wave faild to verify
    
    // Is the code put in other zone? 
    // If set to true, don't forget to spawn a terminal / terminals 
    // in the corresponding zone.
    // 
    // If set to false, the code will be given on the HUD.
    "VerifyInOtherZone": true,
    
    // Works only when "VerifyInOtherZone" is set to true.
    // Specifies the zone to put the code.
    // One of the terminals in the zone will be selected (randomly).
    "ZoneForVerification": 13,
    
    // Defense Wave.
    "EnemyWaves": [
        {
            "WaveSettings": 23,     // reference to SurvivalWaveSettings
                                    // Search the word "Reactor" in SurvivalWaveSettings,
                                    // there are already some wave settings written by 10cc,
                                    // take them into good use.
                                    
            "WavePopulation": 6,    // reference to SurvivalWavePopulation
            
            "SpawnTimeRel": 0.0,    // Spawn time relative.
                                    // The exact spawn time = SpawnTimeRel * Wave
                                       
            "SpawnType": 1        // Enums. 
                                  // 0 - ClosestToReactorNoPlayerBetween
                                  // 1 - InElevatorZone
                                  
                                  // Note: This spawn type can be overriden
                                  // by m_overrideWaveSpawnType in SurvivalWaveSettings.
                                  // This is how flyers are spawned in R6D1 reactor
        }
    ],
    "Events": [
       // For reactor wave events,
       // "Trigger" plays a role in "when to execute this event".
       // It is an enum that accepts the following values:
       // 0 - None
       // 1 - OnStart
       // 2 - OnMid
       // 3 - OnEnd
       // Use the below one as an example, 
       // and don't miss the comments after "Trigger"
        {
            "Trigger": 1, // Executed before wave defense
            "Type": 2,
            "Layer": 0,
            "LocalIndex": 13,
            "Delay": 5.0,
            "WardenIntel": 1369, //"Door to [ZONE_13] unlocked by startup sequence.",
        },
        {
            "Trigger": 2, // Executed after wave defense 
            "Type": 11,
            "Layer": 0,
            "Delay": 12.0,
            "WardenIntel": 1370, //"Auxiliary temrinal located in [ZONE_13]",
            "CustomSubObjectiveHeader": 0,
            "CustomSubObjective": 99999 // "Find the verification code in [ZONE_13]"
        },
        {  
            "Trigger": 3, // Executed after verification for this wave completed.   
            "Type": 11,
            "Layer": 0,
            "LocalIndex": 0,
            "Delay": 0.0,
            "WardenIntel": 0,
            "CustomSubObjectiveHeader": 0,
            "CustomSubObjective": 0
        }
        // Note: For Trigger OnEnd (3) reactor wave events, 
        // They are only executed on host side, which means:
        // It works fine. But, on client side, the Warden Intel
        // for the events won't be displayed. 
    ]
}, // First reactor wave ended
{
// the second reactor wave
},
{
// the third reactor wave
},
// etc...
],

// Determine if the Light is all on upon cage drop. 
// To my knowledge this field is broken in R6 
// - You need to add a “AllLightsOff” 
// in "EventsOnElevatorLand" to make it work as expected
"LightsOnFromBeginning": false, 

// Determine if the Light is all on during 
// when the current wave is in warm-up phase
"LightsOnDuringIntro": false,

// Determine if the Light is all on after startup complete
// when the current wave is in warm-up phase
"LightsOnWhenStartupComplete": false,

// If set to true, the Reactor Startup / Shutdown objective 
// will be deemed un-completed after Startup/Shutdown completed.
// You need to use a ForceObjectiveComplete event
// somewhere in the expedition.
// In Vanilla this field is only used in R6D1, 
// in which the ForceObjectiveComplete event 
// is executed upon boss death
// On the other hand, with "OnActivateOnSolveItem" set to true, 
// you can use "EventsOnActivate" in place of "EventsOnGotoWin"
// Probably you can use this field to create a expedition 
// in which you need to initiate multiple Startup/Shutdown sequences :)
"DoNotSolveObjectiveOnReactorComplete": true, 
```

#### **5 - Special Terminal Command**

The most phenomenal use of this objective type is probably R5C2 Overload, in which "WavesOnActivate", "EventsOnActivate", "ChainedPuzzleMidObjective" are all well used.

Also R5B3 Secondary (or Extreme) is an example for how to use this objective type.

```json
// Special Terminal Command
// Surpassed by terminal "UniqueCommands" 
// Awaiting supplements :)
"SpecialTerminalCommand": "",
"SpecialTerminalCommandDesc": "",
"PostCommandOutput": [],
"SpecialCommandRule": 0,
```

#### **7 - Distribute Powercell**

R6C2 Main Objective.

Note:

1. If you are using this objective type as your Main Layer objective, \
   the required number of powercells will be given in the elevator cargo container.
2. Otherwise (you are using it as your Secondary/Overload objective),\
   the powercells will spawn in the first zone of the layer.\
   Don't forget to set those zones' `"ForceBigpickupDistribution"` to `"true"`
3. If you don't want the powercell to be given in the elevator cargo, you will need the help of `Tweaker`,  a plugin that enables you to manipulate your elevator cargo.

In addition, you need to spawn the required number of `PowerGenerator`(s) in  `LevelLayoutDatablock` in the desired zone(s). The objective manager would choose one of the unselected `PowerGenerator`(s) spawned in the zone as the objective generator.

```json
// The number of powercell to distribute..
"PowerCellsToDistribute": 0,
```

#### **8/13 - Terminal Uplink / Corrupted Uplink**

R6B2 Secondary / R6D2 Secondary

To use this objective types, you need to spawn required number of terminals for each uplink in `LevelLayoutDatablock`.

Also, for Corrupted Uplink, sadly, for each Uplink, you CAN'T spawn the 2 terminals for the uplink in 2 different zone.

```json
"Uplink_NumberOfVerificationRounds": 0,
"Uplink_NumberOfTerminals": 1,

// Enum that determine wave spawn type.
// Not sure how this field works, 
// To my knowledge: 
// 0 - In the nearby zone (like most sec-door alarm)
// 1 - In the current zone 
//     (which means the current zone should contain 
//      multiple rooms (areas) to make the enemies spawn as expected)
// 
// -> Not sure if the spawn type can be override 
//    by "m_overrideWaveSpawnType" in SurvivalWaveSettings
// Awaiting supplements :)
"Uplink_WaveSpawnType": 1,
```

#### **9 - Central Generator Cluster**

Geomorph-tied objective type (same as Reactor Startup/Shutdown).

Here's a list of the name of valid generator geomorph (in which you can spawn a generator cluster) . Use Ctrl + F in the doc '_**All Geomorph**_' to see what they look like:

* **Digsite hub HA 1**\
  ****"Assets/AssetPrefabs/Complex/Mining/Geomorphs/Digsite/geo\_64x64\_mining\_dig\_site\_hub\_HA\_01.prefab"
* **Digsite hub HA 2**\
  ****"Assets/AssetPrefabs/Complex/Mining/Geomorphs/Digsite/geo\_64x64\_mining\_dig\_site\_hub\_HA\_02.prefab"
* **Lab hub HA 2**\
  ****"Assets/AssetPrefabs/Complex/Tech/Geomorphs/geo\_64x64\_tech\_lab\_hub\_HA\_02.prefab"
* **Lab HA 2** \[Standard Geomorph]\
  ****"Assets/AssetPrefabs/Complex/Tech/Geomorphs/geo\_64x64\_tech\_lab\_HA\_02.prefab"
* **Lab HA 3** \[Standard Geomorph]\
  "Assets/AssetPrefabs/Complex/Tech/Geomorphs/geo\_64x64\_tech\_lab\_HA\_03.prefab"

Note that I've marked the last 2 geomorph with \[Standard Geomorph]. If you directly copy-paste them into `"CustomGeomorph"` in `LevelLayoutDatablock`, your console will flood with Errors. Without editing `ComplexResourceSetDatablock`, if you want to use the 2 standard geomorphs, you will need to roll `subseed` to change the Zone's layout and `MarkerSubseed` to finally get a Generator Cluster. I suggest you read the '_**All Geomorph**_' doc to find out why.

Oh, finally, in `LevelLayoutDatablock`, don't forget to set `"GeneratorClustersInZone"` to `1` in the desired zone.

```json
// Central Generator Cluster 
"CentralPowerGenClustser_NumberOfGenerators": 4,
"CentralPowerGenClustser_NumberOfPowerCells": 4,
// You can change the fog upon plugging in each cell
// This field is not used in Rundown 6. 
// Take the following format as example.
"CentralPowerGenClustser_FogDataSteps": [
    { // Fog changes upon plugging in the 1st powercell
      "m_fogDataId": 80, // reference to FogSettingsDatablock
      "m_transitionToTime": 1.0
    },
    { // Fog changes upon plugging in the 2nd powercell
      // If you don't want the fog to change at this point, 
      // set "m_fogDataId" to the same as the one before. 
      "m_fogDataId": 80, 
      "m_transitionToTime": 1.0
    },
    { // Upon plugging in the 3rd powercell
      "m_fogDataId": 81, 
      "m_transitionToTime": 60.0
    },
    { // Upon plugging in the 4th powercell
      "m_fogDataId": 82, 
      "m_transitionToTime": 360.0
    },
    { // Fog changes upon completing the ChainedPuzzleMidObjective.
      // Awaitng supplement: I'm not sure what would happen 
      //                     if "ChainedPuzzleMidObjective" is 0.
      "m_fogDataId": 83, 
      "m_transitionToTime": 10.0
    }
],
```

#### **10 - Activate Neonate\_HSU / Datasphere.  Unseal Hi-Sec Cargo Crate.**

Geomorph-tied objective type (same as Reactor Startup/Shutdown).

Here's a list of the name of available geomorph. Use Ctrl + F in the doc '_**All Geomorph**_' to see what they look like:

* **Lab Dead End Room 1**\
  ****"Assets/AssetPrefabs/Complex/Tech/Geomorphs/geo\_64x64\_Lab\_dead\_end\_room\_02.prefab"
* **Lab Dead End Room 2**\
  ****"Assets/AssetPrefabs/Complex/Tech/Geomorphs/geo\_64x64\_Lab\_dead\_end\_room\_01.prefab"
* **Refinery Dead End HA 1**\
  ****"Assets/AssetPrefabs/Complex/Mining/Geomorphs/Refinery/geo\_64x64\_mining\_refinery\_dead\_end\_HA\_01.prefab"

```json
// -------------------------------------
// Activate Neonate_HSU / Datasphere. Unseal Hi-Sec cargo crate.
// -> Neonate_HSU (which has 4 variants) and Datasphere are all Big pickup Item. 
// -> Vanilla levels for reference: R3A1, R3B2, R3D1, R4C1, R5B3

// Speaking of that you set Activate Neonate_HSU as you Main layer objective,
// -> "ActivateHSU_ItemFromStart" specifies the Big Pickup item that will be placed 
//    in the elevator cargo container upon cage drop,
// -> "ActivateHSU_ItemAfterActivation" specifies the Big Pickup item will
//    be replaced by another Big Pickup item after it's inserted.
// Both of them are references to ItemDatablock    
"ActivateHSU_ItemFromStart": 0,
"ActivateHSU_ItemAfterActivation": 0,
"ActivateHSU_StopEnemyWavesOnActivation": false,

// Works analogously as "DoNotSolveObjectiveOnReactorComplete".
"ActivateHSU_ObjectiveCompleteAfterInsertion": false,
"ActivateHSU_RequireItemAfterActivationInExitScan": false,
"ActivateHSU_Events": [],
```

#### **11 - Survival**

This type of objective begins upon entering the layer.

For example, if you set the Secondary objective as Survival, the timer won't starts until any of your teammates pace into the Secondary Bulkhead Door.

The objective completes upon the timer ends.

You can end the timer in advance by using a `"ForceWin"` event.

After the "prepare time" ends, the objective manager will start executing events in `"EventsOnActivate"`, and spawn waves in `"WavesOnActivate"`.

```json
// The time for the players to "get prepared"
"Survival_TimeToActivate": 0.0, 

// The "Timer"
"Survival_TimeToSurvive": 0.0, 

// The titles. You can use either a string or a reference to TextDatablock
"Survival_TimerTitle": "", 
"Survival_TimerToActivateTitle": "",
```

#### **12 - Gather Terminal**

```json
// Gather Terminal (R6D2 Main), works analogously as Gather Small Item. 
"GatherTerminal_SpawnCount": 0, 
"GatherTerminal_RequiredCount": 0, 
"GatherTerminal_Command": "", 
"GatherTerminal_CommandHelp": "", 
"GatherTerminal_DownloadingText": "", 
"GatherTerminal_DownloadCompleteText": "", 
"GatherTerminal_DownloadTime": -1.0, 
```

### How to write an Event?

First, let's take a look at an event copy-pasted from the vanilla datablock:

```json
{
    "Trigger": 0,
    
    // set up chained puzzle for a certain command on a terminal
    // can only be used in "UniqueCommands" in LevelLayoutDatablock
    "ChainPuzzle": 0,   
    "UseStaticBioscanPoints": false,
    
    "Type": 0,
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
    }
}
```

A bit intimidating, right? Luckily, for a certain event type only few fields are used, which means we can remove unused fields to make our file look cleaner.

Here's a list of EventType:

* 0 - None
* 1 - OpenSecurityDoor
* 2 - UnlockSecurityDoor
* 3 - AllLightsOff
* 4 - AllLightsOn
* 5 - PlaySound
* 6 - SetFogSetting
* 7 - DimensionFlashTeam
* 8 - DimensionWarpTeam
* 9 - SpawnEnemyWave
* 10 - StopEnemyWaves
* 11 - UpdateCustomSubObjective
* 12 - ForceCompleteObjective
* 999 - EventBreak

In the following I will try to explain what each event type does, and which fields are used. Also an example is provided for you to refer to and copy-paste.

#### 0 - None

Does nothing. You can use it to display Warden Intel.

```json
{
    "Trigger": 0,
    "Type": 0,
    "LocalIndex": 0,
    "Delay": 0.0,
    "WardenIntel": 1345 // "Door to [ZONE_5] unlocked"
}
```

#### 1 - OpenSecurityDoor

Open a given Sec-Door, even the door is locked with a security alarm.

Note: Without aid of a plugin, you can't open a sec-door that has already been "approached".

```json
{
    "Trigger": 0,
    "Type": 1,
    "Layer": 1,          // Specify layer in Reality (cannot be in dimension).  
    "DimensionIndex": 0, // Specify dimension if you are unlocking a door in dimension
    "LocalIndex": 2,     // Specify the door to unlock 
    "Delay": 0.0,
    "WardenIntel": 1345 // "Door to [ZONE_2] opened"
}
```

#### 2 - UnlockSecurityDoor

Works similarly as OpenSecurityDoor.

```json
{
    "Trigger": 0,
    "Type": 2,
    "Layer": 1,          // Specify layer in Reality (cannot be in dimension).  
    "DimensionIndex": 0, // Specify dimension if you are unlocking a door in dimension
    "LocalIndex": 2,     // Specify the door to unlock 
    "Delay": 0.0,
    "WardenIntel": 1345 // "Door to [ZONE_2] unlocked"
}
```

#### 3 - AllLightsOff

Shutdown all lights in the current level.

```json
{
    "Trigger": 0,
    "Type": 3,
    "Delay": 0.0,
    "WardenIntel": 1345 // "://SUPPROT SYSTEM OFFLINE"
}
```

#### 4 - AllLightsOn

Turn on all lights in the current level.

```json
{
    "Trigger": 0,
    "Type": 4,
    "Delay": 0.0,
    "WardenIntel": 1345 // "://SUPPROT SYSTEM RESTORED"
}
```

#### 5 - PlaySound

Play certain sound in/from specific zone. You will need to collect the sound ID from vanilla data.

```json
{
    "Trigger": 0,
    "Type": 5,
    "Layer": 1,
    "DimensionIndex": 0,
    "LocalIndex": 2,
    "Delay": 0.0,
    "WardenIntel": 1345, // "Birther Scream"
    "SoundID": 55555555, // Don't use this as your sound id :)
    "DialogueID": 0 // I'm not sure if this is also used. 
}
```

#### 6 - SetFogSettings

Changed the fog for the entire level.

```json
{
    "Trigger": 0,
    "Type": 6,
    "Delay": 0.0,
    "FogSetting": 87,
    "WardenIntel": 1345, // "Malfunction in air purification system."
    "FogTransitionDuration": 5400.0
}
```

#### 7 - DimensionFlashTeam

\[Not 100% sure if my explanation is correct. Rectify if anywhere wrong]

Teleport your team to a given dimension, and teleport back after a certain duration.

This event is used in R6A1 and R6C1.

```json
{
    "Trigger": 0,
    "Type": 7,
    "DimensionIndex": 1,     // Dimension to teleport to
    "LocalIndex": 0,
    "Delay": 0.0,
    "Duration": 120.0,       // Teleport back after 120 seconds.
    "ClearDimension": true, // Removed all enemies in the dimension after teleporting back
    "WardenIntel": 1345
}
```

#### 8 - DimensionWarpTeam

\[Not 100% sure if my explanation is correct. Rectify if anywhere wrong]

Teleport your team to a given dimension. You need to execute another `"DimensionWarpTeam"` event in the dimension to teleport either to another dimension or back to reality.

This event is used in R6D1 and R6D4.

```json
{
    "Trigger": 0,
    "Type": 8,
    "DimensionIndex": 1,     // Dimension to teleport to
    "LocalIndex": 0,
    "Delay": 0.0,
    "ClearDimension": true, // Removed all enemies in previous the dimension
    "WardenIntel": 1345
}
```

#### 9 - SpawnEnemyWave

Like the name said.

Note: What's the difference between `"WardenIntel"` and `"IntelMessage"`?

I'm not pretty sure...

`"WardenIntel"` display intel message after `"Delay"` timer ends.

`"IntelMessage"` won't change \[ZONE\_4] into actual zone name, and is displayed after `"SpawnDelay"` timer ends.

```json
{
    "Trigger": 0,
    "Type": 9,
    "Delay": 0.0,
    "WardenIntel": 0,
    "EnemyWaveData": {
        "WaveSettings": 23,
        "WavePopulation": 7,
        "SpawnDelay": 0.0,
        "TriggerAlarm": false,
        "IntelMessage": 0
    }
}
```

#### 10 - StopEnemyWave

Stop all waves. For example, scout wave, reactor wave, uplink wave... everything.

```json
{
    "Trigger": 0,
    "Type": 10,
    "Delay": 0.0,
    "WardenIntel": 0,
}
```

#### 11 - UpdateCustomSubObjective

What's "Custom SubObjective"? It's the "\[PROGRESSION]" shown in the upper left of your hud, right below the objective description text.

What's the difference between `"CustomSubObjectiveHeader"` and `"CustomSubObjective"`? I don't know how to explain this. It is used in R6D3 Overload, which tells you to shutdown the Error alarm in Zone 292.

Note: unlike `"WardenIntel"`,   `"CustomSubObjectiveHeader"` and `"CustomSubObjective"` only accept reference to datablock. Do not use string.

```json
{    
    "Trigger": 0,
    "Type": 11,
    "Layer": 0,
    "Delay": 0.0,
    "WardenIntel": 0,
    "CustomSubObjectiveHeader": 1344,
    "CustomSubObjective": 1345
}
```

#### 12 - ForceCompleteObjective

Used in R6D1 to make the Main objective complete after the boss death.

Use `"Layer"` to specify which layer to force win.

```json
{    
    "Trigger": 0,
    "Type": 12,
    "Layer": 1,
    "Delay": 0.0,
    "WardenIntel": 0
}
```

#### 999 - EventBreak

Used in `"EventsOnActivate"`with `"OnActivateOnSolveItem"` set to `true`.  Split up the event sequence to several parts and execute each on solving objective item.

Take R6C1, R6C2 Main, R6D4 as example.

```json
{    
    "Trigger": 0,
    "Type": 999
}
```
