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

Note 1: if you want to set a Chained Puzzle to this command, **only 1 chained puzzle** can be set at once (otherwise, upon command execution, there will be 2 chained puzzle being activated at the same time).

Note 2: basing on Note 1, if you set a Chained Puzzle to the command, for example, let's say that you set the 4th event in the event list with a chained puzzle; by doing so, upon command execution, all events prior to the 4th event will be executed, whereas the 4th event and the events lies after it would be executed after Chained Puzzle Completion.&#x20;

Note 3: for command set with a Chained Puzzle, you should set the SpecialCommandRule to either `OnlyOnce` or `OnlyOnceDeleted`. Otherwise, executing the command multiple times leads to some bugs (for example, the command events not being executed, the enemy wave for the Chained Puzzle not stopping).

### SpecialCommandRule - [TERM\_CommandRule](../enum-types.md#term\_commandrule) (enum)

Specifies what happens to the terminal command after executing it.
