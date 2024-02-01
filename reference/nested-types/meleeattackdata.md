---
description: MeleeAttackData
---

# MeleeAttackData

Object that determines timings and animation for some melee attacks.

***

## Fields

### Side - [eMeleeAttackSide](../enum-types.md#emeleeattackside) (enum)

The side the melee attack uses.

### Anim - [AnimHash](animhash.md) (nested type)

The animation to use for the attack.

### AnimBlendIn - Single

The length of time it blends the previous animation with this attack's before fully assuming the animation of this attack.

### AttackLengthTime - Single

The time that the attack is active for. Once finished, the weapon transitions to the idle state.

### AttackHitTime - Single

Only affects Hit animations. Determines the time in seconds that the animation starts from.

### DamageStartTime - Single

Time in seconds at which the weapon starts checking for collisions with its model hitbox.

### DamageEndTime - Single

Time in seconds at which the weapon stops checking for collisions with its model hitbox.

### AttackCamFwdHitTime - Single

Time in seconds at which the attack hits the target directly in view.\
While a target is directly in view and this time has not been reached, the model hitbox will be inactive.

### ComboEarlyTime - Single

Time in seconds at which the next melee attack can be triggered.

### \*FrameTime - Single

All matching fields are ignored in datablocks.

In plugins, if set to a value, sets the corresponding Time field to FrameTime/30.
