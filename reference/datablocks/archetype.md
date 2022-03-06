---
description: GameData_ArchetypeDataBlock_bin.json
---

# Archetype

The Archetype Datablock is used to assign stats and metadata to bulletweapons, including their ingame name and description. Fundamentally, the archetype is the core of every gun in GTFO.

The Archetype Datablock is referenced via it's PersistentID by the [PlayerOfflineGearDataBlock](playerofflinegear.md).

***

## Fields:

### Meta Data:

#### PublicName - LocalizedText

The primary name of the weapon (eg: Assault Rifle). Displayed in the lobby screen and the inventory. The 'model name' of the weapon, as displayed in the lobby screen, can be found in the [PlayerOfflineGear](playerofflinegear.md) datablock

#### Description - LocalizedText

The description of the weapon as displayed in the lobby screen.

### Weapon Properties:

#### Firemode - [eWeaponFireMode](archetype.md#eweaponfiremode-enum)

The firing mode of the weapon. See [eWeaponFireMode](archetype.md#eweaponfiremode-enum) for more information.

#### RecoilDataID - uint

The persistent ID of the [RecoilDataBlock](recoil.md) entry for this weapon to use.

#### DamageBoosterEffect - [AgentModifier](archetype.md#agentmode-enum)

Determines which booster effect types should benefit (or detriment) the stats of this weapon. See [AgentModifier](archetype.md#agentmode-enum) for more information

### Weapon Damage:

#### Damage - Float

The amount of raw damage this weapon deals. For reference, in vanilla a Striker has 20 HP, and a Shooter has 30 HP. In practice, the effective damage value of a weapon is heavily impacted by the DamageFalloff, PrecisionDamageMulti, and the WeakSpotMulti of the enemy you are attacking. For more information on enemy weakspots and damage multipliers, see [EnemyBalancing](enemybalancing.md).

#### DamageFalloff - Vector2

Controls how much damage the weapon does over distances. The damage of your gun will slope linearly from it's raw value to 1.0 over the range of your damage falloff.

* x: The range in meters at which damage falloff begins
* y: The range in meters at which the damage drops to 1.0

![](<../../.gitbook/assets/Damage Falloff.png>)

#### StaggerDamageMulti - Float

Damage multiplier for stagger damage. Enemies have a separate healthbar for stagger damage, which causes a hitstun when it reaches 0. This healthbar is decremented by your weapons damage multiplied by the StaggerDamageMulti when hit.

#### PrecisionDamageMulti - Float

Damage multiplier for hits on enemy weakspots. Enemies have a WeakSpotMulti that controls the damage you deal when hitting their weakspots (Generally the head or tumors). The damage dealt to a particular enemy when shot in a weakspot is the product of your weapons damage, PrecisionDamageMulti, and the enemy's WeakSpotMulti. For more information about enemy weakspots, see [EnemyBalancing](enemybalancing.md)

### Weapon Ammo:

#### DefaultClipSize - Int

The default maximum number of bullets in the weapon's magazine.

#### DefaultReloadTime - Float

The default amount of time in seconds that it takes to complete the weapon's reload animation.

#### CostOfBullet - Float

Controls the maximum amount of ammo that your weapon can store in it's reserve capacity, and the amount of ammo provided by ammopacks. This value is used as a divisor for the [PlayerDataBlock's](player.md) AmmoMaxCap based on which slot the weapon is equipped in. I still have no fucking idea why they made it work this way, sorry. By default, AmmoStandardMaxCap is 460, and AmmoSpecialMaxCap is 230.

In order to calculate the CostOfBullet for a given reserve capacity, divide the desired ammo value by the AmmoMaxCap. For example, for 100 bullets in a primary weapon, you would need a CostOfBullet of 4.6.

#### ShotDelay - Float

The amount of time in seconds between shots. (Note: for burst weapons, the amount of time between distinct bursts is controlled by [BurstDelay](archetype.md#burstdelay-float), not ShotDelay).

### Weapon Pierce:

#### PiercingBullets - Bool

Determines whether or not your bullets can pierce enemies.

#### PiercingDamageCountLimit - Int

The number of enemies a piercing bullet is allowed to hit. At a value of 1, your bullet will only hit 1 enemy and not pierce. Pierce does _not_ work on shotguns.

Note: The limit for pierce is 5 enemies. The devs at one point attempted to buff the Hel Rifle by changing it's pierce count to 6, but it has since been confirmed that the pierce cap was not changed to allow for this.

&#x20;In practice, bullets are capable of hitting the same enemy multiple times without dealing additional damage, which increases the pierce counter, and in turn greatly reduces the amount of enemies you're actually able to hit with piercing weapons. Even at a cap of 5, you will rarely shoot through more than 3 enemies.

### Weapon Accuracy:

#### HipFireSpread - Float

The amount of inaccuracy when firing from the hip.

#### AimSpread - Float

The amount of inaccuracy when firing while aiming down sights.

### Weapon Animations:

#### EquipTransitionTime - Float

The amount of time in seconds for the equip animation to complete.

#### EquipSequence - [WeaponAnimSequenceItem](archetype.md#weaponanimsequenceitem) List

The animation sequence to play when equipping your weapon. See [WeaponAnimSequenceItem](archetype.md#weaponanimsequenceitem) for more info.

#### AimTransitionTime - Float

The amount of time in seconds for the aim down sights animation to complete.

#### AimSequence- [WeaponAnimSequenceItem](archetype.md#weaponanimsequenceitem) List

The animation sequence to play when aiming down the sights of your weapon. See [WeaponAnimSequenceItem](archetype.md#weaponanimsequenceitem) for more info.

### Weapon Special Properties:

#### BurstDelay - Float

The amount of time in seconds between each distinct burst of a burst-fire weapon. The amount of time between each shot of the burst is controlled by ShotDelay.

#### BurstShotCount - Int

The number of shots to fire for each distinct burst of a burst-fire weapon.

#### ShotgunBulletCount - Int

The number of shots to fire if this weapon is a shotgun.

#### ShotgunConeSize - Int

The size of the cone to fire if this weapon is a shotgun. NOTE: This value is _not_ a float, it must be a whole number or your game will halt at startup. I have no idea why they did this, because the code literally casts this value to a float anyway as soon as they use it. I wish I was joking

#### ShotgunBulletSpread - Int

The distance between each shot of the shotgun blast within the cone. Once again, this value is an int, _not_ a float. It must be a whole number. :(

#### SpecialChargeupTime - Float

The amount of time in seconds it takes for your weapon to charge up before firing. On automatic and burst weapons, this is only applied when you start firing.

#### SpecialCooldownTime - Float

The amount of time in seconds it takes for a [SemiBurst ](archetype.md#semiburst-unused-efiremode)weapon to wind down after it's burst limit has been reached.

#### SpecialSemiBurstCountTimeout - Float

The amount of time in seconds it takes for [SemiBurst](archetype.md#semiburst-unused-efiremode) weapons to reset their burst count.

### Sentry Gun Properties

#### Sentry\_StartFireDelay - Float

The amount of time in seconds it takes for your sentrygun to begin firing.

#### Sentry\_RotationSpeed - Float

The speed that your sentrygun can change it's point of aim when firing at enemies.

#### Sentry\_DetectionMaxRange - Float

The maximum distance in meters that your sentry can detect enemies.

#### Sentry\_DetectionMaxAngle - Float

The maximum angle that your sentrygun can target enemies within.

#### Sentry\_FireTowardsTargetInsteadOfForward - bool

If true, the sentrygun's bullets will fire directly towards the enemy it's targeting instead of the direction the sentrygun is facing, which drastically improves their accuracy.

#### Sentry\_LongRangeThreshold - Float

The distance in meters at or above which the 'Long Range Sentry Damage' booster effect will trigger.

#### Sentry\_ShortRangeThreshold - Float

The distance in meters below which the 'Short Range Sentry Damage' booster effect will trigger.

#### Sentry\_LegacyEnemyDetection - bool

If true, the sentrygun will use the older, simpler targeting code.

#### Sentry\_FireTagOnly - bool

If true, the sentrygun will _only_ fire towards enemies which are tagged with the biotracker.

#### Sentry\_PrioTag - bool

If true, the sentrygun will prioritize firing at enemies which are tagged with the biotracker.

#### Sentry\_StartFireDelayTagMulti - float

The multiplier for Sentry\_StartFireDelay if the targeted enemy has been tagged with the biotracker.

#### Sentry\_RotationSpeedTagMulti - float

The multiplier for Sentry\_RotationSpeed if the targeted enemy has been tagged with the biotracker.

#### Sentry\_DamageTagMulti - float

The multiplier for Damage if the targeted enemy has been tagged with the biotracker.

#### Sentry\_StaggerDamageTagMulti - float

The multiplier for StaggerDamageMulti if the targeted enemy has been tagged with the biotracker.

#### Sentry\_CostOfBulletTagMulti - float

The multiplier for CostOfBullet if the targeted enemy has been tagged with the biotracker. Frankly, I have no idea how this would even work but it sounds incredibly cursed.

#### Sentry\_ShotDelayTagMulti - float

The multiplier for ShotDelay if the targeted enemy has been tagged with the biotracker.

## Special Types:

### eWeaponFireMode : Enum

This enum is used by BulletWeapons to determine which firemode class to assign to the weapon, which each effect the behavior of the weapon when firing.

* **0 - Semi:** Fire one shot per click with the defined chargeup and cooldown on every shot
* 1 **- Burst:** First multiple shots per one click with chargeup and cooldown on each burst
* 2 - **Auto:** Fully automatic fire with the defined chargeup and cooldown on each burst
* 3 **- SemiBurst:** A strange, unused firemode. See [SemiBurst ](archetype.md#semiburst-unused-efiremode)for more information
* **10 - SentryGunSemi:** Used for a hardcoded reference to Archetype ID 54
* **11 - SentryGunAuto:** Used for a hardcoded reference to Archetype ID 57
* **12 - SentryGunBurst:** Used for a hardcoded reference to Archetype ID 58
* **13 - SentryGunShotgunSemi:** Used for a hardcoded reference to Archetype ID 59

### AgentModifier : Enum

* 0 - None
* 1 - RegenerationCap
* 2 - RegenerationSpeed
* 3 - HealSupport
* 4 - ReviveSpeedSupport
* 5 - ReviveStartHealthSupport
* 6 - MeleeResistance
* 7 - ProjectileResistance
* 8 - InfectionResistance
* 50 - PistolDamage
* 51 - SMGDamage
* 52 - DMRDamage
* 53 - AssaultRifleDamage
* 54 - CarbineDamage
* 55 - AutoPistolDamage
* 56 - HELDamage
* 58 - ShotgunDamage
* 59 - RevolverDamage
* 60 - SniperDamage
* 61 - BurstCannonDamage
* 62 - MachineGunDamage
* 63 - MachinePistolDamage
* 64 - RifleDamage
* 65 - BurstRifleDamage
* 66 - DoubleTapRifle
* 67 - BullpupRifleDamage
* 68 - CombatShotgunDamage
* 69 - ChokeModShotgunDamage
* 70 - StandardWeaponDamage
* 71 - SpecialWeaponDamage
* 100 - GlueStrength
* 101 - GlueEfficiency
* 102 - SentryGunSpeed
* 103 - SentryGunDamage
* 104 - SentryGunLongRangeDamage
* 105 - SentryGunShortRangeDamage
* 106 - TripMineDamage
* 107 - ScannerRechargeSpeed
* 108 - AmmoSupport
* 150 - HackingProficiency
* 151 - ComputerProcessingSpeed
* 152 - InitialAmmoStandard
* 153 - InitialAmmoSpecial
* 154 - InitialAmmoTool
* 155 - FogRepellerEffect
* 156 - GlowstickEffect
* 157 - BioscanSpeed
* 200 - MeleeDamage

### WeaponAnimSequenceItem

Lists of the WeaponAnimSequenceItem class are used by a number of datablocks to control weapon animation sequences.

#### TriggerTime - Float

The time in seconds, after the previous item in the list, at which this item should play

#### Type - eWeaponAnimSequenceItemType

Controls how the game handles this animation sequence item. See eWeaponAnimSequenceItemType for more info

#### StringData - String

The String Data associated with this animation sequence item. Handled differently depending on the Type of this animation sequence item

### eWeaponAnimSequenceItemType : Enum

Used by WeaponAnimSequenceItem to control the behavior of the animation sequence item.

* 0 - WeaponMovementAnim - Animate the First Person Weapon Holder using StringData as an animation clip name
* 1 - FrontPartAnim - Animate the weapon's Front Part using StringData as an animation clip name
* 2 - LeftHandAnim - Animate the FPS arms (animation layer 5) using StringData as an animation clip name
* 3 - LeftHandMagAnim - Animate the FPS arms using the magazine’s animation. _No StringData input required_
* 4 - ReceiverAnim - Animate the weapon’s receiver part using StringData as an animation clip name
* 5 - Sound - Play a sound event using StringData as a sound event ID
* 6 - DoUpdateAmmo - Reload the ammo count on the weapon's magazine. _No StringData input required_
* 7 - Empty - Dont do anything. Typically used at the very end of an animation sequence to set the sequence's overall length. _No StringData input required_
* 8 - StockAnim - Animate the weapon's Stock Part using StringData as an animation clip name
* 9 - RightHandAnim - Animate the FPS Arms (animation layer 6) using StringData as an animation clip name

## Remarks

### SemiBurst - Unused eFireMode

Despite common belief, SemiBurst is actually a fully functional firemode, albeit one with pretty strange behavior that would be difficult to understand without an explanation or a visual indicator ingame.

Like the name implies, SemiBurst is a strange combination of Semi automatic and burst fire. Every time you fire the weapon, a counter is incremented and a timer with it's duration defined by [SpecialSemiBurstCountTimeout](archetype.md#specialsemiburstcounttimeout-float) starts. If the timer is completed, the counter will reset. If the counter reaches the weapon's [BurstShotCount](archetype.md#burstshotcount-int), it will prevent the weapon from firing until the [SpecialCooldownTime](archetype.md#specialcooldowntime-float) is finished.

In effect, SemiBurst weapons allow you to fire slow, precise shots without any interruptions, but when used in rapid-fire, you will only be able to shoot a short burst before being hit with a cooldown.

Note: in SemiBurst, the weapon's [SpecialChargetupTime](archetype.md#specialchargeuptime-float) is applied to every shot, but the [SpecialCooldownTime](archetype.md#specialcooldowntime-float) is only applied if you reach the [BurstShotCount](archetype.md#burstshotcount-int).

