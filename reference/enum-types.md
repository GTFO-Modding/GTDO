---
description: A list of every enum type related to the game's Datablocks
---

# Enum Types

No description provided.

***

## Enums

### AbilityCondition

* None - 0
* BossPhase0 - 1
* BossPhase1 - 2
* BossPhase2 - 3
* BossPhase3 - 4
* BossPhase4 - 5
* BossPhase5 - 6
* BossStateCombat - 11
* BossStateSpawn - 12
* BossStateRage - 13
* BossStateIntro - 14

### AgentAbility

* None - 0
* Melee - 1
* Ranged - 2
* Alarm - 3
* Defensive - 4
* Healing - 5
* GroupEnhance - 6
* Detection - 7
* DoorBreaker - 8
* SpawnChildren - 9

### AgentMode

* Off - 0
* Agressive - 1
* Patrolling - 2
* Scout - 3
* Hibernate - 4

### AgentModifier

* None - 0
* RegenerationCap - 1
* RegenerationSpeed - 2
* HealSupport - 3
* ReviveSpeedSupport - 4
* ReviveStartHealthSupport - 5
* MeleeResistance - 6
* ProjectileResistance - 7
* InfectionResistance - 8
* PistolDamage - 50
* SMGDamage - 51
* DMRDamage - 52
* AssaultRifleDamage - 53
* CarbineDamage - 54
* AutoPistolDamage - 55
* HELDamage - 56
* ShotgunDamage - 58
* RevolverDamage - 59
* SniperDamage - 60
* BurstCannonDamage - 61
* MachineGunDamage - 62
* MachinePistolDamage - 63
* RifleDamage - 64
* BurstRifleDamage - 65
* DoubleTapRifle - 66
* BullpupRifleDamage - 67
* CombatShotgunDamage - 68
* ChokeModShotgunDamage - 69
* StandardWeaponDamage - 70
* SpecialWeaponDamage - 71
* GlueStrength - 100
* GlueEfficiency - 101
* SentryGunSpeed - 102
* SentryGunDamage - 103
* SentryGunLongRangeDamage - 104
* SentryGunShortRangeDamage - 105
* TripMineDamage - 106
* ScannerRechargeSpeed - 107
* AmmoSupport - 108
* HackingProficiency - 150
* ComputerProcessingSpeed - 151
* InitialAmmoStandard - 152
* InitialAmmoSpecial - 153
* InitialAmmoTool - 154
* FogRepellerEffect - 155
* GlowstickEffect - 156
* BioscanSpeed - 157
* MeleeDamage - 200

### AnimatorControllerHandleName

* Unspecified - 1
* EnemyCripple - 2
* EnemyRunner - 4
* EnemyFiddler - 8
* EnemyLow - 16
* EnemyCrawlFlip - 32
* EnemyCrawl - 64
* EnemyGiant - 128
* EnemyBig - 256
* EnemyExploder - 512
* EnemyBirtherCrawlFlip - 1024

### ArtifactCategory

* Common - 0
* Uncommon - 1
* Rare - 2
* _COUNT - 3

### ArtifactTags

* None - 0
* Corpse - 1
* Ground - 2
* Shelf - 4
* DigSite - 8
* Refinery - 16
* Storage - 32
* DataCenter - 64
* Lab - 128
* Floodways - 256
* AllComplex - 504
* Any - 4294967295

### AssetBundleName

* None - 0
* Complex_Shared - 1
* Complex_Mining - 2
* Complex_Tech - 3
* Complex_Service - 4
* Startup - 5
* Gear_Weapon_Front - 20
* Gear_Weapon_Receiver - 30
* Gear_Weapon_Stock - 40
* Gear_Weapon_Sight - 50
* Gear_Weapon_Mag - 60
* Gear_Weapon_Flashlight - 70
* Gear_Tool_Main - 80
* Gear_Tool_Grip - 90
* Gear_Tool_Delivery - 100
* Gear_Tool_Payload - 110
* Gear_Tool_Targeting - 120
* Gear_Tool_Screen - 130
* Gear_Melee_Head - 140
* Gear_Melee_Neck - 150
* Gear_Melee_Handle - 160
* Gear_Melee_Pommel - 170
* Gear_Material - 200
* Enemies - 300

### AssetBundleShard

* S1 - 0
* S2 - 1
* S3 - 2
* S4 - 3
* S5 - 4
* S6 - 5
* S7 - 6
* S8 - 7
* S9 - 8
* S10 - 9
* S11 - 10
* S12 - 11
* S13 - 12
* S14 - 13
* S15 - 14
* S16 - 15
* S17 - 16
* S18 - 17
* S19 - 18
* S20 - 19

### BoosterCondition

* None - 0
* IsInBioscan - 1
* IsOutsideBioscan - 2
* HasFullHealth - 3
* IsInFogRepellerRadius - 4
* IsNextToTeammate - 5
* IsLastManStanding - 6
* IsNextToGlowstick - 7
* HasFlashlightOff - 8
* HasFlashlightOn - 9
* IsCloseToEnemy - 10
* IsFarAwayFromEnemy - 11
* IsWieldingStandardWeapon - 12
* IsWieldingSpecialWeapon - 13
* IsWieldingTool - 14
* IsWieldingMelee - 15
* IsWieldingConsumable - 16
* IsWieldingResourcePack - 17
* IsWieldingHackingTool - 18
* IsWieldingCarryItem - 19
* HasLowHealth - 20
* HasHighHealth - 21
* HasLessThanAmmoSmall - 120
* HasMoreThanAmmoLarge - 132
* IsTeamAliveTwo - 140
* IsTeamAliveThree - 141
* IsTeamAliveFour - 142

### BoosterEffectCategory

* InitialState - 0
* Damage - 1
* Health - 2
* ProcessingSpeed - 3
* Tool - 4

### BoosterImplantCategory

* Muted - 0
* Bold - 1
* Aggressive - 2
* _COUNT - 3

### ClothesType

* Helmet - 0
* Torso - 1
* Legs - 2
* Backpack - 3
* Palette - 4
* Face - 5

### Complex

* Mining - 0
* Service - 1
* Tech - 2

### Crosshair

* None - 0
* Neutral - 1
* AssaultRifle - 2
* Shotgun - 3
* Keypad - 4
* Circle - 5

### DamageNoiseLevel

* Normal - 0
* Low - 1

### DialogCharFilter

* None - 1
* Char_G - 2
* Char_T - 4
* Char_F - 8
* Char_O - 16

### DialogCondition

* IsClose - 0
* IsVeryClose - 1
* IsFarAway - 2
* HasFlashlight - 100
* HasMapper - 101
* HasScanner - 102
* HasGlueGun - 103
* HasLockCutter - 104
* HeavylyArmed - 105
* LowAmmo - 200
* PlentyAmmo - 201

### DialogPriority

* IdleTalk - 0
* PersonalEvent - 100
* TeamEvent - 200
* CombatEvent - 300

### DialogProbability

* None - 0
* Low - 25
* Medium - 50
* High - 75
* Always - 100

### DialogTensionLimit

* Low - 0
* Medium - 1
* High - 2

### DialogTriggerInterval

* Unlimited - 0
* ShortCooldown - 1
* MediumCooldown - 2
* LongCooldown - 3
* OncePerSegment - 4
* OncePerExpedition - 5

### DimensionObjectiveType

* Ignore - 0
* LinkedToLayer - 1
* Independent - 2

### eBuildAutoExpeditionNumber

* Exp1 - 0
* Exp2 - 1
* Exp3 - 2
* Exp4 - 3
* Exp5 - 4
* Exp6 - 5
* Exp7 - 6

### eCommodityPackSize

* Small - 0
* Medium - 1
* Large - 2

### eCommodityType

* Artifact - 0
* PhysicalSample - 1
* LiquidSample - 2
* Data - 3

### eDimensionIndex

* Reality - 0
* Dimension_1 - 1
* Dimension_2 - 2
* Dimension_3 - 3
* Dimension_4 - 4
* Dimension_5 - 5
* Dimension_6 - 6
* Dimension_7 - 7
* Dimension_8 - 8
* Dimension_9 - 9
* Dimension_10 - 10
* Dimension_11 - 11
* Dimension_12 - 12
* Dimension_13 - 13
* Dimension_14 - 14
* Dimension_15 - 15
* Dimension_16 - 16
* Dimension_17 - 17
* Dimension_18 - 18
* Dimension_19 - 19
* Dimension_20 - 20
* MAX_COUNT - 21
* ARENA_DIMENSION - 22

### eEnemyFilterType

* Include - 0
* Exclude - 1

### eEnemyGroupType

* Hibernate - 0
* PureSneak - 1
* Detect - 2
* PureDetect - 3
* Patrol - 4
* Awake - 5
* Hunter - 6

### eEnemyRole

* Melee - 0
* Ranged - 1
* Tank - 2
* Lurker - 3
* PureSneak - 4
* Scout - 5
* Patroller - 6
* Hunter - 7
* BirtherChild - 8
* MiniBoss - 9
* Boss - 10

### eEnemyRoleDifficulty

* Easy - 0
* Medium - 1
* Hard - 2
* MiniBoss - 3
* Boss - 4
* MegaBoss - 5
* Biss - 6
* Buss - 7

### eEnemyRoleDistribution

* None - 0
* Force_One - 1
* Rel_25 - 2
* Rel_50 - 3
* Rel_75 - 4
* Rel_100 - 5
* Rel_15 - 6
* Rel_10 - 7
* Rel_05 - 8

### eEnemyType

* Weakling - 0
* Standard - 1
* Special - 2
* MiniBoss - 3
* Boss - 4

### eEnemyZoneDistribution

* None - 0
* Force_One - 1
* Rel_Value - 2

### eESALightsEffectScope

* CurrentArea - 0
* CurrentZone - 1

### eExpeditionAccessibility

* Normal - 0
* AlwayBlock - 1
* AlwaysAllow - 2
* BlockedAndScrambled - 3
* UseCustomProgressionLock - 4
* UnlockedByExpedition - 5

### eExtractionEventType

* EnemyWaveSpawn - 0
* ElevatorBioscan - 1
* ThickFog - 2
* LightsOff - 3
* LightsOn - 4
* RemoveAir - 5

### eFPISTransitionTime

* Quick - 0
* Slow - 1

### eFullbodyPlayerMovementSet

* Rifle - 0
* Pistol - 1
* Melee - 2
* CarryHeavy - 3
* Knife - 4
* Spear - 5

### eGameEvent

* None - 0
* player_enter_new_area - 1
* player_enter_new_zone - 2
* player_hacking_start - 3
* player_hacking_success - 4
* player_pickup_medikit - 5
* player_apply_medikit - 6
* player_pickup_ammokit - 7
* player_apply_ammokit - 8
* player_apply_disinfection - 9
* player_pickup_artifact - 10
* player_enter_terminal - 11
* player_exit_terminal - 12
* player_take_damage - 13
* player_take_friendly_fire - 14
* player_downed - 15
* player_revived - 16
* player_revived_2_total - 17
* player_revived_3_total - 18
* player_start_firing - 19
* player_stop_firing - 20
* player_fire_bullet - 21
* player_fire_glue - 22
* player_place_tripmine - 23
* player_place_sentrygun - 24
* enemy_scout_dead_from_melee - 25
* enemy_dead_from_melee - 26
* sticky_mine_explode - 27
* sentry_gun_fire - 28
* sentry_gun_ammo_depleated - 29
* weak_door_opening - 30
* weak_door_closing - 31
* weak_door_punched - 32
* weak_door_explode - 33
* security_door_opening - 34
* bioscan_start - 35
* bioscan_end - 36
* hibernating_enemy_spotted - 37
* hibernating_enemy_heartbeat - 38
* hibernating_enemy_wakeup - 39
* hibernating_enemy_dead - 40
* enemy_spotted - 41
* scout_enemy_spotted - 42
* scout_enemy_use_detect_ability - 43
* scout_enemy_found_player - 44
* scout_enemy_dead - 45
* enemy_striker_attack - 46
* enemy_shooter_attack - 47
* enemy_dead - 48
* enemy_big_attack - 49
* player_low_health - 50
* player_out_of_ammo_current_gear - 51
* player_out_of_ammo_all_gear - 52
* player_reload - 53
* player_revive_start - 54
* enemy_wave_spawned - 55
* player_downed_2_total - 56
* player_downed_3_total - 57
* player_downed_4_total - 58
* player_pickup_toolRefill - 59
* player_apply_toolRefill - 60
* player_pickup_commoditySmall - 61
* player_pickup_commodityMedium - 62
* player_pickup_commodityLarge - 63
* player_pickup_consumable - 64
* player_pickup_keycard - 65
* gs_Startup - 66
* gs_Offline - 67
* gs_NoLobby - 68
* gs_Lobby - 69
* gs_Slim - 70
* gs_FakeLobby - 71
* gs_Generating - 72
* gs_ReadyToStopElevatorRide - 73
* gs_StopElevatorRide - 74
* gs_ReadyToStartLevel - 75
* gs_InLevel - 76
* gs_AfterLevel - 77
* gs_CaptureRecall - 78
* gs_ExpeditionFail - 79
* gs_ExpeditionSuccess - 80
* gs_ExpeditionAbort - 81
* game_quit - 82
* term_Help - 83
* term_Commands - 84
* term_Cls - 85
* term_Exit - 86
* term_Open - 87
* term_Close - 88
* term_Activate - 89
* term_Deactivate - 90
* term_EmptyLine - 91
* term_InvalidCommand - 92
* term_DownloadData - 93
* term_ViewSecurityLog - 94
* term_Override - 95
* term_DisableAlarm - 96
* term_ActivateBeacon - 97
* term_Find - 98
* term_ShowList - 99
* term_Query - 100
* term_Locate - 101
* term_Ping - 102
* wobj_FindLocationInfo - 103
* wobj_FindLocationInfoHelp - 104
* wobj_GoToZone - 105
* wobj_GoToZoneHelp - 106
* wobj_InZoneFindItem - 107
* wobj_InZoneFindItemHelp - 108
* wobj_SolveItem - 109
* wobj_SolveItemHelp - 110
* wobj_GoToWinCondition - 111
* wobj_GoToWinConditionHelp - 112
* time_InLevel_0 - 113
* time_InLevel_5 - 114
* time_InLevel_15 - 115
* time_InLevel_30 - 116
* time_InLevel_45 - 117
* time_InLevel_60 - 118
* time_InLevel_90 - 119
* time_InLevel_120 - 120
* time_InLevel_150 - 121
* time_InLevel_180 - 122
* time_InLevel_210 - 123
* time_InLevel_240 - 124
* checkpoint_reload - 125

### eGearComponent

* None - 0
* FireMode - 1
* Category - 2
* BaseItem - 3
* ItemFPSSettings - 4
* AudioSetting - 5
* MuzzleFlash - 6
* ShellCasing - 7
* Pattern - 8
* Palette - 9
* DecalA - 10
* DecalB - 11
* FrontPart - 12
* FrontPartAttachmentA - 13
* FrontPartAttachmentB - 14
* FrontPartPerk - 15
* ReceiverPart - 16
* ReceiverPartAttachment - 17
* ReceiverPartPerk - 18
* StockPart - 19
* StockPartPerk - 20
* SightPart - 21
* SightPartPerk - 22
* MagPart - 23
* MagPartPerk - 24
* FlashlightPart - 25
* FlashlightPartPerk - 26
* ToolMainPart - 27
* ToolMainPartPerk - 28
* ToolMainPartAttachment - 29
* ToolGripPart - 30
* ToolGripPartPerk - 31
* ToolDeliveryType - 32
* ToolDeliveryPart - 33
* ToolDeliveryPartPerk - 34
* ToolDeliveryPartAttachment - 35
* ToolPayloadType - 36
* ToolPayloadPart - 37
* ToolPayloadPartPerk - 38
* ToolTargetingType - 39
* ToolTargetingPart - 40
* ToolTargetingPartPerk - 41
* ToolScreenPart - 42
* ToolScreenPartPerk - 43
* MeleeHeadPart - 44
* MeleeHeadPartPerk - 45
* MeleeNeckPart - 46
* MeleeNeckPartPerk - 47
* MeleeHandlePart - 48
* MeleeHandlePartPerk - 49
* MeleePommelPart - 50
* MeleePommelPartPerk - 51
* PlatformPerkAID - 52
* PlatformPerkBID - 53
* PlatformPerkCID - 54

### eGearPartAlign

* Muzzle - 0
* ShellEject - 1
* Magazine - 2
* Sight - 4
* Flashlight - 5
* SightLook - 6
* LeftHand - 7
* RightHand - 8
* Receiver - 9
* Front - 10
* ToolGrip - 12
* ToolDelivery - 13
* ToolPayload - 14
* ToolTargeting - 15
* ToolScreen - 16
* ToolDetection - 17
* ToolScanning - 18
* MeleeHead - 20
* RotationPivot - 40
* GroundPlacement - 41

### eGearPerkSpecialType

* HeadshotMulti - 0
* FirstShotInMagMulti - 1
* LastShotInMagMulti - 2

### eGearToolPartDeliveryType

* DirectPlacement - 0
* DirectPlacementWithRemoteTrigger - 1
* Drone - 2
* LongRangeSemi - 3
* LongRangeBurst - 4
* LongRangeSemiRemoteTrigger - 5

### eGearToolPartPayloadType

* Explosive - 0
* Glue - 1
* Fire - 2
* Health - 3

### eGearToolPartTargetingType

* Alpha - 0
* EnemiesAndPlayer - 1
* Gamme - 2
* Delta - 3

### eLocalZoneIndex

* Zone_0 - 0
* Zone_1 - 1
* Zone_2 - 2
* Zone_3 - 3
* Zone_4 - 4
* Zone_5 - 5
* Zone_6 - 6
* Zone_7 - 7
* Zone_8 - 8
* Zone_9 - 9
* Zone_10 - 10
* Zone_11 - 11
* Zone_12 - 12
* Zone_13 - 13
* Zone_14 - 14
* Zone_15 - 15
* Zone_16 - 16
* Zone_17 - 17
* Zone_18 - 18
* Zone_19 - 19
* Zone_20 - 20

### eMeleeAttackSide

* None - 0
* Right - 1
* Left - 2
* Middle - 3

### eOfflineGearType

* None - 0
* StandardInventory - 1
* RundownSpecificInventory - 2
* SpawnedInLevel - 3

### ePlayfabCurrency

* CurrA - 0
* CurrB - 1
* CurrC - 2

### eProgressionPuzzleType

* None - 0
* Keycard_SecurityBox - 1
* PowerGenerator_And_PowerCell - 2
* Locked_No_Key - 3

### eProgressionVisualStyle

* Normal - 0
* Story - 1

### eReactorWaveSpawnType

* ClosestToReactorNoPlayerBetween - 0
* InElevatorZone - 1

### eRetrieveExitWaveTrigger

* OnObjectiveCompleted - 0
* WhenExitScanMakesProgress - 1

### eRundownTier

* TierA - 1
* TierB - 2
* TierC - 3
* TierD - 4
* TierE - 5
* Surface - 99

### eSecurityGateType

* Security - 0
* Apex - 1

### eSeedType

* None - 0
* SessionSeed - 1
* BuildSeed - 2
* StaticSeed - 3

### eSpawnPlacementType

* Default - 0
* Align_0 - 1
* Align_1 - 2
* Align_2 - 3
* Align_3 - 4
* Align_4 - 5
* Align_5 - 6
* CycleAllAligns - 7

### eStartupScreenKey

* None - 0
* StartupScreenData_1 - 1
* StartupScreenData_2 - 2
* StartupScreenData_3 - 3
* StartupScreenData_4 - 4

### ES_HitreactType

* Unspecified - 0
* None - 1
* Micro - 2
* Light - 3
* Heavy - 4
* ToDeath - 5
* InstantRagdollDeath - 6

### ES_StateEnum

* None - 0
* StandStill - 1
* PathMove - 2
* Knockdown - 3
* JumpDissolve - 4
* LiquidSnake - 5
* KnockdownRecover - 6
* Hitreact - 7
* ShortcutJump - 8
* FloaterFly - 9
* FloaterHitReact - 10
* Dead - 11
* ScoutDetection - 12
* ScoutScream - 13
* Hibernate - 14
* HibernateWakeUp - 15
* Scream - 16
* StuckInGlue - 17
* ShooterAttack - 18
* StrikerAttack - 19
* TankAttack - 20
* TankMultiTargetAttack - 21
* TentacleDragMove - 22
* StrikerMelee - 23
* ClimbLadder - 24
* Jump - 25
* BirtherGiveBirth - 26
* TriggerFogSphere - 27
* PathMoveFlyer - 28
* HitReactFlyer - 29
* ShooterAttackFlyer - 30
* DeadFlyer - 31
* DeadSquidBoss - 32

### eWantedZoneHeighs

* LowMidHigh - 0
* OnlyLow - 1
* OnlyHigh - 2
* OnlyMid - 3
* LowMid - 4
* MidHigh - 5
* LowHigh - 6
* Ascending - 7
* Descending - 8
* Unchanged - 9

### eWardenObjectiveEventTrigger

* None - 0
* OnStart - 1
* OnMid - 2
* OnEnd - 3

### eWardenObjectiveEventType

* None - 0
* OpenSecurityDoor - 1
* UnlockSecurityDoor - 2
* AllLightsOff - 3
* AllLightsOn - 4
* PlaySound - 5
* SetFogSetting - 6
* DimensionFlashTeam - 7
* DimensionWarpTeam - 8
* SpawnEnemyWave - 9
* StopEnemyWaves - 10
* UpdateCustomSubObjective - 11
* ForceCompleteObjective - 12
* EventBreak - 999

### eWardenObjectiveSpecialUpdateType

* None - 0
* IgnoreFoundObjectiveItem - 1
* TriggerFoundObjectiveItemOnlyOnce - 2

### eWardenObjectiveType

* HSU_FindTakeSample - 0
* Reactor_Startup - 1
* Reactor_Shutdown - 2
* GatherSmallItems - 3
* ClearAPath - 4
* SpecialTerminalCommand - 5
* RetrieveBigItems - 6
* PowerCellDistribution - 7
* TerminalUplink - 8
* CentralGeneratorCluster - 9
* ActivateSmallHSU - 10
* Survival - 11
* GatherTerminal - 12
* CorruptedTerminalUplink - 13

### eWardenObjectiveWinCondition

* GoToElevator - 0
* GoToExitGeo - 1

### eWeaponAnimSequenceItemType

* WeaponMovementAnim - 0
* FrontPartAnim - 1
* LeftHandAnim - 2
* LeftHandMagAnim - 3
* ReceiverAnim - 4
* Sound - 5
* DoUpdateAmmo - 6
* Empty - 7
* StockAnim - 8
* RightHandAnim - 9

### eWeaponFireMode

* Semi - 0
* Burst - 1
* Auto - 2
* SemiBurst - 3
* SentryGunSemi - 10
* SentryGunAuto - 11
* SentryGunBurst - 12
* SentryGunShotgunSemi - 13

### ExpeditionFunction

* None - 0
* Security - 1
* BulkheadDoorController - 2
* DisinfectionStation - 3
* Strongbox - 4
* AirSupply - 5
* PowerGenerator - 6
* Terminal - 7
* SmallPickupItem - 8
* Sign - 9
* ResourceContainerWeak - 10
* ResourceContainerSecure - 11
* BigPickupItem - 12
* ResourceContainerCluster - 13
* Corpse - 14
* HydroStatisUnit - 15
* HydroStatisUnitCluster - 16
* CorpseCluster - 17
* SecurityTurret - 18
* GeneratorCluster - 19
* GroundSpawn - 20

### ExpeditionLayers

* Main - 0
* Secondary - 1
* Third - 2

### eZoneBuildFromExpansionType

* Towards_Random - 0
* Towards_Forward - 1
* Towards_Backward - 2
* Towards_Right - 3
* Towards_Left - 4

### eZoneBuildFromType

* From_Random - 0
* From_Start - 1
* From_AverageCenter - 2
* From_Furthest - 3
* From_BetweenStartAndFurthest - 4
* From_IndexWeight - 5

### eZoneDistributionAmount

* None_0 - 0
* Pair_2 - 1
* Few_5 - 2
* Some_10 - 3
* SomeMore_15 - 4
* Many_20 - 5
* Alot_30 - 6
* Tons_50 - 7

### eZoneExpansionType

* Random - 0
* Collapsed - 1
* Expansional - 2
* Directional_Forward - 3
* Directional_Backward - 4
* Directional_Right - 5
* Directional_Left - 6
* Directional_Random - 7

### GameplayTrailerActionName

* None - 0
* Move - 1
* Rotate - 2
* Disable - 3

### GameplayTrailerActionTrigger

* OnStart - 0
* OnButtonA - 1
* OnButtonB - 2
* OnButtonX - 3
* OnButtonY - 4

### InventorySlot

* None - 0
* GearStandard - 1
* GearSpecial - 2
* GearClass - 3
* ResourcePack - 4
* Consumable - 5
* ConsumableHeavy - 6
* InPocket - 7
* InLevelCarry - 8
* Pickup - 9
* GearMelee - 10
* HackingTool - 11

### ItemWarpType

* Never - 0
* Always - 1
* OnlyWarpToSpawnDimension - 2
* OnlyWarpToOtherDimension - 3

### LG_FloorTransitionDirection

* FloorUp - 0
* FloorDown - 1

### LG_LayerType

* MainLayer - 0
* SecondaryLayer - 1
* ThirdLayer - 2

### LG_LevelProgression

* StartLevel - 0
* MidLevel - 1
* EndLevel - 2

### LG_RandomType

* SessionSeed - 0
* BuildSeed - 1
* FixedSeed - 2

### LG_StaticDistributionWeightType

* Weight_is_zeroToOne_startToEnd - 0
* Weight_is_exact_node_index - 1

### LG_StaticPlacementType

* OnNodes_WallsAndCeiling - 0
* OnNodes_Ceiling_UpOnly - 1

### LG_StaticSpawnConstraints

* None - 0
* AlwaysAndOnlySpawnInRespawnerZones - 1

### LightCategory

* General - 0
* Special - 1
* Emergency - 2
* Independent - 3
* Door - 4
* Sign - 5
* DoorImportant - 6

### LootCategory

* MedicSmall - 0
* MedicBig - 1
* ArmorySmall - 2
* ArmoryBig - 3
* ResourcesSmall - 4
* ResourcesBig - 5
* ArtifactSmall - 6
* ArtifactBig - 7
* ObjectiveItem - 8
* LootSmall - 9
* LootBig - 10

### LootType

* Health - 0
* Ammo - 1
* Battery - 2
* ArtifactBasic - 3
* ArtifactUncommon - 4
* ArtifactRare - 5
* ArtifactLegendary - 6
* ArtifactExotic - 7
* ObjectiveScavangeItem - 8

### MaterialType

* Concrete - 1
* Metal - 2
* Glass - 4
* EnemyBody - 8
* EnemyWeakspot - 16
* Plastic - 32
* Mud - 64
* Gravel - 128
* SheetMetal - 256
* Catwalk - 512
* Wood - 1024
* PlayerBody - 2048
* WeakLockMelee - 4096
* Sand - 8192

### Mood

* None - 0
* Happy - 1
* Sad - 2

### MUS_State

* None - 0
* StartUp - 1
* MainMenu - 2
* ElevatorIdle - 3
* ElevatorGoingDown - 4
* Exploration - 5
* Tension - 6
* CombatEncounter - 7
* CombatRegular - 8
* CombatHidden - 9
* SurvivalRegular - 10
* SurvivalHidden - 11
* SurvivalExtreme - 12
* SurvivalEpicMoment - 13
* Silence - 14
* TensionMax - 15
* Theme - 16
* Testing - 17

### NetworkMode

* Both - 0
* Local - 1
* Sync - 2

### ShellTypes

* Shell_None - 0
* Shell_9mm - 1
* Shell_45_ACP - 2
* Shell_338 - 3
* Shell_12_Gauge - 4

### SubComplex

* DigSite - 0
* Refinery - 1
* Storage - 2
* DataCenter - 3
* Lab - 4
* All - 5
* Floodways - 6
* Mining_Reactor - 7
* Plug_SubComplex_Transition - 8
* Tech_Reactor - 9
* Tech_Portal - 10

### SurvivalWaveSpawnType

* InRelationToClosestAlivePlayer - 0
* InSuppliedCourseNodeZone - 1
* InSuppliedCourseNode - 2
* InSuppliedCourseNode_OnPosition - 3
* ClosestToSuppliedNodeButNoBetweenPlayers - 4
* OnSpawnPoints - 5
* FromElevatorDirection - 6

### TerminalLineType

* Normal - 0
* Fail - 1
* SpinningWaitDone - 2
* SpinningWaitNoDone - 3
* ProgressWait - 4
* Warning - 5

### TERM_CommandRule

* Normal - 0
* OnlyOnce - 1
* OnlyOnceDelete - 2

### TERM_State

* Sleeping - 0
* Awake - 1
* PlayerInteracting - 2
* DataMining - 3
* Hacked - 4
* CodePuzzle - 5
* InputTest - 6
* ReactorError - 7
* AskToPlayLogAudio - 8
* DoPlayAudioFile - 9
* AudioLoopError - 10
* Ping - 11
* PasswordProtected - 12
* EnterPassword - 13
