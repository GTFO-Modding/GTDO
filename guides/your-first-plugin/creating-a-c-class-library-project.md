---
description: How to set up your project for editing and compiling
---

# Creating a C# class library project

{% hint style="info" %}
We will be creating a Library project written in C# targetting all platforms
{% endhint %}

First create a new project and choose "Class Library" - "A project for creating a classlibrary that targets .NET or .NET Standard"

Then write a name into the Project name field, such as "MyFirstPlugin" and click "Next"

Next ensure you have ".NET 6.0 (Long-term support)" selected as your Framework and click "Create"

{% hint style="info" %}
When the project is finished creating you should see "Class1.cs" open
{% endhint %}

Click Project > Edit Project File and replace it with the following

{% hint style="warning" %}
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
