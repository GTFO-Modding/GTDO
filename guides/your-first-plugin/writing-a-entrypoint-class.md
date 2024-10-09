---
description: >-
  The following Plugin class will allow BepInEx to load and handle your compiled
  assembly as a plugin
---

# Writing a Plugin class

In Visual studio right click "Class1.cs" in the solution explorer and rename it to "Plugin.cs". Choose "Yes" to rename all references

{% hint style="info" %}
If you do not have a Class1.cs you can create Plugin.cs instead by choosing Project > Add Class...
{% endhint %}

Copy and paste the following code into "Plugin.cs" replacing the entire contents of the file

{% hint style="info" %}
If you do not see where to paste the code into, double click the Plugin.cs file in the solution explorer
{% endhint %}

```csharp
using BepInEx;
using BepInEx.Unity.IL2CPP;

namespace MyFirstPlugin;

[BepInPlugin("NewbiePluginAuthor.MyFirstPlugin", "MyFirstPlugin", "1.0.0")]
public class Plugin : BasePlugin
{
    public override void Load()
    {
        // Plugin startup logic
        Log.LogInfo("MyFirstPlugin is loaded!");
    }
}
```

Save your changes by selecting File > Save Plugin.cs

{% hint style="success" %}
You should now be ready to compile your first plugin
{% endhint %}

#### Explaining how this work

We create a new class that inherits from the BepInEx BasePlugin class. We give this new class a special _attribute_ (the `BepInPlugin` thing above the class) which BepInEx uses to make this class into a full-fledged plugin. The arguments we supply to the attribute include:

* The GUID: `"NewbiePluginAuthor.MyFirstPlugin"`\
  This is an identifier which should uniquely identify the plugin. Typically just `author.pluginname` should suffice.
* The plugin name: `"MyFirstPlugin"`
* The plugin version: `"1.0.0"`\
  This uses [semantic versioning](https://semver.org/).
