## Introduction

A **client database** or **DBC** file is a simple binary format for a database table. Each record in the file is one row of the table. Field values may consist of a limited range of data types, and do not include field separation characters — except for character-based string fields. DBC files nearly always use file extension `DBC` or `dbc`, and thus have been named _DataBaseClient_ files ever since their discovery. The true extension meaning has not yet been revealed by Blizzard. 

## Technical details 

Each file consists of a header, the table data, and if necessary a string block.

## Header

	00h:	char[4] Signature 			always 'WDBC' 
	04h:	int32 Records 				number of records in the file 
	08h:	int32 Fields				number of fields per record 
	0Ch:	int32 Record Size 			Fields*FieldSize (FieldSize is usually 4, but not always) 
	10h:	int32 String Block Size 	Size of the string block

## Table Data

Each record has a constant length. Usually all the values are 32bit integers. String data is stored in a block after the records. String data in records contain an offset to the string, relative to the start of the string block. When encountering string data, it usually consists of an English name field, followed by 7 additional fields for different localizations.

## String Block

A continuous block of zero-terminated strings. Offsets into the String Block are relative to the start of the block.

## Known DBC Files

dbc.MPQ contains 138 DBC files:

* AnimationData.dbc                                                                                                                                                                                                  
* AreaPOI.dbc                                                                                                                                                                                                        
* AreaTable.dbc                                                                                                                                                                                                      
* AreaTrigger.dbc                                                                                                                                                                                                    
* AttackAnimKits.dbc                                                                                                                                                                                                 
* AttackAnimTypes.dbc                                                                                                                                                                                                
* AuctionHouse.dbc                                                                                                                                                                                                   
* BankBagSlotPrices.dbc                                                                                                                                                                                              
* CameraShakes.dbc                                                                                                                                                                                                   
* Cfg_Categories.dbc                                                                                                                                                                                                 
* Cfg_Configs.dbc                                                                                                                                                                                                    
* CharacterCreateCameras.dbc                                                                                                                                                                                         
* CharacterFacialHairStyles.dbc                                                                                                                                                                                      
* CharBaseInfo.dbc                                                                                                                                                                                                   
* CharHairGeosets.dbc                                                                                                                                                                                                
* CharHairTextures.dbc                                                                                                                                                                                               
* CharSections.dbc                                                                                                                                                                                                   
* CharStartOutfit.dbc
* CharVariations.dbc
* ChatChannels.dbc
* ChatProfanity.dbc
* ChrClasses.dbc
* ChrRaces.dbc
* CinematicCamera.dbc
* CinematicSequences.dbc
* CreatureDisplayInfo.dbc
* CreatureDisplayInfoExtra.dbc
* CreatureFamily.dbc
* CreatureModelData.dbc
* CreatureSoundData.dbc
* CreatureType.dbc
* DeathThudLookups.dbc
* DurabilityCosts.dbc
* DurabilityQuality.dbc
* Emotes.dbc
* EmotesText.dbc
* EmotesTextData.dbc
* EnvironmentalDamage.dbc
* Exhaustion.dbc
* Faction.dbc
* FactionGroup.dbc
* FactionTemplate.dbc
* FootprintTextures.dbc
* FootstepTerrainLookup.dbc
* GameObjectDisplayInfo.dbc
* GMTicketCategory.dbc
* GroundEffectDoodad.dbc
* GroundEffectTexture.dbc
* HelmetGeosetVisData.dbc
* ItemClass.dbc
* ItemDisplayInfo.dbc
* ItemGroupSounds.dbc
* ItemPetFood.dbc
* ItemRandomProperties.dbc
* ItemSet.dbc
* ItemSubClass.dbc
* ItemSubClassMask.dbc
* ItemVisualEffects.dbc
* ItemVisuals.dbc
* Languages.dbc
* LanguageWords.dbc
* LoadingScreens.dbc
* LoadingScreenTaxiSplines.dbc
* Lock.dbc
* LockType.dbc
* Map.dbc
* Material.dbc
* NameGen.dbc
* NamesProfanity.dbc
* NamesReserved.dbc
* NPCSounds.dbc
* Package.dbc
* PageTextMaterial.dbc
* PaperDollItemFrame.dbc
* PetLoyalty.dbc
* PetPersonality.dbc
* QuestInfo.dbc
* QuestSort.dbc
* Resistances.dbc
* ServerMessages.dbc
* SheatheSoundLookups.dbc
* SkillCostsData.dbc
* SkillLine.dbc
* SkillLineAbility.dbc
* SkillLineCategory.dbc
* SkillRaceClassInfo.dbc
* SkillTiers.dbc
* SoundAmbience.dbc
* SoundCharacterMacroLines.dbc
* SoundEntries.dbc
* SoundProviderPreferences.dbc
* SoundSamplePreferences.dbc
* SoundWaterType.dbc
* Spell.dbc
* SpellAuraNames.dbc
* SpellCastTimes.dbc
* SpellCategory.dbc
* SpellChainEffects.dbc
* SpellDispelType.dbc
* SpellDuration.dbc
* SpellEffectCameraShakes.dbc
* SpellEffectNames.dbc
* SpellFocusObject.dbc
* SpellIcon.dbc
* SpellItemEnchantment.dbc
* SpellRadius.dbc
* SpellRange.dbc
* SpellShapeshiftForm.dbc
* SpellVisual.dbc
* SpellVisualEffectName.dbc
* SpellVisualKit.dbc
* SpellVisualPrecastTransitions.dbc
* StableSlotPrices.dbc
* Startup_Strings.dbc
* Stationery.dbc
* StringLookups.dbc
* Talent.dbc
* TalentTab.dbc
* TaxiNodes.dbc
* TaxiPath.dbc
* TaxiPathNode.dbc
* TerrainType.dbc
* TerrainTypeSounds.dbc
* TransportAnimation.dbc
* UISoundLookups.dbc
* UnitBlood.dbc
* UnitBloodLevels.dbc
* VideoHardware.dbc
* VocalUISounds.dbc
* WeaponImpactSounds.dbc
* WeaponSwingSounds2.dbc
* WMOAreaTable.dbc
* WorldMapArea.dbc
* WorldMapContinent.dbc
* WorldMapOverlay.dbc
* WorldSafeLocs.dbc
* ZoneIntroMusicTable.dbc
* ZoneMusic.dbc

Back to [[Client File Formats]]