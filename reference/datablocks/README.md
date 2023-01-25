---
description: >-
  A list of every datablock in the game, their fields and if you're lucky, what
  they do!
---

# Datablocks

Datablocks are groups of fields that form all the customizable parts of rundowns, weapons, enemies, levels, waves, and more. Everything needed to create a custom rundown can be created utilizing datablocks. This reference will explain all of the fields within each datablock. Check out the guides for more information about how to use them.

{% hint style="warning" %}
#### Prerequisites

To work with datablocks, you should be familiar with JSON.
{% endhint %}

### Datablocks Storage

Datablocks and their change history is kept on [GitHub](https://github.com/UntiIted/OriginalDataBlocks).

## Common Fields

All datablocks share 3 main fields, each of them has special meaning.

#### persistentID - UInt32

The ID of the block, used to reference by all other blocks. If you see any other field with type UInt32, chances are it's a reference to some other block (but that type is also used to reference wwise audio IDs).

Must be unique.

{% hint style="warning" %}
Although persistentID type is UInt32, the actual value range is often much smaller because it is changed to other types in networking for example.\
Sticking to a safe range of 1-65535 is recommended, but datablocks with even smaller ranges do exist ([SurvivalWaveSettings](main/survivalwavesettings.md) for example). If we notice any blocks with a range smaller than that, we will make a note about it in the relevant reference page.
{% endhint %}

#### internalEnabled - Boolean

Whether this block is enabled. Disabled blocks are ignored by the game.

#### name - String

The name of the block. This seems to be only for readability and is not used by the game, but it may be used by mods.

Must be unique.

## Additional Fields

#### Headers

This field is only used by devs in their editor.

#### LastPersistentID - UInt32

The last persistentID found in datablocks. Serves no purpose but can clutter the logs if not set correctly.

## Types

in all datablocks documentation, you see a specific format of fields:\
`name - type` or `name - type (special meaning)`

The name is just that, the name of the field. The type is what data should be specified there.

These are the most basic types:

* [UInt32](https://docs.microsoft.com/en-us/dotnet/api/system.uint32?view=net-6.0) - whole number from 0 to 4,294,967,295
* [Int32](https://docs.microsoft.com/en-us/dotnet/api/system.int32?view=net-6.0) - integer from -2,147,483,648 to 2,147,483,647
* [Single](https://docs.microsoft.com/en-us/dotnet/api/system.single?view=net-6.0) (aka float) - approximate real number of varying precision with values ranging from negative 3.402823e38 to positive 3.402823e38.
* [Boolean](https://docs.microsoft.com/en-us/dotnet/api/system.boolean?view=net-6.0) - data type with 2 values - "true" and "false".
* [String](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=net-6.0) - plain text.

#### Enumerator/Enum

[Enums](https://docs.microsoft.com/en-us/dotnet/api/system.enum?view=net-6.0) are a special type, representing named values. Here's an example ([eEnemyZoneDistribution](../enum-types.md#eenemyzonedistribution)):

* None - 0
* Force\_One - 1
* Rel\_Value - 2

The underlying enum type here is Int32, and it has 3 named values. Enums usually have this underlying type, start from 0, and move up in sequence, but there are exceptions. You can check out the [enum types](../enum-types.md) page to see all enums.

In JSON, enums can be specified both as underlying type and as plain text.

There are special cases where the enum values are combined, e.g. [EnemyMovementDataBlock](enemymovement.md) AnimationControllers, type [AnimatorControllerHandleName](../enum-types.md#animatorcontrollerhandlename).

An example value you could see here is "EnemyRunner, EnemyLow, EnemyCrawl", or 84. This combines 3 values and the game processes it in a way that understands the value set as all 3.

#### Nested type/Class/Object

In datablocks reference, nested type refers to a class that's defined by the game. Each nested type has its own page to reduce clutter when the same type is referenced several times.

In JSON, these are all [objects](https://www.w3schools.com/js/js\_json\_objects.asp), starting and ending with curly braces `{ }`.

Every datablock file defines one object containing several fields, including a list of objects - Blocks.

#### List/Array and Dictionary

All 3 of these never go by themselves, they contain other types (and sometimes can be nested).

Lists and Arrays always start and end with `[ ]` symbols. For example, a "List Int32" looks like this: `[ 1, 2, 3 ]` instead of a plain Int32 value `1`. a "List List Int32" follows the same principle: `[ [ 1, 2, 3 ], [ 1, 2, 3 ] ]`. Arrays look exactly the same as Lists in JSON.

Dictionaries are a more complex type and are rarely found in datablocks. A dictionary is an object that maps 2 types, the first as key, the 2nd as value. In JSON, dictionaries look the same as nested objects.

![Example dictionary](<../../.gitbook/assets/image (3) (1) (1) (1).png>)

Here you can see a dictionary with 2 keys "Glue" and "Explosive" mapped to objects. In JSON, an object with 2 fields "Glue" and "Explosive" could look exactly the same.

### Empty values

Sometimes you see fields set to seemingly invalid values such as an empty string or -1, or just not there at all. In these cases you can think of the fields as unset, which means the game provides some default value or behaviour for it.

### Additional notes

#### Vector

In datablocks, Vectors are messed up right now and generate with some fields that don't actually do anything:

![Vectors fields that aren't supposed to be there](<../../.gitbook/assets/image (2) (1).png>)

You can ignore or delete these.

#### Time fields

Fields related to time/length/duration are specified in seconds unless stated otherwise.
