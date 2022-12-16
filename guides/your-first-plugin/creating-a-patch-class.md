---
description: >-
  The following Patch class will use HarmonyX to allow us to modify how GTFO
  behaves
---

# Creating a Patch class

First, in Visual Studio, click Project > Add Class and change Class1.cs to Patch.cs

Next replace the pre-generated code with the following

```csharp
using CellMenu;
using HarmonyLib;
using UnityEngine;
using UnityEngine.Diagnostics;

namespace MyFirstPlugin;

internal static class Patch
{
    [HarmonyPatch(typeof(CM_PageRundown_New), nameof(CM_PageRundown_New.Setup))]
    [HarmonyPostfix]
    public static void MyPatch(CM_PageRundown_New __instance)
    {
        __instance.m_aboutTheRundownButton.OnBtnPressCallback = (Action<int>)((_) => { Application.ForceCrash((int)ForcedCrashCategory.Abort); });
    }
}

```

After that go back to our Plugin class and add the following line to your Load method

```csharp
_ = Harmony.CreateAndPatchAll(typeof(Patch), "MyFirstPlugin");
```

You can now compile the plugin and when you click the About Rundown button in-game you will unlock a new rundown

#### Explaining how this works

When the plugin loads it will create a Harmony instance and apply our patch using the attributes we gave to the MyPatch method. When an object of CM\_PageRundown\_New calls the Setup method our code will be executed. Our patch replaces the action of the about rundown button with our own code.

{% hint style="danger" %}
If multiple patch classes are desired first create a harmony instance and then use the types
{% endhint %}

```csharp
var harmony = new Harmony("MyFirstPlugin");
harmony.PatchAll(typeof(RundownPatch));
harmony.PatchAll(typeof(PlayerPatch));
harmony.PatchAll(typeof(EnemyPatch));
```

{% hint style="info" %}
To find more information on how to use HarmonyX please reference their [Github Wiki](https://github.com/BepInEx/HarmonyX/wiki)
{% endhint %}
