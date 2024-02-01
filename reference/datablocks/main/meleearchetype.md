---
description: GameData_MeleeArchetypeDataBlock_bin.json
---

# MeleeArchetype

Defines melee weapon stats and metadata.

This datablock is not referenced directly, but instead specified by the [GearCategoryDataBlock](gearcategory.md) given to a melee weapon.

***

## Fields

### PublicName - String

Datablock name. Unused elsewhere.

### NoiseLevel - [DamageNoiseLevel](../../enum-types.md#damagenoiselevel) (enum)

Normal: Wakes up sleepers in 7m from hitting locks or the ground.\
Quiet: Wakes up sleepers in 4m from hitting locks or the ground. Also has reduced chance to trigger long range aggro (i.e. glowing enemy wakes up far away from killing another enemy).

### ChargedAttackDamage - Single

Damage dealt by fully charged attacks.\
Partial charge interpolates the damage from light to fully charged by the charge progress cubed.

### LightAttackDamage - Single

Damage dealt by light attacks.

### LightStaggerMulti - Single

Stagger damage multiplier for light attacks.

### ChargedStaggerMulti - Single

Stagger damage multiplier for fully charged attacks.\
Partial charge interpolates the multiplier from light to fully charged by the charge progress cubed.

### LightPrecisionMulti - Single

Precision damage multiplier for light attacks.

### ChargedPrecisionMulti - Single

Precision damage multiplier for fully charged attacks.\
Partial charge interpolates the multiplier from light to fully charged by the charge progress cubed.

### LightEnvironmentMulti - Single

Environment damage multiplier for light attacks (i.e. vs. locks and doors).

### ChargedEnvironmentMulti - Single

Environment damage multiplier for fully charged attacks (i.e. vs. locks and doors).\
Partial charge interpolates the multiplier from light to fully charged by the charge progress cubed.

### LightBackstabberMulti - Single

Backstab damage multiplier for light attacks. Stacks multiplicatively with the default backstab bonus. Does not apply to enemies without the default backstab bonus.

### ChargedBackstabberMulti - Single

Backstab damage multiplier for light attacks. Stacks multiplicatively with the default backstab bonus. Does not apply to enemies without the default backstab bonus.\
Partial charge interpolates the multiplier from light to fully charged by the charge progress cubed.

### LightSleeperMulti - Single

Damage multiplier to sleeping enemies for light attacks. Does not apply to Scouts.

### ChargedSleeperMulti - Single

Damage multiplier to sleeping enemies for fully charged attacks. Does not apply to Scouts.\
Partial charge interpolates the multiplier from light to fully charged by the charge progress cubed.

### SkipLimbDestruction - Boolean

Prevents the weapon from breaking enemy limbs.

### CameraDamageRayLength - Single

Distance in meters that the weapon hits what is directly in view. Does not affect the model hitbox.

### AttackSphereRadius - Single

Additional distance in meters around the model hitbox that hits can occur in. Does not affect wall collision.\
Remains inactive while something is directly in view.\
Appears to be twice as large as the value written in practice.

### PushDamageSphereRadius - Single

Distance in meters around the player that pushes can affect targets in.

### CanHitMultipleEnemies - Boolean

Allows the weapon to hit with both the forward damage ray (hitting a target directly in view) and the model hitbox. Also allows the weapon to hit additional targets after the first hit if the hit animation can deal damage.\
Can still damage multiple enemies simultaneously with the model hitbox even if set to false.

### EvaluateHoldBeforeAttack - Boolean

If true, waits until the attack button is released to trigger a light attack. Otherwise, immediately begins the light attack animation on mouse click, though it can still transition to a charge attack.

### PlayImpactEffect - Boolean

Should cause the impact particle effect when hitting terrain.

### AllowRunningWhenCharging - Boolean

Allows the user to sprint while charging.\
If false, will stop and prevent sprinting while charging.

### PlayerRunSpeedMultiWhileCharging - Single

Multiplier to user sprint speed while charging. Cannot cause the user to exceed their sprint speed, but can increase the diagonal sprint speed to match the forward sprint speed.

### MeleeAnimationSet - UInt32 ([MeleeAnimationSetDataBlock](meleeanimationset.md))

Melee animation set ID of this weapon.

### MeleeSFXSet - UInt32 ([MeleeSFXDataBlock](../rarely-edited/meleesfx.md))

Melee SFX set ID of this weapon.

### ChargedAttackStaminaCost - ActionCost

Stamina cost for fully charged attacks.\
Partial charge interpolates the multiplier from light to fully charged by the charge progress cubed.

### LightAttackStaminaCost - ActionCost

Stamina cost for light attacks.

### PushStaminaCost - ActionCost

Stamina cost for pushes.
