---
description: TerminalPlacementData
---

# TerminalPlacementData

Used for specifying terminal placements.

## Fields

### PlacementWeights - [ZonePlacementWeights](zoneplacementweights.md) (nested type)

Terminal placement weights.

### AreaSeedOffset - Int32

Seed offset for area selection.

### MarkerSeedOffset - Int32

Seed offset for marker selection within selected area.

### LocalLogFiles - [List TerminalLogFileData](terminallogfiledata.md) (nested type)

List of logs in this terminal.

### UniqueCommands - [List CustomTerminalCommand](customterminalcommand.md) (nested type)

List of unique commands in this terminal.

### StartingStateData - [TerminalStartStateData](terminalstartstatedata.md) (nested type)

Specified the starting state of the terminal (audio playing, password-protected).
