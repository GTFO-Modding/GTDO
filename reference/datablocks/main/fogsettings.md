---
description: GameData_FogSettingsDataBlock_bin.json (filled)
---

# FogSettings

This datablock edits fog settings, which include fog's visual effects (color, opacity, etc.), height, and controls if the fog is flipped (inversed fog, like the one in R5E1), infectious, etc.

As one of the most important features of the game, fog serves to occlude player's sight, limit zones' reachability and make decisions on whether to 'toss a Fog Repeller and combat amid' or to 'flee'. Also, colored fog (for example, Green Fog in R7C2, etc.) would affect lighting of the entire level, making your level able to give players impressions of tension, horror, anxiety, sound, and so on.

## Fields

### Enabled - Boolean

Unused.

### FogColor - Color

Determine the color of the fog. This can affect the lighting of the entire level and create some preferable visual effect.

It seems that starting in Rundown 7, the way fog occludes sight and interacts with lights has changed. Colored fog may not block sight well, so it's best to use white fog for that purpose.

For example, here's extremely dense red fog:

![Extremely dense red fog, looking from above fog](<../../../.gitbook/assets/image (1) (3).png>)

![Extremely dense red fog, looking from below fog](<../../../.gitbook/assets/image (8) (1).png>)

### FogDensity - Single

The base fog density in the entire level.

To create inversed fog (e.g. R5E1), you have to set `FogDensity` and `DensityHeightMaxBoost` such that `FogDensity` < `DensityHeightMaxBoost`

### FogAmbience - Single

Unused.

### DensityNoiseDirection - Vector3

`Noise` are those floating particles right above the fog plane. These particles make the fog plane resemble a tide.&#x20;

This field controls the floating direction of those particles / tide pattern of the fog plane.

### DensityNoiseSpeed - Single

Controls how fast noise particles float / how uneven the tide pattern of the fog plane is.

### DensityNoiseScale - Single

Seems to be the size of the noise particles. Higher values can make them look visibly separated, kind of like dust clouds.&#x20;

### DensityHeightAltitude - Single

The lowest point for the fog height. For non-inversed fog, everything with altitude lower than this value would be fully submerged by the fog.&#x20;

As a reference for zone altitude: `Low` : -4.0, `Mid` : 0.0, `High`: 4.0

### DensityHeightRange - Single

Distance above lowest point for fog height, used in calculating the highest point for fog height.

### DensityHeightMaxBoost - Single

This is the actual field for controlling the density of (non-inversed) fog. The larger, the more occluding.

### Infection - Single

The maximum value for how fast infection accumulates from fog. For example, `0.1` would take you 10 seconds to get fully infected. `0.03` is a common, average value to set to.&#x20;

Note that how much infection you get depends on how deep in the fog you are with linear scaling, where the highest point of infection (and lowest actual infection gain rate) is at `DensityHeightAltitude + DensityHeightRange` and lowest point is `DensityHeightAltitude`
