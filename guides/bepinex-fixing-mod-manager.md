---
description: '"failed to start bepinex"/"preloader dll" please help'
---

# BepInEx - Fixing mod manager

The recent BepInEx update broke all existing mods and the mod manager. Updating mods is up to the plugin developers, and updating the mod manager is up to thunderstore reps. However, until the latter happens, there is a way to sort-of fix it manually.

The fix consists of 2 main steps:

1. Copy a specific dll in-place and rename it so the mod manager finds the file it wants
2. Override the launch parameters so the correct dll is loaded

Note that before you do these, you should create a new profile and install bepinex pack on it. Old profiles can have mixed files from old and new installations.

### Copying the dll

First, navigate to your profile folder - open your profile in the mod manager, open Settings, and find "Browse profile folder".

![Browse profile folder setting](<../.gitbook/assets/paveikslas (5).png>)

Click on it. File explorer should open in the profile folder.

Now navigate to `BepInEx\core` and find `BepInEx.Unity.IL2CPP.dll`. Copy-paste it in-place, and rename the copied dll to `BepInEx.IL2CPP.dll`. Your folder should now look something like this:

![Folder with dll copied](<../.gitbook/assets/paveikslas (7).png>)

While you're there, you can copy your current path from the file explorer.

![File explorer path selected to copy](<../.gitbook/assets/paveikslas (1).png>)

Now go back to the mod manager's Settings, scroll down, and open "Set launch parameters".

![Set launch parameters menu](<../.gitbook/assets/paveikslas (6).png>)

In there, you will need to set the correct dll path. The line will look something like this:\
`--doorstop-target-assembly "C:\Users\`USER`\AppData\Roaming\Thunderstore Mod Manager\DataFolder\GTFO\`PROFILE`\UpdateTest\BepInEx\core\BepInEx.Unity.IL2CPP.dll"`

Copy this line, paste it, and replace the path leading to the dll to the correct one for your user and profile. If you copied the path earlier, you can simply insert it in the correct part of the text in this line:

`--doorstop-target-assembly "\BepInEx.Unity.IL2CPP.dll"`

With that done, you should be good to go.

Also note that launch parameters persist between profiles, so you would need to adjust them every time you change profiles. You will also need to delete them when mod manager is updated.
