---
description: GameData_ChainedPuzzleDataBlock_bin.json (filled)
---

# ChainedPuzzle

Defines Chained Puzzle settings (e.g. Security Door alarm).

## Fields

### PublicAlarmName - String

The Alarm name. For example, `Class S Surge Alarm`

### TriggerAlarmOnActivate - Boolean

Whether to trigger alarm when the puzzle starts. Typically set to `false` for scans without an alarm and enemy wave.

However, you can set this field to `true` even if you don't specify the enemy wave for the puzzle via the following fields. In that case, there will still be alarm sound but no enemy waves.

### SurvivalWaveSettings - UInt32 ([SurvivalWaveSettingsDataBlock](../main/survivalwavesettings.md))

Determine how the wave spawns. You set this field to make the wave either a relatively regular, surge, diminished, or ://ERROR! alarm wave.

You may take those wave settings already available in the vanilla datablocks into good use.

### SurvivalWavePopulation - UInt32 ([SurvivalWavePopulationDataBlock](../main/survivalwavepopulation.md))

Determine what type(s) of enemy would spawn.

### DisableSurvivalWaveOnComplete - Boolean

Specify whether to stop the wave after Chained Puzzle Completion. Typically set to `false` for ://ERROR! alarm.

### UseRandomPositions - Boolean

Whether to use random position for each scan. Usually set to `true`.

By setting this field to `false`, the scan position for each puzzle would be **relatively static,** i.e. it's not static all the time.

### WantedDistanceFromStartPos - Single

As explained by the field name :)

### WantedDistanceBetweenPuzzleComponents - Single

Also as explained by the field name :)

### ChainedPuzzle - [List ChainedPuzzleComponent](../../nested-types/chainedpuzzlecomponent.md) (nested type)

Determines the count and types of scans.

### OnlyShowHUDWhenPlayerIsClose - Boolean

If set to `true`, the HUD won't show up if you are a certain distance (seems to be 25m) away from the scan.

Typically set to `false` for regular scan, and `true` for extraction scan.

### AlarmSoundStart - UInt32

Alarm sound when the puzzle starts. Changing the sound properly may give the scan a different impression.

Usually this sound starts the alarm sound loop.

Referenced to SoundID.

### AlarmSoundStop - UInt32

Alarm sound when the puzzle stop. Could use this field to set the ambient ERROR alarm sound.

Usually this sound stops the alarm sound loop. If not set correctly, the alarm sound can go on forever.

Referenced to SoundID.
