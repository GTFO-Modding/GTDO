---
description: TerminalZoneSelectionData (filled)
---

# TerminalZoneSelectionData

Used to select existing terminals.

***

## Fields

### LocalIndex - [eLocalZoneIndex](../enum-types.md#elocalzoneindex) (enum)

Zone of the terminal selection.

### SeedType - [eSeedType](../enum-types.md#eseedtype) (enum)

Which seed to use when picking.&#x20;

Session should randomize between level attempts, Build should produce the same result always. Static is same as Build except the seed is set separately.

None might be broken.

### TerminalIndex - Int32

Might be unused.

### StaticSeed - Int32

Seed to use when SeedType is set to static.
