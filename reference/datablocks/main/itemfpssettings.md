---
description: GameData_ItemFPSSettingsDataBlock_bin.json (filled)
---

# ItemFPSSettings

Determines Item location and camera settings for the first-person view.

> Note: GTFO uses 2 separate cameras in the First-Person view - the Look Camera renders the world, and the Item Camera renders the item held in the player's hands. These two cameras usually have differing FOVs in both the aimed and unaimed state of a weapon/tool.

***

## Fields

### localPosHip - Vector3

Position of weapon when hipfiring

### localRotHip - Vector3

Rotation of weapon when hipfiring

### SwayAmount - Single

No description provided.

### crouchTiltAngle - Single

Angle the weapon tilts when player is crouched

### localPosRelaxed - Vector3

Position of weapon when idle animation is playing

### localRotRelaxed - Vector3

Rotation of weapon when idle animation is playing

### localPosZoom - Vector3

Position of weapon when aiming

### localRotZoom - Vector3

Rotation of weapon when aiming

### bodyOffsetLocal - Vector3

Root position of weapon

### bodyRotationOffsetLocal - Vector3

Root rotation of weapon

### ItemCameraFOVDefault - Int32

FOV of camera that renders the weapon or tool

### ItemCameraFOVZoom - Int32

FOV of camera that renders the weapon or tool, when aiming

### LookCameraFOVZoom - Int32

FOV of camera that renders the world

### canAim - Boolean

Can this weapon be aimed?

### onlyStartAimOnPressed - Boolean

Identical across all base game Items (set to false), probably unused

### canRelax - Boolean

Can this weapon play an idle animation?

### customDelayUntilRelax - Single

Time until this weapon plays an idle animation

### allowRotToAimPos - Boolean

Is the weapon allowed to rotate when moving to the aimed position?

### rotToAimPosMinDis - Single

Identical across all base game Items (set to 1.0), probably unused

### transitionToAim - [eFPISTransitionTime](../../enum-types.md#efpistransitiontime) (enum)

Speed of aim transition animation

### RecoilAnimation - UInt32 ([ItemMovementAnimationDataBlock](../rarely-edited/itemmovementanimation.md))

Animation used when the weapon is recoiling

### IdleAnimation - UInt32 ([ItemMovementAnimationDataBlock](../rarely-edited/itemmovementanimation.md))

Animation used when the player is stationary

### WalkAnimation - UInt32 ([ItemMovementAnimationDataBlock](../rarely-edited/itemmovementanimation.md))

Animation used when the player is walking

### RunAnimation - UInt32 ([ItemMovementAnimationDataBlock](../rarely-edited/itemmovementanimation.md))

Animation used  when the player is sprinting

### JumpAnimation - UInt32 ([ItemMovementAnimationDataBlock](../rarely-edited/itemmovementanimation.md))

Animation used  when the player is jumping

### LandAnimation - UInt32 ([ItemMovementAnimationDataBlock](../rarely-edited/itemmovementanimation.md))

Animation used when the player lands from a jump

### ChargeCancelAnimation - UInt32 ([ItemMovementAnimationDataBlock](../rarely-edited/itemmovementanimation.md))

Animation used when the weapon is charged and the charge is aborted before completion

### DofDefault - [DOFSettingsData](../../nested-types/dofsettingsdata.md) (nested type)

Default Depth of Field settings

### DofAim - [DOFSettingsData](../../nested-types/dofsettingsdata.md) (nested type)

Depth of Field settings when weapon is aiming
