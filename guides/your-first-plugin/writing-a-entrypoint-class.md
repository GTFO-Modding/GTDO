---
description: >-
  The following EntryPoint class will allow BepInEx to load and handle your
  compiled assembly like a plugin
---

# Writing a EntryPoint class

In Visual studio right click "Class1.cs" in the solution explorer and rename it to "EntryPoint.cs". Choose "Yes" to rename all references

{% hint style="info" %}
If you do not have a Class1.cs you can create EntryPoint.cs instead by choosing Project > Add Class...
{% endhint %}

Copy and paste the following code into "EntryPoint.cs" replacing the entire contents of the file

{% hint style="info" %}
If you do not see where to paste the code into, double click the EntryPoint.cs file in the solution explorer
{% endhint %}

```csharp
using BepInEx;
using BepInEx.Unity.IL2CPP;

namespace MyFirstPlugin
{
    [BepInPlugin("MyFirstPlugin", "My First Plugin", "1.0.0")]
    public class EntryPoint : BasePlugin
    {
        public override void Load()
        {
            Log.LogInfo("Hello world");
        }
    }
}
```

Save your changes by selecting File > Save EntryPoint.cs

{% hint style="success" %}
You should now be ready to compile your first plugin
{% endhint %}
