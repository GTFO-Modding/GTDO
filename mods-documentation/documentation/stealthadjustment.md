---
description: Customizable stealth settings, mostly related to sleeper alerting
---

# StealthAdjustment

{% embed url="https://gtfo.thunderstore.io/package/Untilted/StealthAdjustment/" %}

### Developer

Discord: Stormpooper#3436

### Overview

Most information about this mod is available on Thunderstore. This page is more about a reference of the fields and more detailed information.

### Mod compatibility

As far as I know, there should be no problems running this together with any other existing mods, but for documentation's sake I have to mention that this plugin prefixes 2 methods with `return false`: `EnemyAgent.PropagateTargetLimited` and `EnemyDetection.UpdateDetectionTimer`.&#x20;

Plugin developers will know what this means.

### Persistent data

This is another one of my mods that uses persistent data - a json file with default values is automatically generated on first launch. These values can be edited as you see fit and they can also be packaged with a separate mod (most likely a rundown) so the users of that mod will automatically use the included settings.

### Fields reference

{% hint style="info" %}
Vector2 here represents a min/max value
{% endhint %}

{% hint style="info" %}
If the default value of a field is not mentioned, assume base game does not have an equivalent or the default is the same as it is in base game (can be seen in a fresh generated config file).
{% endhint %}

#### LightBuildupSpeedMultiplier - float

Multiplier for how fast sleepers build up detection to flashlights. This is also editable in datablocks.

By default in the game it takes \~2 seconds of light for the sleeper to alert, here it will take around 1 second.

#### LightCooldownSpeedMultiplier - float

Multiplier for how fast sleepers cool down from detection to flashlights. This is also editable in datablocks.

This value's cooldown being slow leads to sleepers repeatedly cycling from heartbeats to sleeping to heartbeats again, which just wastes players' time. By default, here it cools down 4 times faster.

#### ChanceToPropagate - float

Overrides the chance for a sleeper to alert another sleeper under conditions when it is normally rng. In the base game, the rng value varies by type of melee weapon used and damage inflicted, but here it is always the same and set to be guaranteed by default.

#### DetectionDistance - float

The max distance at which a sleeper can propagate to another. This value is squared - 169 means 13 meters.

#### ClusterDetectionDistance - float

The max distance at which a sleeper is considered in a cluster with another sleeper.

#### LowNoiseClusterDetectionDistance - float

Same as above but for "low noise" weapons (knife). Defaults to 1 meter instead of the usual 3.

#### ContinueDetectionAfterClusterAlert - bool

If this is set to true, when a sleeper alerts something in a cluster, it will continue scanning for more sleepers to alert within the detection distance.

#### MaxAlertCount - int

The maximum number of sleepers to propagate to. Game default is effectively 1.

#### IncludeClusterInAlertCount - bool

Whether cluster sleepers should add to the alert count.

#### LimitClusterByAlertCount - bool

Whether the number of alerted sleepers in a cluster is limited by the max alert count. Will not function if `IncludeClusterInAlertCount` is set to false.

#### AdditionalHibernationWindow - float

The additional window of time during which a sleeper cannot be propagated to. Starts when a sleeper has just started transitioning to "active" (started listening). Base game does not have such a window.

#### AdditionalNoiseDuration - float

The player's noise system is a bit complicated. The player can make a bunch of different noise "types" and that noise stays on the player for a certain period of time. This can sometimes result in the player alerting a sleeper with noise even though the player is not actually making noise anymore, leading players to feel like the sleeper alerted for no reason.

To minimize the effect of this on normal stealth, this field was added and set to a negative value by default to decrease the "noisy" time of the player. This has some side-effects making sleepers not react to noise properly in some cases but I think it's worth it.

Most noises in the game linger for 0.55 seconds and the default value here is -0.4, meaning the noises instead linger for 0.15 seconds.

#### AdditionalRunNoiseDuration - float

Same as above but for run and "Loud landing" noise types (loud landing is what killed bhop). This value is set to 0 by default, meaning there is no difference from the base game. Changing this to a negative value will potentially allow people to bhop again.

#### TransitionDurationInTransToActive - Vector2

Transition fields are related to the 4 states of a hibernating sleeper's detection, where sleeping is "deactivated" and listening is "active", and the other 2 states are the in-between states.

This transition is from "deactivated" to "starts listening". At this point, noise detection is off (will not start pulsing/heartbeats to noise), but can already propagate, which is why `AdditionalHibernationWindow` was added.

Game default is 2 seconds, mod default is 1.25 seconds, which means the sleeper will react to noises faster.

#### TransitionDurationActive - Vector2

This duration is effectively the amount of time the sleeper will stay listening. As soon as this ends, noise detection and propagation are turned off.

Game default is 2-4 seconds, mod default is 1-4.

#### TransitionDurationInTransToDeactivated - Vector2

This duration is the amount of time it takes for the sleeper to be fully deactivated, but it has no mechanic difference from the sleeper being deactivated (sleeping). It basically just extends a few other timers, making the sleeper stay asleep longer.

Game and mod default is 1 second.

#### TransitionDurationDeactivated - Vector2

Essentially the amount of time a sleeper will stay asleep if undisturbed.

Game default is 2-15 seconds, mod default is 5-15 seconds.

Imagine getting 2 seconds of movement before red light again or something alerts despite the flashlight sync you just did.

I was actually going to expand this and some others to variable values depending on how well players perform in stealth (where more noise/time spent/messing up would force sleepers to be more awake) but decided against it.

#### TransitionSilentCloseSneakWindow - Vector2

This is the duration of time after a sleeper is deactivated when a sleeper will not noise-detect players sneaking right next to it (if you didn't know, yes they detect sneaking within 2 meters of the sleeper).

Game and mod default is 0.5-1.5 seconds.
