---
description: GameData_ArchetypeDataBlock_bin.json (filled)
---

# Archetype

***

***

## Fields

### PublicName - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

Weapons technically have 2 names. This is the one used as a more generic name, e.g. "Assault Rifle".

The other name is specified in GearJSON in [PlayerOfflineGearDataBlock](playerofflinegear.md).

### Description - [LocalizedText](../../nested-types/localizedtext.md) (nested type)

Weapon description displayed in lobby.

### FireMode - [eWeaponFireMode](../../enum-types.md#eweaponfiremode) (enum)

Firing mode of this weapon. Can affect which other fields are used.

SemiBurst is an unused but functional firemode. It's basically a semi auto where you can fire x shots before triggering a cooldown, unless your delay between any 2 shots is big enough for it to reset.

### RecoilDataID - UInt32 ([RecoilDataBlock](recoil.md))

Recoil data ID of this weapon.

### DamageBoosterEffect - [AgentModifier](../../enum-types.md#agentmodifier) (enum)

Which booster types should affect this weapon.

Seems functional but currently unused.

### Damage - Single

Base damage of this weapon.

### DamageFalloff - Vector2

Linear damage falloff for this weapon.

X determines where it starts, Y determines where it ends.

Anywhere in-between X and Y the damage falls off linearly via a multiplier to 0, but there's a lowest value for the multiplier.

Lowest value for the multiplier is currently 0.1.

### StaggerDamageMulti - Single

Stagger damage multiplier for base damage.

### PrecisionDamageMulti - Single

Precision damage multiplier for base damage. This multiplier is only applied when a weakspot is hit (back damage doesn't count).

### DefaultClipSize - Int32

Default mag size.&#x20;

[GearMagPartDataBlock](../rarely-edited/gearmagpart.md) can affect this.&#x20;

### DefaultReloadTime - Single

Time in seconds for the reload animation to complete. Note that reload can be completed before the animation is done.

[GearMagPartDataBlock](../rarely-edited/gearmagpart.md) can affect this.

### CostOfBullet - Single

Used together with [PlayerDataBlock](player.md) Ammo values to several weapon ammo values. For example for a weapon with a cost of 10 and these (currently game default) ammo values:

```
  "AmmoStandardInitial": 300,
  "AmmoStandardInitialOnDropin": 200,
  "AmmoStandardMaxCap": 460,
  "AmmoStandardResourcePackMaxCap": 450,
```

We will have:

* 30 initial (mag included) ammo when starting a level.
* OnDropin seems unused.
* 46 max reserve ammo.
* 450 \* 0.2 / 10 = 9 bullets per refill (0.2 comes from the fact that you use 0.2 of a refill at any given time (e.g. 4 uses of a refill is 0.8)

Note that for sentries there's another multiplier in [ItemDataBlock](item.md) called ClassAmmoCostFactor.

### ShotDelay - Single

Time in seconds between shots.

Sentries don't immediately detect that an enemy died so they're more likely to waste ammo on dead enemies with low delay.

### ShellCasingSize - Single

Shell casing size multiplier.

### ShellCasingSpeedRange - Vector2

Shell casing ejection speed range.

### PiercingBullets - Boolean

Whether this weapon can pierce.

Pierce is currently broken for sentries.

### PiercingDamageCountLimit - Int32

How many enemies can a piercing bullet hit. 1 means it will not pierce.

5 is technically max, although in a roundabout way - for piercing weapons, a loop is performed a maximum of 5 times before exiting. Each collider hit consumes one iteration. It can often happen that the same enemy is hit several times (although damage is applied only once), making high pierce give diminishing returns. In practice, even with 4-5 pierce you'll most likely only hit up to 3 enemies.

### HipFireSpread - Single

Hipfire random spread.

Spread is hard to judge, but a weapon with 1 spread is fairly accurate even at mid-long range (\~15m).

Behind the scenes this is just a multiplier for a random point inside a unit circle.

### AimSpread - Single

ADS random spread.

### EquipTransitionTime - Single

How long equip animation takes. Also affects when it can be fired after selecting.

### EquipSequence - [List WeaponAnimSequenceItem](../../nested-types/weaponanimsequenceitem.md) (nested type)

Animation sequence to play when equipping a weapon.

### AimTransitionTime - Single

How long ADS animation takes.

### AimSequence - [List WeaponAnimSequenceItem](../../nested-types/weaponanimsequenceitem.md) (nested type)

Animation sequence to play when aiming with a weapon.

### BurstDelay - Single

For burst weapons, delay between separate bursts.

### BurstShotCount - Int32

For burst weapons, how many shots a single burst fires.

### ShotgunBulletCount - Int32

For shotguns, pellet count in a shot.

### ShotgunConeSize - Int32

For shotguns, the cone size. Note that this value is Int32, only accepting whole numbers.

Cone size affects pellet spread, but it is not random. It fires one pellet in the middle and the rest in a circle around the middle based on a sin/cos function.

### ShotgunBulletSpread - Int32

Shotgun random pellet spread. Also a whole number.

This doesn't scale well with cone size and can result in shots going way further from the middle than expected.

### SpecialChargetupTime - Single

How long it takes for the weapon to charge before firing.

### SpecialCooldownTime - Single

Delay before a weapon can charge up again when it stops firing.

Currently broken for auto weapons.

### SpecialSemiBurstCountTimeout - Single

Time for semiburst weapon shot count to reset.

### Sentry\_StartFireDelay - Single

Delay before a sentry starts firing when detecting an enemy.

### Sentry\_RotationSpeed - Single

Sentry rotation speed.

### Sentry\_DetectionMaxRange - Single

Sentry detection max range.

Currently broken (sort of) - the noise range the sentry causes around itself directly depends on this value.

### Sentry\_DetectionMaxAngle - Single

Max angle to either side at which a sentry can detect enemies.

Note that sentries can only cover 180 degrees (value 90) total as they physically cannot turn around.

### Sentry\_FireTowardsTargetInsteadOfForward - Boolean

By default sentries shoot where their barrel is aiming, which can cause them to miss when they shouldn't.

Setting this to true will make them basically an aimbot, always shooting towards the target.

Unfortunately, the target position is also currently broken on some enemies and so they can miss even as aimbot.

### Sentry\_LongRangeThreshold - Single

Distance for long range boosters.

### Sentry\_ShortRangeThreshold - Single

Distance for short range boosters.

### Sentry\_LegacyEnemyDetection - Boolean

Seems to determine how sentries should target enemies.

Practical difference is unknown.

### Sentry\_FireTagOnly - Boolean

Should sentry only target biotracker-tagged enemies.

### Sentry\_PrioTag - Boolean

Should sentry prioritize targetting biotracker-tagged enemies.

### Sentry\_StartFireDelayTagMulti - Single

Start fire delay multiplier when targetting biotracker-tagged enemies.

### Sentry\_RotationSpeedTagMulti - Single

Rotation speed multiplier when targetting biotracker-tagged enemies.

### Sentry\_DamageTagMulti - Single

Damage multiplier when targetting biotracker-tagged enemies.

### Sentry\_StaggerDamageTagMulti - Single

Stagger damage multiplier when targetting biotracker-tagged enemies.

### Sentry\_CostOfBulletTagMulti - Single

Cost of bullet multiplier when targetting biotracker-tagged enemies.

Makes perfect sense.

### Sentry\_ShotDelayTagMulti - Single

Shot delay multiplier when targetting biotracker-tagged enemies.
