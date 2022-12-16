---
description: How to set up your project for editing and compiling
---

# Creating a C# class library project

{% hint style="info" %}
We will be creating a Library project written in C# targeting all platforms
{% endhint %}

First create a new project and choose "Class Library" - "A project for creating a classlibrary that targets .NET or .NET Standard"

Then write a name into the Project name field, such as "MyFirstPlugin" and click "Next"

Next ensure you have ".NET 6.0 (Long-term support)" selected as your Framework and click "Create"

{% hint style="info" %}
When the project is finished creating you should see "Class1.cs" open
{% endhint %}

Click Project > Edit Project File and replace it with the following

{% hint style="warning" %}
The following project settings assume you have r2modman installed in the Default location with BepInEx installed and run at least once
{% endhint %}

{% hint style="info" %}
You can change which r2modman profile is used by editing the Profile property\
\
Additionally, you can also change the BepInEx path to your preferred location by editing the BepInEx property
{% endhint %}

```xml
<Project Sdk="Microsoft.NET.Sdk">
	<PropertyGroup>

		<!--
		Use the following property to set your preferred r2modman profile
		-->
		<Profile>Default</Profile>

		<TargetFramework>net6.0</TargetFramework>
		<ImplicitUsings>enable</ImplicitUsings>
		<Nullable>enable</Nullable>
		<DebugType>None</DebugType>
		<AssemblyName>$(SolutionName)</AssemblyName>
		<RootNamespace>$(SolutionName)</RootNamespace>
		<BepInEx>$(AppData)\r2modmanPlus-local\GTFO\profiles\$(Profile)\BepInEx</BepInEx>
		<BuildDirectory>$(BepInEx)\plugins\$(SolutionName)\</BuildDirectory>
		<OutputPath>$(BuildDirectory)</OutputPath>	
		<AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
	</PropertyGroup>
	<Target Name="PostBuild" BeforeTargets="PostBuildEvent">
		<Delete Files="$(OutputPath)$(AssemblyName).deps.json" />
	</Target>
	<ItemGroup>
		<Reference Include="$(BepInEx)\core\0Harmony.dll" Private="false" />
		<Reference Include="$(BepInEx)\core\BepInEx.Core.dll" Private="false" />
		<Reference Include="$(BepInEx)\core\BepInEx.Unity.IL2CPP.dll" Private="false" />
		<Reference Include="$(BepInEx)\core\Il2CppInterop.Common.dll" Private="false" />
		<Reference Include="$(BepInEx)\core\Il2CppInterop.Runtime.dll" Private="false" />
		<Reference Include="$(BepInEx)\interop\*.dll" Private="false" />
		<Reference Remove="$(BepInEx)\interop\netstandard.dll" />
	</ItemGroup>
</Project>
```

Finally save the changes to the csproj file

{% hint style="success" %}
You should now be ready to create your Plugin class
{% endhint %}
