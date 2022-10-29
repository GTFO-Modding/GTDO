---
description: >-
  We will be compiling our plugin for release, meaning that there will be no
  debugging options set up
---

# Compiling for release

First Click Build > Configuration Manager in Visual Studio

Then in the Configuration Manager window, change Active solution configuration from "Debug" to "Release", then click close

Next Click Build > Build Solution

{% hint style="info" %}
If you used the earlier project settings your plugin should now be created inside your r2modman profile
{% endhint %}

{% hint style="success" %}
You should now be able to launch your modded game and see in the BepInEx log our logged message
{% endhint %}
