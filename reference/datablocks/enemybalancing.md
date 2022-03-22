---
description: GameData_EnemyBalancingDataBlock_bin.json
---

# EnemyBalancingDataBlock

No description provided.

***

## Fields

### Health - [HealthData](../nested-types/healthdata.md) (nested type)

The amount of health an enemy has before it dies.

### GlueTolerance - Single

Determines how much C-foam is required to freeze the enemy.

### GlueFadeOutTime - Single

The number of seconds it takes for an enemy to unfreeze after being C-foamed.

### CanBePushed - Boolean

Determines if the shove action will have any affect on the enemy.

### ForbidTwitchHit - Boolean

Attempts to prevent "soft-stagger" from occuring, where an enemy's projectiles and tentacles are unable to be used.

### AllowDamgeBonusFromBehind - Boolean

Determines if an enemy can receive additional back damage.

### UseTentacleTunnelCheck - Boolean

The default attack type of tentacles. Checks if the player collided with the tentacle to deal damage, and can attack around sharp corners.

### UseVisibilityRaycastDuringTentacleAttack - Boolean

Determines if an enemy has hit-scan tentacle attacks, where the player being line of sight guarantees a hit.

### TentacleAttackDamageRadiusIfNoTunnelCheck - Single

Adds an area-of-effect to a hit-scan tentacle. This is used so that an enemy can hit clients who may have latency, or allow the enemy to hit multiple players.

### TentacleAttackDamage - Single

The damage value of tentacle attacks.

### MeleeAttackDamage - Single

The damage value of punching attacks.

### MeleeAttackDamageCheckRadius - Single

The size of damage checking spheres around both of the enemy's hands to determine if a player was hit or not.

### TagTime - Single

How long a bio-tracker tag remains before it completely fades out.

### EnemyCollisionRadius - Single

Determines if a player is in range to collide with the enemy.

### EnemyCollisionPlayerMovementReduction - Single

When an player is colliding with an enemy, this will reduce the player's movement speed.

### EnemyCollisionMinimumMoveSpeedModifier - Single

The slowest the player can be as a result of colliding with multiple of this enemy.
