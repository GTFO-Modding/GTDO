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
* DamageOverTime - 9
* Nanoswarm\_Shield - 10
* Nanoswarm\_Weakness - 11
* ExplosionResistance - 12
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
* MovementSpeed - 250
* MovementAcceleration - 251

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
* EnemyPouncer - 2048

### ArtifactCategory

* Common - 0
* Uncommon - 1
* Rare - 2
* \_COUNT - 3

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
* Complex\_Shared - 1
* Complex\_Mining - 2
* Complex\_Tech - 3
* Complex\_Service - 4
* Startup - 5
* Gear\_Weapon\_Front - 20
* Gear\_Weapon\_Receiver - 30
* Gear\_Weapon\_Stock - 40
* Gear\_Weapon\_Sight - 50
* Gear\_Weapon\_Mag - 60
* Gear\_Weapon\_Flashlight - 70
* Gear\_Tool\_Main - 80
* Gear\_Tool\_Grip - 90
* Gear\_Tool\_Delivery - 100
* Gear\_Tool\_Payload - 110
* Gear\_Tool\_Targeting - 120
* Gear\_Tool\_Screen - 130
* Gear\_Melee\_Head - 140
* Gear\_Melee\_Neck - 150
* Gear\_Melee\_Handle - 160
* Gear\_Melee\_Pommel - 170
* Gear\_Material - 200
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
* \_COUNT - 3

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
* Char\_G - 2
* Char\_T - 4
* Char\_F - 8
* Char\_O - 16

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
* Dimension\_1 - 1
* Dimension\_2 - 2
* Dimension\_3 - 3
* Dimension\_4 - 4
* Dimension\_5 - 5
* Dimension\_6 - 6
* Dimension\_7 - 7
* Dimension\_8 - 8
* Dimension\_9 - 9
* Dimension\_10 - 10
* Dimension\_11 - 11
* Dimension\_12 - 12
* Dimension\_13 - 13
* Dimension\_14 - 14
* Dimension\_15 - 15
* Dimension\_16 - 16
* Dimension\_17 - 17
* Dimension\_18 - 18
* Dimension\_19 - 19
* Dimension\_20 - 20
* MAX\_COUNT - 21
* ARENA\_DIMENSION - 22

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
* Force\_One - 1
* Rel\_25 - 2
* Rel\_50 - 3
* Rel\_75 - 4
* Rel\_100 - 5
* Rel\_15 - 6
* Rel\_10 - 7
* Rel\_05 - 8

### eEnemyType

* Weakling - 0
* Standard - 1
* Special - 2
* MiniBoss - 3
* Boss - 4

### eEnemyZoneDistribution

* None - 0
* Force\_One - 1
* Rel\_Value - 2

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
* player\_enter\_new\_area - 1
* player\_enter\_new\_zone - 2
* player\_hacking\_start - 3
* player\_hacking\_success - 4
* player\_pickup\_medikit - 5
* player\_apply\_medikit - 6
* player\_pickup\_ammokit - 7
* player\_apply\_ammokit - 8
* player\_apply\_disinfection - 9
* player\_pickup\_artifact - 10
* player\_enter\_terminal - 11
* player\_exit\_terminal - 12
* player\_take\_damage - 13
* player\_take\_friendly\_fire - 14
* player\_downed - 15
* player\_revived - 16
* player\_revived\_2\_total - 17
* player\_revived\_3\_total - 18
* player\_start\_firing - 19
* player\_stop\_firing - 20
* player\_fire\_bullet - 21
* player\_fire\_glue - 22
* player\_place\_tripmine - 23
* player\_place\_sentrygun - 24
* enemy\_scout\_dead\_from\_melee - 25
* enemy\_dead\_from\_melee - 26
* sticky\_mine\_explode - 27
* sentry\_gun\_fire - 28
* sentry\_gun\_ammo\_depleated - 29
* weak\_door\_opening - 30
* weak\_door\_closing - 31
* weak\_door\_punched - 32
* weak\_door\_explode - 33
* security\_door\_opening - 34
* bioscan\_start - 35
* bioscan\_end - 36
* hibernating\_enemy\_spotted - 37
* hibernating\_enemy\_heartbeat - 38
* hibernating\_enemy\_wakeup - 39
* hibernating\_enemy\_dead - 40
* enemy\_spotted - 41
* scout\_enemy\_spotted - 42
* scout\_enemy\_use\_detect\_ability - 43
* scout\_enemy\_found\_player - 44
* scout\_enemy\_dead - 45
* enemy\_striker\_attack - 46
* enemy\_shooter\_attack - 47
* enemy\_dead - 48
* enemy\_big\_attack - 49
* player\_low\_health - 50
* player\_out\_of\_ammo\_current\_gear - 51
* player\_out\_of\_ammo\_all\_gear - 52
* player\_reload - 53
* player\_revive\_start - 54
* enemy\_wave\_spawned - 55
* player\_downed\_2\_total - 56
* player\_downed\_3\_total - 57
* player\_downed\_4\_total - 58
* player\_pickup\_toolRefill - 59
* player\_apply\_toolRefill - 60
* player\_pickup\_commoditySmall - 61
* player\_pickup\_commodityMedium - 62
* player\_pickup\_commodityLarge - 63
* player\_pickup\_consumable - 64
* player\_pickup\_keycard - 65
* gs\_Startup - 66
* gs\_Offline - 67
* gs\_NoLobby - 68
* gs\_Lobby - 69
* gs\_Slim - 70
* gs\_FakeLobby - 71
* gs\_Generating - 72
* gs\_ReadyToStopElevatorRide - 73
* gs\_StopElevatorRide - 74
* gs\_ReadyToStartLevel - 75
* gs\_InLevel - 76
* gs\_AfterLevel - 77
* gs\_CaptureRecall - 78
* gs\_ExpeditionFail - 79
* gs\_ExpeditionSuccess - 80
* gs\_ExpeditionAbort - 81
* game\_quit - 82
* term\_Help - 83
* term\_Commands - 84
* term\_Cls - 85
* term\_Exit - 86
* term\_Open - 87
* term\_Close - 88
* term\_Activate - 89
* term\_Deactivate - 90
* term\_EmptyLine - 91
* term\_InvalidCommand - 92
* term\_DownloadData - 93
* term\_ViewSecurityLog - 94
* term\_Override - 95
* term\_DisableAlarm - 96
* term\_ActivateBeacon - 97
* term\_Find - 98
* term\_ShowList - 99
* term\_Query - 100
* term\_Locate - 101
* term\_Ping - 102
* wobj\_FindLocationInfo - 103
* wobj\_FindLocationInfoHelp - 104
* wobj\_GoToZone - 105
* wobj\_GoToZoneHelp - 106
* wobj\_InZoneFindItem - 107
* wobj\_InZoneFindItemHelp - 108
* wobj\_SolveItem - 109
* wobj\_SolveItemHelp - 110
* wobj\_GoToWinCondition - 111
* wobj\_GoToWinConditionHelp - 112
* time\_InLevel\_0 - 113
* time\_InLevel\_5 - 114
* time\_InLevel\_15 - 115
* time\_InLevel\_30 - 116
* time\_InLevel\_45 - 117
* time\_InLevel\_60 - 118
* time\_InLevel\_90 - 119
* time\_InLevel\_120 - 120
* time\_InLevel\_150 - 121
* time\_InLevel\_180 - 122
* time\_InLevel\_210 - 123
* time\_InLevel\_240 - 124
* checkpoint\_reload - 125
* new\_user\_registered - 126

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

* Zone\_0 - 0
* Zone\_1 - 1
* Zone\_2 - 2
* Zone\_3 - 3
* Zone\_4 - 4
* Zone\_5 - 5
* Zone\_6 - 6
* Zone\_7 - 7
* Zone\_8 - 8
* Zone\_9 - 9
* Zone\_10 - 10
* Zone\_11 - 11
* Zone\_12 - 12
* Zone\_13 - 13
* Zone\_14 - 14
* Zone\_15 - 15
* Zone\_16 - 16
* Zone\_17 - 17
* Zone\_18 - 18
* Zone\_19 - 19
* Zone\_20 - 20

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
* Keycard\_SecurityBox - 1
* PowerGenerator\_And\_PowerCell - 2
* Locked\_No\_Key - 3

### eProgressionVisualStyle

* Normal - 0
* Story - 1
* External - 2
* ExternalStory - 3

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
* Align\_0 - 1
* Align\_1 - 2
* Align\_2 - 3
* Align\_3 - 4
* Align\_4 - 5
* Align\_5 - 6
* CycleAllAligns - 7

### eStartupScreenKey

* None - 0
* StartupScreenData\_1 - 1
* StartupScreenData\_2 - 2
* StartupScreenData\_3 - 3
* StartupScreenData\_4 - 4

### ES\_HitreactType

* Unspecified - 0
* None - 1
* Micro - 2
* Light - 3
* Heavy - 4
* ToDeath - 5
* InstantRagdollDeath - 6

### ES\_StateEnum

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
* ScreamFlyer - 33

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
* LightsInZone - 13
* LightsInZoneToggle - 14
* AnimationTrigger - 15
* SpawnEnemyOnPoint - 16
* SetNavMarker - 17
* StepProgressionObjective - 18
* SetWorldEventCondition - 19
* LockSecurityDoor - 20
* SetTerminalCommand - 21
* ActivateChainedPuzzle - 22
* LightOnWorldEventObject - 23
* AddToTimer - 24
* ResetTimer - 25
* WinOnDeath - 26
* ForceInstantWin - 27
* DialogueOnClosest - 28
* GetAchievement - 28
* ClearDimension - 30
* StartRepeatingFog - 31
* StopSustainedEvent - 32
* EventBreak - 999

### eWardenObjectiveSpecialUpdateType

* None - 0
* IgnoreFoundObjectiveItem - 1
* TriggerFoundObjectiveItemOnlyOnce - 2

### eWardenObjectiveType

* HSU\_FindTakeSample - 0
* Reactor\_Startup - 1
* Reactor\_Shutdown - 2
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
* Empty - 14
* TimedTerminalSequence - 15

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
* MagazineAction - 10
* EjectCasing - 11

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
* Dumbwaiter - 21

### ExpeditionLayers

* Main - 0
* Secondary - 1
* Third - 2

### eZoneBuildFromExpansionType

* Towards\_Random - 0
* Towards\_Forward - 1
* Towards\_Backward - 2
* Towards\_Right - 3
* Towards\_Left - 4

### eZoneBuildFromType

* From\_Random - 0
* From\_Start - 1
* From\_AverageCenter - 2
* From\_Furthest - 3
* From\_BetweenStartAndFurthest - 4
* From\_IndexWeight - 5

### eZoneDistributionAmount

* None\_0 - 0
* Pair\_2 - 1
* Few\_5 - 2
* Some\_10 - 3
* SomeMore\_15 - 4
* Many\_20 - 5
* Alot\_30 - 6
* Tons\_50 - 7

### eZoneExpansionType

* Random - 0
* Collapsed - 1
* Expansional - 2
* Directional\_Forward - 3
* Directional\_Backward - 4
* Directional\_Right - 5
* Directional\_Left - 6
* Directional\_Random - 7

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

### Language

* English - 1
* French - 2
* Italian - 3
* German - 4
* Spanish - 5
* Russian - 6
* Portuguese\_Brazil - 7
* Polish - 8
* Japanese - 9
* Korean - 10
* Chinese\_Traditional - 11
* Chinese\_Simplified - 12

### LG\_FloorTransitionDirection

* FloorUp - 0
* FloorDown - 1

### LG\_LayerType

* MainLayer - 0
* SecondaryLayer - 1
* ThirdLayer - 2

### LG\_LevelProgression

* StartLevel - 0
* MidLevel - 1
* EndLevel - 2

### LG\_RandomType

* SessionSeed - 0
* BuildSeed - 1
* FixedSeed - 2

### LG\_StaticDistributionWeightType

* Weight\_is\_zeroToOne\_startToEnd - 0
* Weight\_is\_exact\_node\_index - 1

### LG\_StaticPlacementType

* OnNodes\_WallsAndCeiling - 0
* OnNodes\_Ceiling\_UpOnly - 1

### LG\_StaticSpawnConstraints

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

### MagazineDropSoundType

* None - 0
* Small - 1
* Large - 2

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

### MUS\_State

* None - 0
* StartUp - 1
* MainMenu - 2
* ElevatorIdle - 3
* ElevatorGoingDown - 4
* Exploration - 5
* Tension - 6
* EncounterRegular - 7
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
* IntentionalCombatHidden - 18
* IntentionalCombatRegular - 19
* EncounterHidden - 20

### NetworkMode

* Both - 0
* Local - 1
* Sync - 2

### ShellTypes

* Shell\_None - 0
* Shell\_9mm - 1
* Shell\_45\_ACP - 2
* Shell\_338 - 3
* Shell\_12\_Gauge - 4

### SubComplex

* DigSite - 0
* Refinery - 1
* Storage - 2
* DataCenter - 3
* Lab - 4
* All - 5
* Floodways - 6
* Mining\_Reactor - 7
* Plug\_SubComplex\_Transition - 8
* Tech\_Reactor - 9
* Tech\_Portal - 10
* Gardens - 11
* Mining\_Portal - 12

### SurvivalWaveSpawnType

* InRelationToClosestAlivePlayer - 0
* InSuppliedCourseNodeZone - 1
* InSuppliedCourseNode - 2
* InSuppliedCourseNode\_OnPosition - 3
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

### TERM\_Command

* None - 0
* Help - 1
* Commands - 2
* Cls - 3
* Exit - 4
* Open - 5
* Close - 6
* Activate - 7
* Deactivate - 8
* EmptyLine - 9
* InvalidCommand - 10
* DownloadData - 11
* ViewSecurityLog - 12
* Override - 13
* DisableAlarm - 14
* Locate - 15
* ActivateBeacon - 16
* Find - 17
* ShowList - 18
* Query - 19
* Ping - 20
* ReactorStartup - 21
* ReactorVerify - 22
* ReactorShutdown - 23
* WardenObjectiveSpecialCommand - 24
* TerminalUplinkConnect - 25
* TerminalUplinkVerify - 26
* TerminalUplinkConfirm - 27
* ListLogs - 28
* ReadLog - 29
* Start - 30
* TryUnlockingTerminal - 31
* WardenObjectiveGatherCommand - 32
* TerminalCorruptedUplinkConnect - 33
* TerminalCorruptedUplinkVerify - 34
* TimedConnectionSend - 35
* TimedConnectionVerify - 36
* UsedCommand - 37
* UniqueCommand1 - 38
* UniqueCommand2 - 39
* UniqueCommand3 - 40
* UniqueCommand4 - 41
* UniqueCommand5 - 42
* Info - 43
* MAX\_COUNT - 44

### TERM\_CommandRule

* Normal - 0
* OnlyOnce - 1
* OnlyOnceDelete - 2

### TERM\_State

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
