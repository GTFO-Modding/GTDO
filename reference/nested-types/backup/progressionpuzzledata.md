---
description: ProgressionPuzzleData (filled)
---

# ProgressionPuzzleData

Defines puzzles required to open security doors.

***

## Fields

### PuzzleType - [eProgressionPuzzleType](../enum-types.md#eprogressionpuzzletype) (enum)

The type of the puzzle.

### CustomText - [LocalizedText](localizedtext.md) (nested type)

Custom text for the door.

Only used for Locked\_No\_Key type.

### PlacementCount - Int32

Number of cells to place.

Only used for PowerGenerator\_And\_PowerCell type.

Note that cells can also be spawned by big pickup distribution, arguably with better random placement results.

### ZonePlacementData - [List ZonePlacementData](zoneplacementdata.md) (nested type)

Alternative placement locations. Picked randomly from the list.
