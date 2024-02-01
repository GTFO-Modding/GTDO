---
description: GameData_MeleeAnimationSetDataBlock_bin.json
---

# MeleeAnimationSet

Defines melee weapon animation sets alongside several timings related to them.

This datablock is referenced by a [MeleeArchetypeDataBlock](meleearchetype.md).

***

## Fields

### HoldToChargeTime - Single

Time in seconds that attack must be held for the weapon to begin charging.

### MaxDamageChargeTime - Single

Time in seconds to reach full charge.

### AutoAttackTime - Single

Time in seconds after starting a charge at which the weapon will automatically swing.

### AutoAttackWarningTime - Single

Time in seconds after starting a charge at which a sound effect plays and causes the reticle to blink red (to warn that the automatic attack will occur soon).

### FPIdleAnim - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### FPSettleAnim - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### FPWalkAnim - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### FPRunAnim - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### FPJumpAnim - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### FPLandAnim - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### FPChargeCancelAnimRight - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### FPChargeCancelAnimLeft - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### FPAttackMissRight - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation for the light attack that swings from the right (e.g. the first swing).

### FPAttackMissLeft - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation for the light attack that swings from the left (e.g. the second swing).

### FPAttackHitRight - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation that plays after hitting a light attack from the right.

### FPAttackHitLeft - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation that plays after hitting a light attack from the left.

### FPAttackPush - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation for pushing.\
Note: Pushes cannot normally be consecutively done faster than 1.2s. However, attacks reset this cooldown and allow two consecutive pushes to be performed afterwards, separated by push's combo time.

### FPAttackChargeUpRight - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation for charging an attack from the right.

### FPAttackChargeUpLeft - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation for charging an attack from the left.

### FPAttackChargeUpReleaseRight - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation for the charge attack that swings from the right.

### FPAttackChargeUpReleaseLeft - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation for the charge attack that swings from the left.

### FPAttackChargeUpHitRight - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation that plays after hitting a charge attack from the right.

### FPAttackChargeUpHitLeft - [MeleeAttackData](../../nested-types/meleeattackdata.md) (nested type)

Animation that plays after hitting a charge attack from the left.

### TPAnimHashIdle - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### TPAnimHashIdleCrouch - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### TPAnimHashAttackLeft - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### TPAnimHashAttackLeftCrouch - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### TPAnimHashAttackLeftCharge - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### TPAnimHashAttackLeftChargeCrouch - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### TPAnimHashAttackLeftRelease - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.

### TPAnimHashAttackLeftReleaseCrouch - [AnimHash](../../nested-types/animhash.md) (nested type)

No description provided.
