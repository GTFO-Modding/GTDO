---
description: GameData_PlayerDataBlock_bin.json (filled)
---

# Player

Defines player stats.

While this is a datablock, currently its only reference is hardcoded ID 1.

## Fields

### health - Single

The max health of a player.

### healthRegenStartDelayAfterDamage - Single

How long it takes for health to start regenerating after taking damage.

### healthRegenRelMax - Single

Relative max hp to regenerate.

E.g. 0.5 from 100 base would be 50.

### healthRegenDelay - Single

Delay between health regeneration updates.

### healthRegenPerSecond - Single

How much health is regenerated per second.

### friendlyFireMulti - Single

Friendly fire damage multiplier.

Currently broken for tools.

### fallDamageMinHeight - Single

Minimum height a player has to fall to take fall damage.

### fallDamageMaxHeight - Single

Falling height where a player takes maximum fall damage.

### fallDamageMin - Single

Minimum fall damage a player can take.

### fallDamageMax - Single

Maximum fall damage a player can take.

Anywhere between min and max, fall damage scales linearly.

### nanoswarmShieldDamageMultiplierCurve - AnimationCurve

Unknown, most likely related to the unreleased nanoswarm tool and likely to change.

### nanoswarmShieldResistanceCurve - AnimationCurve

Unknown, most likely related to the unreleased nanoswarm tool and likely to change.

### nanoswarmNegativeResistanceCurve - AnimationCurve

Unknown, most likely related to the unreleased nanoswarm tool and likely to change.

### battery - Int32

Seems unused.

### smallBatteryConsumtionPerSec - Single

Seems unused.

### mediumBatteryConsumtionPerSec - Single

Seems unused.

### largeBatteryConsumtionPerSec - Single

Seems unused.

### walkMoveSpeed - Single

Player move speed while walking.

### runMoveSpeed - Single

Player move speed when running/sprinting.

### airMoveSpeed - Single

Affects move speed in the air. Seems to have little effect on slowing down and turning, mostly impacts speeding up. However, unless set to high values, makes no notable impact.

### crouchMoveSpeed - Single

Player move speed while crouching.

### ladderMoveSpeed - Single

Player move speed when going up and down ladders.

### walkFootstepLength - Single

Only seems to have an impact on when player footstep audio is played.

### runFootstepLength - Single

Only seems to have an impact on when player footstep audio is played.

### crouchFootstepLength - Single

Only seems to have an impact on when player footstep audio is played.

### throttleSmoothAcc - Single

Multiplier for smooth acceleration. At low values players will have trouble speeding up.

### throttleSmoothStop - Single

Multiplier for smooth stopping. At low values players will have trouble stopping in place (can still reverse direction normally depending on acc value).

### throttleSmoothVertical - Single

Seems to have no effect.

### jumpVelInitial - Single

Initial vertical velocity gained from a jump.

### jumpGravityMulDefault - Single

Gravity mults affect how fast falling accelerates (rising decelerates).

Gravity mult when rising and holding the jump button.

### jumpGravityMulButtonReleased - Single

Gravity mult when rising and not holding the jump button.

### jumpGravityMulAfterPeak - Single

Gravity mult after jump peak.

### jumpGravityMulFalling - Single

Gravity mult when falling without jumping.

### jumpVerticalVelocityMax - Single

Maximum vertical movement speed.

### camPosDefault - Vector3

Default player camera position offset from player's feet.

### camPosCrouch - Vector3

Player camera position offset while crouched.

### camFovRunDif - Single

Added fov while player is running.

### DofDefault - [DOFSettingsData](../../nested-types/dofsettingsdata.md) (nested type)

Default depth of field settings.

### DofInElevator - [DOFSettingsData](../../nested-types/dofsettingsdata.md) (nested type)

Depth of field settings in elevator.

### DofInTerminal - [DOFSettingsData](../../nested-types/dofsettingsdata.md) (nested type)

Depth of field settings in terminal.

### ChromaticAbberationIntensityMax - Single

Seems unused.

### mouselookAimScaleMinMax - Vector2

Mouselook settings are probably something you shouldn't mess with.

Seems to affect aim sensitivity when in sights.

### mouselookAimScaleFovRef - Vector2

Seems to affect aim sensitivity when in sights.

### FPSArmsOffset - Vector3

FPS settings are probably something you shouldn't mess with.

FPS model setting.

### FPSBodyOffset - Vector3

FPS model setting.

### AdditionalFPSBodyOffsetWhenRunning - Vector3

FPS model setting.

### FPSBodyOffsetWhenNotFollowingCamera - Vector3

FPS model setting.

### FPSBodyScale - Vector3

FPS model setting.

### FPSBodyMoveNeckToFollowCamera - Boolean

FPS model setting.

### FPSBodyWantedDisToNeck - Single

FPS model setting.

### GearMaxSightHeightDiff - Single

Affects maximum possible height above default of sights.

### AmmoStandardInitial - Int32

Ammo settings are closely tied with [Archetype](archetype.md#costofbullet-single) cost of bullet settings and explained there.

These settings are not literal bullet counts but rather a base value for calculations.

Initial standard weapon ammo when starting the level.

### AmmoStandardInitialOnDropin - Int32

Seems unused.

### AmmoStandardMaxCap - Int32

Max reserve ammo for standard weapons.

### AmmoStandardResourcePackMaxCap - Int32

Affects how much ammo you get from a refill pack.

### AmmoSpecialInitial - Int32

Initial special weapon ammo when starting the level.

### AmmoSpecialInitialOnDropin - Int32

Seems unused.

### AmmoSpecialMaxCap - Int32

Max reserve ammo for special weapons.

### AmmoSpecialResourcePackMaxCap - Int32

Affects how much ammo you get from a refill pack.

### AmmoClassInitial - Int32

Initial tool ammo.

### AmmoClassInitialOnDropin - Int32

Seems unused.

### AmmoClassMaxCap - Int32

Max tool ammo.

### AmmoClassResourcePackMaxCap - Int32

Affects how much ammo you get from a refill pack.

There is an additional multiplier for sentries.

### implantSmallTriggerDelay - Single

Seems unused.

### implantBigTriggerDelay - Single

Seems unused.

### itemAnimWeight - Single

{% hint style="warning" %}
The following item settings seem to be either unused or have no impact worth editing for modders, therefore they have no descriptions.
{% endhint %}

### itemAnimAxisWeight - Vector3

No description provided.

### itemLookatAimWeight - Single

No description provided.

### itemLookSwayWeight - Single

No description provided.

### itemLookSwayPosImpulseScale - Vector3

No description provided.

### itemLookSwayPosStiffness - Single

No description provided.

### itemLookSwayPosDamping - Single

No description provided.

### itemLookSwayRotImpulseScale - Vector3

No description provided.

### itemLookSwayRotXMulti - Vector2

No description provided.

### itemLookSwayRotStiffness - Single

No description provided.

### itemLookSwayRotDamping - Single

No description provided.

### itemLookSwayWeightAiming - Single

No description provided.

### itemLookSwayPosImpulseScaleAiming - Vector3

No description provided.

### itemLookSwayRotImpulseScaleAiming - Vector3

No description provided.

### itemAnimWeightAiming - Single

No description provided.

### itemRecoilWeight - Single

No description provided.

### itemFootstepWeight - Single

No description provided.

### itemFootstepWeightAiming - Single

No description provided.

### itemFootstepDelay - Single

No description provided.

### itemFootstepImpulseScale - Vector3

No description provided.

### itemFootstepStiffness - Single

No description provided.

### itemFootstepDamping - Single

No description provided.

### breathingEnabled - Boolean

Determines whether audible breathing from stamina and infection is enabled.

### breathingStaminaEnabled - Boolean

Determines whether audible breathing from stamina is enabled.

### breathingScaredEnabled - Boolean

Seems unused or unknown.

### breathingDebugEnabled - Boolean

When enabled, prints some additional debug logs regarding breathing.

### breathingVolume - Single

Base audible breathing sound volume.

### breathingHealthLowLimit - Single

Health limit for switching to low health breathing sound.

### StaminaTimeBeforeResting - Single

Time without spending stamina before player starts resting.

### StaminaRegenRestingInCombat - Single

Stamina regeneration rate when resting in combat.

### StaminaRegenNotRestingInCombat - Single

Stamina regeneration rate when not resting in combat.

### StaminaRegenRestingOutOfCombat - Single

Stamina regeneration rate when resting out of combat.

### StaminaRegenNotRestingOutOfCombat - Single

Stamina regeneration rate when not resting out of combat.

### StaminaEnableAffectMoveSpeed - Boolean

Whether stamina can affect movement speed.

### StaminaHighMovespeedModifier - Single

Movement speed multiplier when stamina is high.

### StaminaLowMovespeedModifier - Single

Movement speed multiplier when stamina is low.

### StaminaMoveSpeedCurveExponent - Single

Stamina speed modifier is a lerp between high and low with tiredness (0 - full stamina, 1 - empty stamina) as the value used to interpolate.

This value is the exponent for tiredness. Higher value means stamina will slow down players less.

### StaminaEnableAffectMeleeSpeed - Boolean

Whether stamina should affect melee charge speed.

### StaminaHighMeleeSpeedModifier - Single

Melee charge speed multiplier when stamina is high.

### StaminaLowMeleeSpeedModifier - Single

Melee charge speed multiplier when stamina is low.

### StaminaMeleeSpeedCurveExponent - Single

[StaminaMoveSpeedCurveExponent](player.md#staminamovespeedcurveexponent-single) equivalent for melee charge speed.

### StaminaExhaustedAudioThreshold - Single

Sfx Audio threshold for stamina exhausted loop.

### StaminaWasTiredAudioThreshold - Single

Threshold for setting an audio switch for playing was tired breathing audio later.

### StaminaRestedAudioThreshold - Single

Stamina threshold for playing rested audio after player was tired.

### StaminaUsageAffectedByDrama - Boolean

Effectively decides whether InCombat values will be used during combat.

### StaminaMinimumCapWhenNotInCombat - Single

Minimum allowed stamina when not in combat.

### StaminaMaximumCapWhenInCombat - Single

Maximum allowed stamina when in combat.

### StaminaMaximumCapWhenInCombatFallRate - Single

How fast should stamina fall to combat maximum cap during combat.

Default 0 in base game, which means stamina will not fall unless players use it.

### StaminaJumpCost - [ActionCost](player.md#regarding-actioncost)

Jump stamina action cost.

### StaminaSneakCost - [ActionCost](player.md#regarding-actioncost)

Crouching movement stamina action cost.

### StaminaWalkCost - [ActionCost](player.md#regarding-actioncost)

Walking stamina action cost.

### StaminaRunCost - [ActionCost](player.md#regarding-actioncost)

Running/sprinting stamina action cost.

### StaminaCrouchEnterCost - [ActionCost](player.md#regarding-actioncost)

Crouch enter stamina action cost.

### defaultDialogLineDelay - Single

Delay between separate dialog lines.

Dialog line fields seem mostly related to [PlayerDialogDataBlock](../rarely-edited/playerdialog.md).

{% hint style="warning" %}
To our knowledge the rest of these fields are either unused or not useful for modders so most of them probably will not have useful descriptions.
{% endhint %}

### shortDialogCooldown - Single

How long a short dialog is blocked after playing.

### mediumDialogCooldown - Single

How long a medium dialog is blocked after playing.

### longDialogCooldown - Single

How long a long dialog is blocked after playing.

### radioEnabledDefaultDistance - Single

No description provided.

### radioQualityLowestAtDistance - Single

No description provided.

### lowTensionMaxLimit - Single

No description provided.

### mediumTensionMaxLimit - Single

No description provided.

### dialogEnabledInSpectator - Boolean

No description provided.

### radioQualityInSpectator - Single

No description provided.

### radioDistortionInSpectator - Single

No description provided.

### noAirTimeToEmpty - Single

No description provided.

### noAirDamageRel - Single

No description provided.

### noAirDamageDelay - Single

No description provided.

## Regarding ActionCost

A separate page for this **struct** was not generated because whoever made it is an idiot (but actually probably just a new person who doesn't know how datablocks are supposed to work).

For rundown developers, ActionCost is essentially the same thing as any other nested type.

### baseStaminaCostInCombat - Single

Stamina cost of this action in combat.

### baseStaminaCostOutOfCombat - Single

Stamina cost of this action out of combat.

### resetRestingTimerInCombat - Boolean

Whether this action should reset resting timer in combat.

### resetRestingTimerOutOfCombat - Boolean

Whether this action should reset resting timer out of combat.
