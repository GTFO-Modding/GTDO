---
description: TerminalLogFileData (filled)
---

# TerminalLogFileData

Defines terminal logs.

## Fields

### FileName - String

Name of the log.

### FileContent - [LocalizedText](./localizedtext.md) (nested type)

Text content of the log.

### FileContentOriginalLanguage - [Language](../enum-types.md#language) (enum)

No description provided.

### AttachedAudioFile - UInt32

Audio ID attached to the log.

### AttachedAudioByteSize - Int32

Terminals display log file size. This is the "size" of the audio file attached.

### PlayerDialogToTriggerAfterAudio - UInt32

PlayerDialog to trigger after audio log finishes.
