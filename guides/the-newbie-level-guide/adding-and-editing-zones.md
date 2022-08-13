---
description: >-
  Don't be fooled by the fact that this guide is 5 parts, this right here is
  half of it
---

# Adding and editing zones

## Overview

This is the meat of the guide. We're going to add a zone, add sleepers, alarms, blood doors, spitters, respawns, resources, a generator puzzle, a pitch black zone, fog.. there's tons of stuff we can do here.

_However_, as always, we can't explore everything or we'll be here all week (and this part is already really long). I'll try not to go into too much detail on the meaning of fields this time either, since you can check the relevant blocks' reference to see what all the fields do.

In practice I would just use the more readable blocks from the [typelist](https://github.com/UntiIted/OriginalDataBlocks) (or some people opt to make levels using the [datablockeditor](https://gtfo-modding.github.io/DatablockEditor/)), but we started with MTFO generated blocks so let's continue with them.

## Before we start

There's a block we can change once for the whole rundown to make level editing life a bit easier in the long run.

The block in question is ExpeditionBalanceDataBlock. We won't cover all of it, only the relevant parts.

{% hint style="info" %}
In rundown db, ExpeditionBalance is always usually set to 1. If you want to make changes specific to levels, you can make a new expedition balance block and set the ID just for the level.
{% endhint %}

Yes, we're about to screw up the balance of the current level, but when making your own levels you shouldn't start with preset resources and sleeper spawns.

#### Resources

The fields in question:

```
      "HealthPerZone": 1.0,
      "DisinfectionPerZone": 1.0,
      "WeaponAmmoPerZone": 0.8,
      "ToolAmmoPerZone": 0.7,
```

These are the base multipliers for resources. Say, with Health being 1.0, setting "HealthMulti" in a zone to 0.8 will result in 4 uses of health, or 80% health for a player. This basically requires no calculation.

The values we don't like - the ones that complicate the math - are weapon and tool ammo.

Set both of those fields to 1 so you don't have to think about how many uses of ammo/tool you'll spawn.

#### Artifacts

Artifact progress is not saved when using mods, so unless you have special mods that make use of it, it's just an annoyance. What's more, they can even cause your layout to reroll if there's not enough space to place all of them, affecting not only one zone, but the rest of the layout generated afterwards.

Set these 2 fields to 0 to avoid artifact spawns:

```
      "ArtifactsPerSegment": 1,
      "ArtifactsPerLayer": 30,
```

#### Sleeper spawns

Sleeper spawning system is convoluted, you can read about it [here](../../reference/nested-types/enemyspawningdata.md). The relevant part here is that when we're going with relative value, the points assigned are calculated like this: `EnemyPopulationPerZone * DistributionValue` (from expedition balance and level layout).

```
      "EnemyPopulationPerZone": 25.0
```

So with a distribution value of 1, we'll have 25 points. But if we want to have exactly 12 points for example, we have to do some math.

Since we don't like math, let's set EnemyPopulationPerZone to 10. Now all we have to do to get 12 points is assign 1.2 in DistributionValue. Why not just go with 1? Because devs decided to automatically fail if it's set to less than 5 regardless of DistributionValue.

Reminder that we have just screwed up the resources and especially sleepers in our level, but in reality we wouldn't start with resources and sleepers already set anyway.

## Adding a new zone

Now that that's taken care of, we can start messing with the level layout itself.

Let's add a new zone to the existing level. We're going to do this in the following order:

1. Copy the first zone and paste it at the end;
2. Change the local index;
3. Setup build parameters - where it's built from, the direction, size, altitude, subcomplex;
4. Adjust terminals;
5. Adjust lighting;
6. Set sleepers;
7. Set resources and consumables.

There's more we can do, but these 7 are plenty to get a full zone. And this is already too much to do at once without testing.

#### Steps 1 and 2

Go to level layout, copy the first zone, and paste it after the last zone. If you collapse all the zones now, you should see 12 in total:

![11 zones collapsed + the pasted one in the end](<../../.gitbook/assets/image (35).png>)

An easier way to see is by using [Breadcrumbs](https://code.visualstudio.com/docs/getstarted/userinterface):

![Zones list with 12 elements in Breadcrumbs](<../../.gitbook/assets/image (10).png>)

Anyway, the last zone had localindex 10, so this one should have 11. You can verify by searching for localIndex 11:

![Search for localindex 11 shows no results](<../../.gitbook/assets/image (24).png>)

{% hint style="info" %}
Remember, if you don't know what a field does, check the datablocks reference to see if it's documented.
{% endhint %}

#### Step 3

SubComplex is 2, so this would be a Storage zone. Let's change it to DigSite (0) instead.

BuildFromLocalIndex is 0, so the source zone here will be the elevator zone. This is fine.

StartPosition is 1 (From\_Start). The elevator zone is pretty small so this might not have impact, but let's change it to 2 (From\_AverageCenter).

StartExpansion is 1. Let's change it to 3, hoping it will generate a security door to the right.

ZoneExpansion is 3. Let's also change this to go right, setting it to 5.

AltitudeData is 3. I would normally allow all here, but this level has infection fog, so let's go with 5. Medium-high should generate mostly above infection fog (of course that depends on fog settings but we already have existing medium zones and we know those are above fog).

CoverageMinMax is 40-45. That should result in a zone around medium-ish size. Let's set it to 65-65. We'll hopefully get a huge room and around 2 larges or a mix.

This is all guesswork. If we wanted precision, we'd have to try mods or keep rerolling the layout until we get what we want. But for now let's roll with what we get, even if it turns out completely different from my expectations.

#### Step 4

The generated zone should be decently big now, so let's have 2 terminals.

Find TerminalPlacements. Delete the log file entry, and set weights to 0, leaving the terminal placement up to rng. Then copy-paste that block.

The results:

![2 terminal placements in the added zone](<../../.gitbook/assets/image (8) (1).png>)

#### Step 5

Lights are decided by "LightSettings" field. If this is set to 0, the light settings in rundown db will be chosen instead.

Right now it's set to 56. If we go to the light settings datablock and find that entry, we'll see it's named "AlmostWhite\_1". Let's try 71 "RustyRedToBrown\_1" instead. If you want, you can pick something different or even make your own light settings.

#### Step 6

The sleeper spawning system is convoluted, you can read about it [here](../../reference/nested-types/enemyspawningdata.md). Yes I already said it before in this page.

We'll have to alternate between 4 files here so you might want to use split editor.

We're going to create 1 randomized group of either strikers, shooters, or big strikers, and 1 group with forced scout. We can reuse existing groups and populations but let's make our own for practice. A bottom-up approach is more appropriate here, so let's start with population.

Deleting all existing blocks and remaking from scratch would introduce a few problems with hardcoded ID uses and the current level spawns so let's not do that (but when making full custom rundowns that might be better in the long run). Instead we'll be using numbers that are guaranteed not to mix up with base game blocks. However, if you want to, you can delete all populations but 1, as there's 3 total missions out of 159 in RundownDataBlock that use other populations:

![3 matches for populations that aren't ID 1](<../../.gitbook/assets/image (22).png>)

All 3 of them are from R1 by the way.

I'll follow the "rules" set in enemy spawning system. Considering the special enum values, limitations, and the total size of the enums in base game (ensuring scout entry doesn't step on one), here are the 4 population entries:

```
        {
          "Role": 5,
          "Difficulty": 20,
          "Enemy": 20,
          "Cost": 5.0,
          "Weight": 1.0,
          "Comment": "Scout"
        },
        {
          "Role": 100,
          "Difficulty": 100,
          "Enemy": 24,
          "Cost": 1.0,
          "Weight": 1.0,
          "Comment": "Diff 100 - group-randomized Striker_Hibernate"
        },
        {
          "Role": 101,
          "Difficulty": 100,
          "Enemy": 26,
          "Cost": 1.0,
          "Weight": 1.0,
          "Comment": "Diff 100 - group-randomized Shooter_Hibernate"
        },
        {
          "Role": 102,
          "Difficulty": 100,
          "Enemy": 28,
          "Cost": 4.0,
          "Weight": 1.0,
          "Comment": "Diff 100 - group-randomized Striker_Big_Hibernate"
        }
```

{% hint style="info" %}
Population entries don't have a "Comment" field. You can add any fields to JSON and as long as there are no syntax errors the game will ignore them.
{% endhint %}

I added comment fields for clarity.

As we can see the role-difficulty pairs are unique so these entries won't be randomized at population-level, only at group-level.

Now to add enemy groups:

```
    {
      "Type": 1,
      "Difficulty": 20,
      "SpawnPlacementType": 0,
      "MaxScore": 5.0,
      "ScoreInAreaPaddingMulti": 1.0,
      "RelativeWeight": 1.0,
      "Roles": [
        {
          "Role": 5,
          "Distribution": 1
        }
      ],
      "name": "Forced Scout",
      "internalEnabled": true,
      "persistentID": 100
    },
    {
      "Type": 0,
      "Difficulty": 100,
      "SpawnPlacementType": 0,
      "MaxScore": 4.0,
      "ScoreInAreaPaddingMulti": 1.0,
      "RelativeWeight": 1.0,
      "Roles": [
        {
          "Role": 24,
          "Distribution": 4
        },
        {
          "Role": 26,
          "Distribution": 2
        }
      ],
      "name": "Diff 100 3 strikers 1 shooter",
      "internalEnabled": true,
      "persistentID": 101
    },
    {
      "Type": 0,
      "Difficulty": 100,
      "SpawnPlacementType": 0,
      "MaxScore": 4.0,
      "ScoreInAreaPaddingMulti": 1.0,
      "RelativeWeight": 0.5,
      "Roles": [
        {
          "Role": 24,
          "Distribution": 3
        },
        {
          "Role": 26,
          "Distribution": 3
        }
      ],
      "name": "Diff 100 2 strikers 2 shooters",
      "internalEnabled": true,
      "persistentID": 102
    },
    {
      "Type": 0,
      "Difficulty": 100,
      "SpawnPlacementType": 0,
      "MaxScore": 4.0,
      "ScoreInAreaPaddingMulti": 1.0,
      "RelativeWeight": 0.1,
      "Roles": [
        {
          "Role": 26,
          "Distribution": 5
        }
      ],
      "name": "Diff 100 4 shooters",
      "internalEnabled": true,
      "persistentID": 103
    },
    {
      "Type": 0,
      "Difficulty": 100,
      "SpawnPlacementType": 0,
      "MaxScore": 4.0,
      "ScoreInAreaPaddingMulti": 1.0,
      "RelativeWeight": 0.2,
      "Roles": [
        {
          "Role": 28,
          "Distribution": 5
        }
      ],
      "name": "Diff 100 1 big striker",
      "internalEnabled": true,
      "persistentID": 104
    }
  ],
  "LastPersistentID": 9999
```

1 forced scout group, and 4 mixed groups of the 3 enemies. Considering the relative weights, this should be a striker-dominant zone. MaxScores are the same all around so these will be a bit more predictable sizes. If we wanted more randomized sizes we could go with a range of 2-6 for example. It's just best not to give really big sizes to groups since a whole group always spawns in the same room, possibly resulting in high concentration in one area and rest zone empty.

Note I included LastPersistentID updated value. That's just so the logs don't clutter saying blocks with IDs above last were found.

Also remember MaxScore has that obnoxious hardcoded random multiplier on it, screwing with our spawns for no good reason.

Finally, we can set the spawns in level layout:

```
          "EnemySpawningInZone": [
            {
              "GroupType": 1,
              "Difficulty": 20,
              "Distribution": 1,
              "DistributionValue": 1,
              "Comment": "1 forced scout"
            },
            {
              "GroupType": 0,
              "Difficulty": 100,
              "Distribution": 2,
              "DistributionValue": 3,
              "Comment": "diff 100 30 score randomized groups"
            }
          ],
```

Comments again for clarity.

30 score spawns + 1 forced scout sounds fair for this zone size, but that of course depends on balancing.

Also normally you would take a look at the generated layout and settle on it before starting to spawn sleepers.

#### Step 7

All that's left before we finally drop in is resources and consumables.

Before setting any spawns, always make sure these 2 are set to true:

```
          "AllowSmallPickupsAllocation": true,
          "AllowResourceContainerAllocation": true,
```

Resources are fairly straight-forward and purely dependent on balance so let's just use them to verify ExpeditionBalance values, setting all to 2 - should be 10 uses of each resource.

![Resources set to 2.0 each](<../../.gitbook/assets/image (28).png>)

Consumables are set by just one field - "ConsumableDistributionInZone". If we tried to make something specific we'd have to constantly look at ItemDataBlock. Let's do the same as we did with lights and judge by names here instead.

It's currently set to 20, "OnlyFogReps". Fog repeller balancing is important for an infection level, but our zone specifically is set to medium-high altitude data. While it can still generate something under infection fog, it should mostly stick to above that. Our options are combatting darkness, fog, giving foam/tripmines which are very powerful, or just generic consumable distribution that doesn't focus on anything in particular. Let's go with the generic one, setting it to 1.

## Testing the new zone

A more proper level-making process could be something like this for example:

1. The entire layout;
2. Objective;
3. Resources;
4. Consumables and other spawns;
5. Sleepers;
6. Alarms.

But since we're just learning we simply focused on a single zone and finally made it to testing.

### Before drop

In lobby, remember to select the biotracker if you don't have mods that'll let you count and avoid enemies easier (you really should be using some though).

Before we drop in, we need to be ready for errors. We have 2 options here.

#### Option 1: Using bepinex console/UnityLogListening set to true

If bepinex console is enabled and unity log listening is enabled in bepinex config.

While dropping in, look at the console to check if you don't see tons of errors (red text) looping, meaning we've entered an infinite cage drop.

#### Option 2: No bepinex console/UnityLogListening set to false

This is if we can't see game logs in bepinex console.

Open the game logs folder `%userprofile%\AppData\LocalLow\10 Chambers Collective\GTFO` and locate the current log. Monitor it while dropping in. If the level generation fails, the latest log can start rapidly rising in size, meaning we entered an infinite error loop and will never finish cage drop.

#### Either way

If infinite cage drop happens, exit the game and relaunch after debugging and coming up with a fix. Exiting just the level _can_ work but we can't guarantee no after-effects will carry over to the next drop.

Even if we drop in successfully we'll check for exceptions to see if anything failed without causing infinite cage drop. During the whole testing process and after exiting the level you should still look at the logs to verify no errors appeared.

### After drop

Immediately upon dropping in and revealing the map I can something new at the right side of the map generated. Let's compare before/after.

![The level before adding the new zone](<../../.gitbook/assets/image (7).png>)

![The level after adding the new zone](<../../.gitbook/assets/image (9).png>)

We can see the map is the same apart from something new generated at the top right, which would be our zone. However, even without going in to test, it's clearly visible that the zone is not generated from the elevator zone. Verifying this we can see it generated from the zone to the right of elevator, and the source entry is to the north (forward):

![](<../../.gitbook/assets/image (26).png>)

Why did this happen?

There's no errors in the bepinex console and no particular errors in the game logs, but let's look closer.

```
Next Batch: GenerateZones - Count: 12

14:39:39.745 - <color=#C84800> ---- MainLayer ---- Picked build from area : Area_A</color>
14:39:39.808 - BlockAndCleanFailedAreasFromZone >  ZoneAlias: 102 dim:Reality  AreaCount: 1  ZoneCoverageOnFail:10  ZoneMinCoverage:40  CoverageStatus:NotEnough
14:39:40.490 - BlockAndCleanFailedAreasFromZone >  ZoneAlias: 111 dim:Reality  AreaCount: 1  ZoneCoverageOnFail:10  ZoneMinCoverage:65  CoverageStatus:NotEnough
14:39:40.491 - WARNING : Zone11 (Zone_11 - 111): Failed to find any good StartAreas in zone 0 (100) expansionType:Towards_Right m_buildFromZone.m_areas: 5 scoredCount:0 dim: Reality
14:39:40.491 - BlockAndCleanFailedAreasFromZone >  ZoneAlias: 111 dim:Reality  AreaCount: 5  ZoneCoverageOnFail:39  ZoneMinCoverage:65  CoverageStatus:NotEnough
14:39:40.491 - BlockAndCleanFailedAreasFromZone >  ZoneAlias: 111 dim:Reality  AreaCount: 1  ZoneCoverageOnFail:3  ZoneMinCoverage:65  CoverageStatus:NotEnough
14:39:40.552 - Last Batch: GenerateZones
```

The "BlockAndCleanFailedAreasFromZone" part is ok, it happens. I'm not an LG expert, but if I had to guess I'd say it either collided with other zones or ran out of plugs to connect areas.

Line 6 explains the cause. Zone 0 has nowhere to generate a security door so it moved on to another zone.

I'd say LG handled this well but we still need to fix it. A few options here:

* Expand the elevator zone - screw up the whole existing layout.
* Move source to zone 103 (right-most zone) - that is a fog zone and there are other balance shenanigans.
* Move source to zone 102 - this is what LG did.

Let's go with option 3. We should also change the entrance to north like LG generated because there's likely no entrance to generate on the right side, but we can still try that and see what happens. Spoilers - it still generated from the north. Let's go ahead and change both fields now:

```
          "BuildFromLocalIndex": 2,
          "StartExpansion": 1,
```

Here's our map now:

![Map after changing source zone](<../../.gitbook/assets/image (20).png>)

We can see it still generated in the same spot, as expected, and this time the layout of the zone is different. This is the exact same map as before changing entrance direction to north.

Time to explore.

### Exploring the zone

#### The layout

The zone is heading right indeed, it's above fog everywhere except in parts of the last room, which is the huge one so that's expected. The lighting is also as expected. Here's a view of the last room from its entrance:

![Zone 111 area F (the huge area - last room)](<../../.gitbook/assets/image (27).png>)

If it seems relatively dark, it's because I'm using the lights adjustment mod.

Two terminals generated, one near the middle, another at the very end.

Overall, I would say the layout is a great success.

#### The sleepers

24 total sleepers spawned - 2 big strikers, 1 scout, 11 strikers and 10 shooters. The spread is fair, only one area got 3 groups which is still very manageable. The spawns are very easy in this zone. I would say we can easily double the distribution here unless there's some special reason not to (like an error alarm), but we're not trying to balance the level. The spawns are all there, the count and spread is as expected. The sleepers part is successful.

#### The resources

10 uses of each spawned in various pack sizes. Right on target. If you get a bit more it might still be fine, because there's a base game bug where a resource pack spawns bigger than it should be.

With consumables we weren't going for anything special, so there's not much to verify apart from the fact that the usual stuff spawned.

We've seen everything and after leaving the level there are still no errors to see. We've successfully added a new zone.

## Editing existing zones

Unfortunately, we're still not done here. Out of the things we said we would do in the overview, we still have these to do: alarms, blood doors, spitters, respawns, a generator puzzle, a pitch black zone, and fog.

Might as well go for some sort of world record in page length.

Or speedrun the rest of these topics.

### Adding an alarm

Ah yes, the best difficulty filler in the game, abused on every single level. Even the error shenanigans in R4 are technically all alarms.

Alarms' enemies are defined by 2 different datablocks, one of them is just linking 5 roles to enemies (out of those 5, one is broken in base game and never spawns).

From level layout, there's only one field to change here, ChainedPuzzleToEnter. That is both for alarm and normal scans, without one set, we can just open the door without even team scanning.

[Chained puzzles](../../reference/datablocks/main/chainedpuzzle.md) use 3 other blocks:

* [SurvivalWaveSettings](../../reference/datablocks/main/survivalwavesettings.md) - the wave settings. Defines what, when, how many, and where;
* [SurvivalWavePopulation](../../reference/datablocks/main/survivalwavepopulation.md) - wave settings specify what roles can spawn, this block maps roles to enemies, making settings more reusable;
* [ChainedPuzzleTypeDataBlock](../../reference/datablocks/rarely-edited/chainedpuzzletype.md) - the types of scans, like full team, big, small, cluster etc. Mostly you just see the names and decide what scan to pick. I don't know any reason to edit this datablock.

Population ID 1 will give us striker in standard, shooter in special, and big striker in miniboss. As basic an alarm setup as it gets.

For settings let's make something new. Something the base game doesn't do for alarms.

```
    {
      "m_pauseBeforeStart": 0.0,
      "m_pauseBetweenGroups": 5.0,
      "m_wavePauseMin_atCost": 49.0,
      "m_wavePauseMax_atCost": 50.0,
      "m_wavePauseMin": 29.0,
      "m_wavePauseMax": 30.0,
      "m_populationFilter": [
        0
      ],
      "m_filterType": 1,
      "m_chanceToRandomizeSpawnDirectionPerWave": 1.0,
      "m_chanceToRandomizeSpawnDirectionPerGroup": 0.1,
      "m_overrideWaveSpawnType": false,
      "m_survivalWaveSpawnType": 0,
      "m_populationPointsTotal": 60.0,
      "m_populationPointsPerWaveStart": 30.0,
      "m_populationPointsPerWaveEnd": 30.0,
      "m_populationPointsMinPerGroup": 5.0,
      "m_populationPointsPerGroupStart": 5.0,
      "m_populationPointsPerGroupEnd": 10.0,
      "m_populationRampOverTime": 60.0,
      "name": "2 intense waves",
      "internalEnabled": true,
      "persistentID": 151
    }
  ],
  "LastPersistentID": 255
```

A little bit of analysis:

* Using LastPersistentID as a reminder wave settings can't go above 255.
* Wave pause settings set to basically enforce 30-ish seconds between waves. The little variation is because something bugs if min-max are equal.
* Population filter (with some help from base game boss bug) will allow only the 3 roles to spawn.
* The most notable thing here is the limited population. Combined with points per wave, we get exactly 2 waves, with group spawns being more intense on the 2nd wave.

This alarm should keep the players occupied for at least a minute and depending on their clearing power, not much longer than that.

Moving on to Chained puzzle:

```
    {
      "PublicAlarmName": "Geo Alarm",
      "TriggerAlarmOnActivate": true,
      "SurvivalWaveSettings": 151,
      "SurvivalWavePopulation": 1,
      "DisableSurvivalWaveOnComplete": false,
      "UseRandomPositions": true,
      "WantedDistanceFromStartPos": 0.0,
      "WantedDistanceBetweenPuzzleComponents": 1.0,
      "ChainedPuzzle": [
        {
          "PuzzleType": 33
        }
      ],
      "OnlyShowHUDWhenPlayerIsClose": false,
      "AlarmSoundStart": 3339129407,
      "AlarmSoundStop": 42633153,
      "name": "Geo alarm 2 waves",
      "internalEnabled": true,
      "persistentID": 165
    }
```

We're using the blocks we settled on. For scans, one type 33 - the geo scan (introduced in R6.5) (highly likely not to function well in a random geo, but let's try it) - should be enough and we're not disabling the waves when the scan is completed, so the players will have to kill the 2 full waves.

Now they could just cheese it by running away and mining wherever until the population runs out, but from my experience they don't do that:

1. Barely anybody even notices something out of the ordinary with spawns when they're made well. If they do, they don't realize the specifics.
2. People hate wasting time. Even with cheese they'd have to sit in a sustain full-team scan for a while doing absolutely nothing.

All that's left is to set `"ChainedPuzzleToEnter": 165` and test.

Unsurprisingly the geo scan is screwed up but it's mostly functional so it's fine. Moving on.

### Adding a blood door

{% hint style="warning" %}
As noted [here](../../reference/nested-types/activeenemywavedata.md), only hunter groups work properly for blood doors.
{% endhint %}

The new zone has suffered enough so let's leave it alone for now. Let's add a blood door to the zone left from the elevator - localIndex 1.

Setting up a blood door is fairly easy as long as you know your enemy groups. It's controlled by "ActiveEnemyWave" in level layout. Let's skip making hunter groups this time and just see what's in stock. I see "Hunter Easy Bullrush" in groups with ID 32. MaxScore 8 makes me guess it should be about 8 spawns, but it seems the cost is 2 in population so it's actually 4. Let's spawn one group on the door and 2 in the area for a total of 12 chargers:

```
      "ActiveEnemyWave": {
        "HasActiveEnemyWave": true,
        "EnemyGroupInfrontOfDoor": 32,
        "EnemyGroupInArea": 32,
        "EnemyGroupsInArea": 2
      },
```

A quick test here shows the predictions were spot on. On to the next topic.

### The rest

Spitters, respawns, a generator puzzle, a pitch black zone, fog - we've got 5 things left to do, and at this point I feel like we've had enough practice to tackle them without too many details.

#### Spitters

Spitters are static spawn enemies, controlled by "StaticSpawnDataContainers". This references [StaticSpawnDataBlock](../../reference/datablocks/rarely-edited/staticspawn.md), but it's rare to edit that directly in my experience. We can tackle just the level layout datablock after seeing that spitters are ID 1 in static spawns. Here's our block, placed in the first zone:

```
      "StaticSpawnDataContainers": [
        {
          "Count": 10,
          "DistributionWeightType": 1,
          "DistributionWeight": 1.0,
          "DistributionRandomBlend": 0.5,
          "DistributionResultPow": 2.0,
          "StaticSpawnDataId": 1,
          "FixedSeed": 0
        }
```

We're spawning just a few because I hate spitters. Most fields besides the ID and Count are for location randomization.

#### Respawns

Respawner sacks are also a static spawn I believe, but they seem to be a special one, you only set up enemy respawning and they'll spawn automatically. So let's do that, again placing them in the first zone because we hate everyone who plays our levels:

```
      "EnemyRespawning": true,
      "EnemyRespawnRequireOtherZone": true,
      "EnemyRespawnRoomDistance": 2,
      "EnemyRespawnTimeInterval": 10.0,
      "EnemyRespawnCountMultiplier": 1.0,
```

The fields are all straight-forward here, but as always you can check the datablock reference for explanations. We don't need any respawn exclusions here so we don't even need to have that field.

Now when we messed with expedition balancing we reduced the first zone's population to barely anything, and there will be few respawn sacks as well because of that. Still enough to verify it's there and respawn works though.

#### Generator puzzle

I was going to make a keycard puzzle but we already have that example in the early zones. And generators have a little optional trick - we can spawn cells using big pickups distribution instead of ZonePlacementData. Scientific research suggests that thanks to how markers are set up, we'll get more possible placements inside our zone using big pickups instead of zone placement.

In zone 0, set ForceBigPickupsAllocation to true and BigPickupDistributionInZone to 5. In zone 1, set PuzzleType to 2 and PlacementCount to 0.

Now the zone to the left of spawn should require a generator to be activated which spawns in its entrance zone, and in elevator zone we spawned a cell using big pickups.

#### Pitch black zone

This one's just a matter of light settings, and there already seem to be 2 settings for darkness. Let's go with 73 in zone 1.

#### Editing fog

This can't be set per zone, we can either edit the level's fog settings or setup some warden objective stuff. From rundown db we can see the level uses ID 90. We should copy that to a new persistent ID and set it, then edit the settings. But let's just edit ID 90 directly.

If we don't want to flip the balance of the level, we can only do something boring, which means we're flipping the balance of the level. Here are the new settings:

```
{
  "Enabled": true,
  "FogColor": {
    "a": 0.03137255,
    "r": 0.4392157,
    "g": 0.7529412,
    "b": 0.5176471
  },
  "FogDensity": 0.005,
  "FogAmbience": 0.0,
  "DensityNoiseDirection": {
    "x": 0.0,
    "y": -1.0,
    "z": 0.0,
    "magnitude": 1.0,
    "sqrMagnitude": 1.0
  },
  "DensityNoiseSpeed": 0.034,
  "DensityNoiseScale": 0.1,
  "DensityHeightAltitude": 5.05,
  "DensityHeightRange": 0.0,
  "DensityHeightMaxBoost": 0.0,
  "Infection": 0.03,
  "name": "Fog_lightest_White_low1_INFECTION_R6_B2",
  "internalEnabled": true,
  "persistentID": 90
},
```

Fog density has been increased, altitude moved way up to 5, range and max boost changed to 0. Now the fog is upside-down and cancer is in the high zones instead of low. Flip successful.

If you didn't test these 5 parts yet, now's the time. We're all done with the changes. Here's a picture where you can see the fog, generator, spitters, and respawners:

![Zone 0 showing the changes made](<../../.gitbook/assets/image (37).png>)

Bonus points if you get hit by a spitter as soon as you drop in.

## Afterword

I would like to thank all my fans, my mother, and everyone that supported me. I finally got to finish this damn page.

Jokes aside, we can finally move on to warden objective. That topic's not simple either but fortunately I just have to settle on one thing and I get to choose a simple objective.

## Extra

I mentioned typelist blocks before so I thought I'd throw in a few examples of how our blocks would look like then:

![Added zone build parameters](<../../.gitbook/assets/image (47).png>)

![Added zone sleeper spawns](<../../.gitbook/assets/image (15).png>)

![Added enemy groups](<../../.gitbook/assets/image (4).png>)

![Added survival settings](<../../.gitbook/assets/image (1).png>)
