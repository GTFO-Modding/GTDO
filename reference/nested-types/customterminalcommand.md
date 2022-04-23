---
description: CustomTerminalCommand
---

# CustomTerminalCommand

Defines custom terminal commands.

## Fields

### Command - String

Name of the command.

### CommandDesc - String

Description of the command.

### PostCommandOutputs - [List TerminalOutput](terminaloutput.md) (nested type)

List of output returned after terminal command is posted.

### CommandEvents - [List WardenObjectiveEventData](wardenobjectiveeventdata.md) (nested type)

List of events to execute when command is executed.

### SpecialCommandRule - [TERM\_CommandRule](../enum-types.md#term\_commandrule) (enum)

Specifies what happens to the terminal command after executing it.
