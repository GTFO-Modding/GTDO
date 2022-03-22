---
description: GameData_RundownDataBlock_bin.json
---

# Rundown

## Fields

#### "**UseTierUnlockRequirements**": **** _Boolean_

Whether or not to use unlock requirements for this rundown.

<details>

<summary>"ReqToReachTierB": <em>{</em><a href="../nested-types/rundowntierprogressiondata.md"><em>RundownTierProgressionData</em></a><em>}</em></summary>

#### _"_**MainSectors": **_**Int32**_

The amount of completed main sectors required to reach this tier.

#### "SecondarySectors": _Int32_

The amount of completed secondary sectors required to reach this tier.

#### "ThirdSectors": _Int32_

The amount of completed third sectors required to reach this tier.

#### "AllClearedSectors": _Int32_

The amount of "all clear" sectors required to reach this tier.

</details>

Progression data to reach tier B of the rundown.

<details>

<summary>"ReqToReachTierC": <em>{</em><a href="../nested-types/rundowntierprogressiondata.md"><em>RundownTierProgressionData</em></a><em>}</em></summary>

#### _"_**MainSectors": **_**Int32**_

The amount of completed main sectors required to reach this tier.

#### "SecondarySectors": _Int32_

The amount of completed secondary sectors required to reach this tier.

#### "ThirdSectors": _Int32_

The amount of completed third sectors required to reach this tier.

#### "AllClearedSectors": _Int32_

The amount of "all clear" sectors required to reach this tier.

</details>

Progression data to reach tier C of the rundown.

<details>

<summary>"ReqToReachTierD": <em>{</em><a href="../nested-types/rundowntierprogressiondata.md"><em>RundownTierProgressionData</em></a><em>}</em></summary>

#### _"_**MainSectors": **_**Int32**_

The amount of completed main sectors required to reach this tier.

#### "SecondarySectors": _Int32_

The amount of completed secondary sectors required to reach this tier.

#### "ThirdSectors": _Int32_

The amount of completed third sectors required to reach this tier.

#### "AllClearedSectors": _Int32_

The amount of "all clear" sectors required to reach this tier.

</details>

Progression data to reach tier D of the rundown.

<details>

<summary>"ReqToReachTierE": <em>{</em><a href="../nested-types/rundowntierprogressiondata.md"><em>RundownTierProgressionData</em></a><em>}</em></summary>

#### _"_**MainSectors": **_**Int32**_

The amount of completed main sectors required to reach this tier.

#### "SecondarySectors": _Int32_

The amount of completed secondary sectors required to reach this tier.

#### "ThirdSectors": _Int32_

The amount of completed third sectors required to reach this tier.

#### "AllClearedSectors": _Int32_

The amount of "all clear" sectors required to reach this tier.

</details>

Progression data to reach tier E of the rundown.

<details>

<summary>"StorytellingData": <em>{</em><a href="../nested-types/rundownstorytellingdata.md"><em>RundownStorytellingData</em></a><em>}</em></summary>

#### "Title": _{_[_LocalizedText_](../nested-types/localizedtext.md)_}_

No description provided.

#### "TextLog": _{_[_LocalizedText_](../nested-types/localizedtext.md)_}_

No description provided.

#### "TextLogPos":  _Vector2_

No description provided.

#### "Visuals": _{_[_RundownStorytellingVisualData_](../nested-types/rundownstorytellingvisualdata.md)_}_

No description provided.

#### "SurfaceIconPosition":  _Vector2_

No description provided.

#### "SurfaceDescription": _{_[_LocalizedText_](../nested-types/localizedtext.md)_}_

No description provided.

</details>

Data for title, visual, description, etc. of the rundown.

#### "**VanityItemLayerDropDataBlock**": _UInt32_

The id for the vanity item datablock for this rundown.

<details>

<summary>"TierA": [<a href="../nested-types/expeditionintierdata.md">ExpeditionInTierData</a>]</summary>

#### "HostIDSeed": _Int32_

No description provided.

#### "SessionSeed": _Int32_

No description provided.

#### "Enabled": _Boolean_

No description provided.

#### "Accessibility": [_eExpeditionAccessibility_](../enum-types.md#eexpeditionaccessibility)

No description provided.

#### "UnlockedByExpedition": {[_ExpeditionIndex_](../nested-types/expeditionindex.md)_}_

No description provided.

#### "CustomProgressionLock": {[_RundownTierProgressionData_](../nested-types/rundowntierprogressiondata.md)_}_

No description provided.

#### "Descriptive": {[DescriptiveData](../nested-types/descriptivedata.md)}

No description provided.

#### "Seeds": {[_BuildSeedData_](../nested-types/buildseeddata.md)_}_

No description provided.

#### "Expedition": {[_ExpeditionData_](../nested-types/expeditiondata.md)_}_

No description provided.

#### "VanityItemsDropData": {[_VanityItemsDropData_](../nested-types/vanityitemsdropdata.md)_}_

No description provided.

#### "LevelLayoutData": _UInt32_

No description provided.

#### "MainLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "SecondaryLayerEnabled": _Boolean_

No description provided.

#### "SecondaryLayout": _UInt32_

No description provided.

#### "BuildSecondaryFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "SecondaryLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "ThirdLayerEnabled": _Boolean_

No description provided.

#### "ThirdLayout": _UInt32_

No description provided.

#### "BuildThirdFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "ThirdLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "DimensionDatas": \[{[_DimensionInExpeditionData_](../nested-types/dimensioninexpeditiondata.md)_}]_

No description provided.

#### "SoundEventOnWarpToReality": _UInt32_

No description provided.

#### "SpecialOverrideData": {[_SpecialExpeditionOverridesData_](../nested-types/specialexpeditionoverridesdata.md)_}_

No description provided.

</details>

Expedition data for all levels in tier A of this rundown.

<details>

<summary>"TierB": [<a href="../nested-types/expeditionintierdata.md">ExpeditionInTierData</a>]</summary>

#### "HostIDSeed": _Int32_

No description provided.

#### "SessionSeed": _Int32_

No description provided.

#### "Enabled": _Boolean_

No description provided.

#### "Accessibility": [_eExpeditionAccessibility_](../enum-types.md#eexpeditionaccessibility)

No description provided.

#### "UnlockedByExpedition": {[_ExpeditionIndex_](../nested-types/expeditionindex.md)_}_

No description provided.

#### "CustomProgressionLock": {[_RundownTierProgressionData_](../nested-types/rundowntierprogressiondata.md)_}_

No description provided.

#### "Descriptive": {[DescriptiveData](../nested-types/descriptivedata.md)}

No description provided.

#### "Seeds": {[_BuildSeedData_](../nested-types/buildseeddata.md)_}_

No description provided.

#### "Expedition": {[_ExpeditionData_](../nested-types/expeditiondata.md)_}_

No description provided.

#### "VanityItemsDropData": {[_VanityItemsDropData_](../nested-types/vanityitemsdropdata.md)_}_

No description provided.

#### "LevelLayoutData": _UInt32_

No description provided.

#### "MainLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "SecondaryLayerEnabled": _Boolean_

No description provided.

#### "SecondaryLayout": _UInt32_

No description provided.

#### "BuildSecondaryFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "SecondaryLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "ThirdLayerEnabled": _Boolean_

No description provided.

#### "ThirdLayout": _UInt32_

No description provided.

#### "BuildThirdFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "ThirdLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "DimensionDatas": \[{[_DimensionInExpeditionData_](../nested-types/dimensioninexpeditiondata.md)_}]_

No description provided.

#### "SoundEventOnWarpToReality": _UInt32_

No description provided.

#### "SpecialOverrideData": {[_SpecialExpeditionOverridesData_](../nested-types/specialexpeditionoverridesdata.md)_}_

No description provided.

</details>

Expedition data for all levels in tier B of this rundown.

<details>

<summary>"TierC": [<a href="../nested-types/expeditionintierdata.md">ExpeditionInTierData</a>]</summary>

#### "HostIDSeed": _Int32_

No description provided.

#### "SessionSeed": _Int32_

No description provided.

#### "Enabled": _Boolean_

No description provided.

#### "Accessibility": [_eExpeditionAccessibility_](../enum-types.md#eexpeditionaccessibility)

No description provided.

#### "UnlockedByExpedition": {[_ExpeditionIndex_](../nested-types/expeditionindex.md)_}_

No description provided.

#### "CustomProgressionLock": {[_RundownTierProgressionData_](../nested-types/rundowntierprogressiondata.md)_}_

No description provided.

#### "Descriptive": {[DescriptiveData](../nested-types/descriptivedata.md)}

No description provided.

#### "Seeds": {[_BuildSeedData_](../nested-types/buildseeddata.md)_}_

No description provided.

#### "Expedition": {[_ExpeditionData_](../nested-types/expeditiondata.md)_}_

No description provided.

#### "VanityItemsDropData": {[_VanityItemsDropData_](../nested-types/vanityitemsdropdata.md)_}_

No description provided.

#### "LevelLayoutData": _UInt32_

No description provided.

#### "MainLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "SecondaryLayerEnabled": _Boolean_

No description provided.

#### "SecondaryLayout": _UInt32_

No description provided.

#### "BuildSecondaryFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "SecondaryLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "ThirdLayerEnabled": _Boolean_

No description provided.

#### "ThirdLayout": _UInt32_

No description provided.

#### "BuildThirdFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "ThirdLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "DimensionDatas": \[{[_DimensionInExpeditionData_](../nested-types/dimensioninexpeditiondata.md)_}]_

No description provided.

#### "SoundEventOnWarpToReality": _UInt32_

No description provided.

#### "SpecialOverrideData": {[_SpecialExpeditionOverridesData_](../nested-types/specialexpeditionoverridesdata.md)_}_

No description provided.

</details>

Expedition data for all levels in tier C of this rundown.

<details>

<summary>"TierD": [<a href="../nested-types/expeditionintierdata.md">ExpeditionInTierData</a>]</summary>

#### "HostIDSeed": _Int32_

No description provided.

#### "SessionSeed": _Int32_

No description provided.

#### "Enabled": _Boolean_

No description provided.

#### "Accessibility": [_eExpeditionAccessibility_](../enum-types.md#eexpeditionaccessibility)

No description provided.

#### "UnlockedByExpedition": {[_ExpeditionIndex_](../nested-types/expeditionindex.md)_}_

No description provided.

#### "CustomProgressionLock": {[_RundownTierProgressionData_](../nested-types/rundowntierprogressiondata.md)_}_

No description provided.

#### "Descriptive": {[DescriptiveData](../nested-types/descriptivedata.md)}

No description provided.

#### "Seeds": {[_BuildSeedData_](../nested-types/buildseeddata.md)_}_

No description provided.

#### "Expedition": {[_ExpeditionData_](../nested-types/expeditiondata.md)_}_

No description provided.

#### "VanityItemsDropData": {[_VanityItemsDropData_](../nested-types/vanityitemsdropdata.md)_}_

No description provided.

#### "LevelLayoutData": _UInt32_

No description provided.

#### "MainLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "SecondaryLayerEnabled": _Boolean_

No description provided.

#### "SecondaryLayout": _UInt32_

No description provided.

#### "BuildSecondaryFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "SecondaryLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "ThirdLayerEnabled": _Boolean_

No description provided.

#### "ThirdLayout": _UInt32_

No description provided.

#### "BuildThirdFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "ThirdLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "DimensionDatas": \[{[_DimensionInExpeditionData_](../nested-types/dimensioninexpeditiondata.md)_}]_

No description provided.

#### "SoundEventOnWarpToReality": _UInt32_

No description provided.

#### "SpecialOverrideData": {[_SpecialExpeditionOverridesData_](../nested-types/specialexpeditionoverridesdata.md)_}_

No description provided.

</details>

Expedition data for all levels in tier D of this rundown.

<details>

<summary>"TierE": [<a href="../nested-types/expeditionintierdata.md">ExpeditionInTierData</a>]</summary>

#### "HostIDSeed": _Int32_

No description provided.

#### "SessionSeed": _Int32_

No description provided.

#### "Enabled": _Boolean_

No description provided.

#### "Accessibility": [_eExpeditionAccessibility_](../enum-types.md#eexpeditionaccessibility)

No description provided.

#### "UnlockedByExpedition": {[_ExpeditionIndex_](../nested-types/expeditionindex.md)_}_

No description provided.

#### "CustomProgressionLock": {[_RundownTierProgressionData_](../nested-types/rundowntierprogressiondata.md)_}_

No description provided.

#### "Descriptive": {[DescriptiveData](../nested-types/descriptivedata.md)}

No description provided.

#### "Seeds": {[_BuildSeedData_](../nested-types/buildseeddata.md)_}_

No description provided.

#### "Expedition": {[_ExpeditionData_](../nested-types/expeditiondata.md)_}_

No description provided.

#### "VanityItemsDropData": {[_VanityItemsDropData_](../nested-types/vanityitemsdropdata.md)_}_

No description provided.

#### "LevelLayoutData": _UInt32_

No description provided.

#### "MainLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "SecondaryLayerEnabled": _Boolean_

No description provided.

#### "SecondaryLayout": _UInt32_

No description provided.

#### "BuildSecondaryFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "SecondaryLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "ThirdLayerEnabled": _Boolean_

No description provided.

#### "ThirdLayout": _UInt32_

No description provided.

#### "BuildThirdFrom": {[_BuildLayerFromData_](../nested-types/buildlayerfromdata.md)_}_

No description provided.

#### "ThirdLayerData": {[_LayerData_](../nested-types/layerdata.md)_}_

No description provided.

#### "DimensionDatas": \[{[_DimensionInExpeditionData_](../nested-types/dimensioninexpeditiondata.md)_}]_

No description provided.

#### "SoundEventOnWarpToReality": _UInt32_

No description provided.

#### "SpecialOverrideData": {[_SpecialExpeditionOverridesData_](../nested-types/specialexpeditionoverridesdata.md)_}_

No description provided.

</details>

Expedition data for all levels in tier E of this rundown.

