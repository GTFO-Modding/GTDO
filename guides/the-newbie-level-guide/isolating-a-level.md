---
description: How to take a rundown and reduce it to one level
---

# Isolating a level

## Overview

This step isn't necessary (and in some ways it's better not to do this at all), but for learning purposes it's good to understand exactly what you'll be working with.

MTFO regenerates everything even in custom folders so you can't have just the datablock files you want to edit, but you can minimize the content in each of them. For this step, we're going to reduce the main blocks to exactly one level, specifically - rundown and level layout.

This also doubles as an exercise in using VS Code.

## Isolating blocks

### Setup

To start, make sure you have the current unedited blocks generated. If you've already made some changes, just backup the custom datablocks somewhere else and delete them from plugins folder, then launch and close the game.

Afterwards copy & paste the folder and rename it. You'll have something like this.

![Generated GameData and copied folder](<../../.gitbook/assets/image (19) (1) (2).png>)

{% hint style="warning" %}
MTFO will not load the gamedata\_ folder matching the current game version, but everything else is fair game. Make sure you only have the current version folder and one folder with the blocks to edit. MTFO can even choose to load from root plugins/ folder if there are json files in it.
{% endhint %}

Now open the plugins folder with VS Code.

![Context menu option to open with VS Code](<../../.gitbook/assets/image (41).png>)

### Deleting rundown blocks

Open rundown db and delete the headers.

![Headers selected to delete](<../../.gitbook/assets/image (43).png>)

{% hint style="info" %}
Headers have no impact on modded datablocks, deleting them is purely optional. They're used only by the devs in their editor tools.
{% endhint %}

Find the current rundown.

![Rundown 6.0 block](<../../.gitbook/assets/image (18) (1).png>)

Go to the start of the block, collapse it, and copy it.

![R6 block collapsed and selected to copy](<../../.gitbook/assets/image (12).png>)

Collapse all the blocks and delete them.

![Blocks collapsed and selected to delete](<../../.gitbook/assets/image (46).png>)

And finally, paste the copied rundown block and delete the comma at the end of it.

![R6 block pasted](<../../.gitbook/assets/image (42).png>)

### Deleting all but one level from the rundown

Now we only have one rundown and we need to keep only one level in it. Let's go with B2.

Collapse all the tier blocks.

![R6 tier blocks collapsed](<../../.gitbook/assets/image (31).png>)

Delete everything but B tier.

![R6 with only B tier](<../../.gitbook/assets/image (11).png>)

Confirm that the 2nd object in B tier is B2 "Contaminant" and collapse the tier blocks

![B Tier collapsed](<../../.gitbook/assets/image (23).png>)

Delete all but the 2nd block.

![B Tier with only B2 left](<../../.gitbook/assets/image (21).png>)

B2 has now become B1 and is the only level in the rundown.

{% hint style="info" %}
When rundown id is not 1, GTFO API ensures all levels are unlocked, we don't have to take care of that ourselves. Normally "Accessibility", "UnlockedByExpedition", and "CustomProgressionLock" would be involved in locking/unlocking the level.
{% endhint %}

### Deleting secondary layer

Contaminant is the only level in our rundown, but the level layout datablocks still have all the levels, and B2 still has a secondary layer. Let's _thoroughly_ remove the secondary layer.

![Contaminant with secondary layer removed. Pay attention to the red triangles next to line numbers.](<../../.gitbook/assets/image (29).png>)

### Deleting level layout blocks

Most of the work is done. We just have to find the correct level layout and delete the rest.

In the picture above you can see that `LevelLayoutData` is set to 162. That's our main layer level layout.

Open level layout db and find the correct block.

![R6B2 main layer level layout](<../../.gitbook/assets/image (6).png>)

Repeat the same process as for rundown block: collapse it, copy it, collapse all blocks, delete them, paste the copied block, delete the comma.

Remember VS Code has to process \~160k lines here so don't be too harsh if it lags a bit. Deleting at least a part of the blocks does have practical use here as VS Code and its plugins won't take time to load when editing huge files like this one.

You should now have around 1632 lines in this file (more if you didn't delete headers).

### Regarding changing rundown ID to 1

While this is not a necessary step anymore thanks to GTFO API, it was originally agreed with devs to change all custom rundowns' ID to 1.

In case you want to do that:

All you need to do is set `"persistentID": 1` on the rundown block. GameSetupDataBlock RundownIdToLoad should also be changed to 1, but that's again handled by GTFO API.

Note that this disables other GTFO API checks such as unlocking levels.

You can change level layout ID as well. If you do, remember to update the reference in rundown.

### Verifying

Remember to save everything.

Launch the game. You should now see only B1 in the rundown menu.

![R6.5 with only B2 Contaminant, now shown as B1.](<../../.gitbook/assets/image (44).png>)

Drop in the level. It should load just fine. If you have freecam or some other mods, you can use them to check what the level looks like more easily. See if anything has changed.

You should see some marker (all sorts of objects placed in the level, a whole different topic) placement differences, also the lack of the secondary layer.

Oh and we deleted the bulkhead key, controller, and the bulkhead door (which is now just a security door) from main layer. If you want to restore that, you can do so by copying over these 3 from the original gamedata\_ folder we kept as a backup:

* ZonesWithBulkheadEntrance - zones in same layer (main) that have bulkhead entrances
* BulkheadDoorControllerPlacements - where to place bulkhead door controllers. If a zone with a bulkhead entrance does not have a door controller, the entrance will not require a bulkhead key.
* BulkheadKeyPlacements - where to place bulkhead keys in the layer.

Make sure you restore the ones under `MainLayerData` and not secondary. You can also just copy the whole `MainLayerData` block.

Later sections of the guide will assume you restored these (or didn't delete them to begin with).

If you did actually restore and verify again, the terminal near the bulkhead might be near the zone door in front of the door controller now.

![Bulkhead zone new terminal location](<../../.gitbook/assets/image (32).png>)

~~You could also just ctrl+z enough to restore bulkhead changes in VS Code~~

The rundown and level layout blocks are cleaned up and we can move onto the 2nd step in the guide.
