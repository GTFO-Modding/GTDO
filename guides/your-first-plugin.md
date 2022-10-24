---
description: 'Or: "How I learned to hate IL2cpp"'
---

# 👶 Your First Plugin

## Preface
{% hint style="info" %}
A Plugin is a compiled C# assembly file that is loaded by BepInEx to allow for custom code to be executed, such as patches or custom behaviour
{% endhint %}
{% hint style="danger" %}
This guide assumes you are running windows 10 or 11, own GTFO on steam, and have r2modman installed
{% endhint %}
In this guide we will go over the following
1. Setting up Visual Studio Community
2. Creating a C# class library project
3. Writing a EntryPoint class
4. Compiling for release

## Setting up Visual Studio Community

{% hint style="info" %}
Visual Studio Community allows you to navigate, edit and compile code.
{% endhint %}
1. Download Visual Studio [here](https://visualstudio.microsoft.com/downloads/) by clicking "Free Download" underneath the Community section
2. Run "VisualStudioSetup.exe" from your download folder
3. Continue through the process until you get to the "Installing" window with the "Workloads" tab
4. Under the "Desktop & Mobile" section select ".NET desktop development"
5. Under the "Gaming" section select "Game development with Unity"
6. Once you have your preferred components selected click "Install" on the bottom right
7. Wait for the heat death of the universe until your IDE is installed
8. Continue through the rest of the set up until a "Get started" window appears
{% hint style="info" %}
Signing in to Visual Studio is optional
{% endhint %}
{% hint style="success" %}
You should now be ready to create your C# class library project
{% endhint %}

## Creating a C# class library project

{% hint style="info" %}
When Visual Studio first opens you are shown a Get started window. From here you can open your recent projects, clone github repositories, or create a new project.
{% endhint %}
{% hint style="info" %}
We will be creating a Library project written in C# targetting all platforms
{% endhint %}
First create a new project and choose "Class Library" - "A project for creating a class library that targets .NET or .NET Standard"
Then write a name into the Project name field, such as "MyFirstPlugin" and then click "Next"
Next ensure you have ".NET 6.0 (Long-term support)" selected as your Framework and click "Create"
{% hint style="info" %}
When the project is finished creating you should see "Class1.cs" open
{% endhint %}
Click Project > Edit Project File and replace it with the following
{% hint style="danger" %}
The following project settings assume you have r2modman installed in the default location with BepInEx installed and run at least once
{% endhint %}
{% hint style="info" %}
You can change the BepInEx path to your preferred location by editing the BepInEx property within PropertyGroup
{% endhint %}
```xml
<Project Sdk="Microsoft.NET.Sdk">
	<PropertyGroup>
		<TargetFramework>net6.0</TargetFramework>
		<Version>1.0.0</Version>
		<AssemblyName>$(SolutionName).Il2Cpp.CoreCLR</AssemblyName>
		<BepInEx>$(AppData)\r2modmanPlus-local\GTFO\profiles\Default\BepInEx</BepInEx>
		<BuildDirectory>$(BepInEx)\plugins\$(SolutionName)\</BuildDirectory>
		<OutputPath>$(BuildDirectory)</OutputPath>
		<AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
		<DebugType>None</DebugType>
	</PropertyGroup>
	<Target Name="PostBuild" BeforeTargets="PostBuildEvent">
		<Exec Command="del $(OutputPath)$(AssemblyName).deps.json" />
	</Target>
	<ItemGroup>
		<!-- NuGet packages -->
		<PackageReference Include="HarmonyX" Version="2.10.0" IncludeAssets="compile" />
		<PackageReference Include="Il2CppInterop.Common" Version="1.3.0" />
		<PackageReference Include="Il2CppInterop.Runtime" Version="1.3.0" />
		<!-- Interop assemblies -->
		<Reference Include="$(BepInEx)\interop\*.dll" Private="false" />
		<Reference Remove="$(BepInEx)\interop\netstandard.dll" />
		<Reference Remove="$(BepInEx)\interop\Newtonsoft.Json.dll" />
		<!-- BepInEx assemblies -->
		<Reference Include="$(BepInEx)\core\BepInEx.*.dll" Private="false" />
	</ItemGroup>
</Project>
```
Finally save the changes to the csproj file
{% hint style="success" %}
You should now be ready to create your EntryPoint class
{% endhint %}

## Writing a EntryPoint class

{% hint style="info"%}
The following EntryPoint class will allow BepInEx to load and handle your compiled assembly like a plugin
{% endhint %}
Right click "Class1.cs" in the solution explorer and rename it to "EntryPoint". Choose "Yes" to rename all references
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
Save your changes by doing File > Save EntryPoint.cs
{% hint style="success" %}
You should now be ready to compile your first plugin
{% endhint %}

## Compiling for release

{% hint style="info" %}
We will be compiling our plugin for release, meaning that there will be no debugging options set up
{% endhint %}
First Click Build > Configuration Manager in Visual Studio
Then In the Configuration Manager window, change Active solution configuration from "Debug" to "Release", then click close
Next Click Build > Build Solution
{% hint style="info" %}
If you used the earlier project settings your plugin should now be created inside your default r2modman profile
{% endhint %}
{% hint style="success" %}
You should now be able to launch your Default modded profile and see in the BepInEx log our "Hello world" message!
{% endhint %}
