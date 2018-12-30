Back to [world database](mangosdb_struct) list of tables.

The \`spell\_template\` table
-----------------------------

holds data about every spell used.

### Structure

| **ID** | **Field**                                                                     | **Type**             | **Null** | **Key** | **Default** | **Extra** |
|--------|-------------------------------------------------------------------------------|----------------------|----------|---------|-------------|-----------|
|        | [Id](spell_template#id)                                                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Category](spell_template#category)                                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Dispel](spell_template#dispel)                                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Mechanic](spell_template#mechanic)                                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Attributes](spell_template#attributes)                                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AttributesEx](spell_template#attributesex)                                   | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AttributesEx2](spell_template#attributesex2)                                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AttributesEx3](spell_template#attributesex3)                                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AttributesEx4](spell_template#attributesex4)                                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AttributesEx5](spell_template#attributesex5)                                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AttributesEx6](spell_template#attributesex6)                                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Stances](spell_template#stances)                                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [StancesNot](spell_template#stancesnot)                                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Targets](spell_template#targets)                                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [TargetCreatureType](spell_template#targetcreaturetype)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [RequiresSpellFocus](spell_template#requiresspellfocus)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [FacingCasterFlags](spell_template#facingcasterflags)                         | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [CasterAuraState](spell_template#casteraurastate)                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [TargetAuraState](spell_template#targetaurastate)                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [CasterAuraStateNot](spell_template#casteraurastatenot)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [TargetAuraStateNot](spell_template#targetaurastatenot)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [CastingTimeIndex](spell_template#castingtimeindex)                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [RecoveryTime](spell_template#recoverytime)                                   | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [CategoryRecoveryTime](spell_template#categoryrecoverytime)                   | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [InterruptFlags](spell_template#interruptflags)                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AuraInterruptFlags](spell_template#aurainterruptflags)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [ChannelInterruptFlags](spell_template#channelinterruptflags)                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [procFlags](spell_template#procflags)                                         | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [procChance](spell_template#procchance)                                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [procCharges](spell_template#proccharges)                                     | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [maxLevel](spell_template#maxlevel)                                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [baseLevel](spell_template#baselevel)                                         | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [spellLevel](spell_template#spelllevel)                                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [DurationIndex](spell_template#durationindex)                                 | int(11) unsigned     | NO       |         | 0           |           |
|        | [powerType](spell_template#powertype)                                         | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [manaCost](spell_template#manacost)                                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [manaCostPerlevel](spell_template#manacostperlevel)                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [manaPerSecond](spell_template#manapersecond)                                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [manaPerSecondPerLevel](spell_template#manapersecondperlevel)                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [rangeIndex](spell_template#rangeindex)                                       | INT (11) UNSIGNED    | NO       |         | 1           |           |
|        | [speed](spell_template#speed)                                                 | FLOAT                | NO       |         | 0           |           |
|        | [StackAmount](spell_template#stackamount)                                     | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Totem1](spell_template#totem1)                                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Totem2](spell_template#totem2)                                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Reagent1](spell_template#reagent1)                                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [ReagentCount1](spell_template#reagentcount1)                                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EquippedItemClass](spell_template#equippeditemclass)                         | INT (11) UNSIGNED    | NO       |         | -1          |           |
|        | [EquippedItemSubClassMask](spell_template#equippeditemsubclassmask)           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EquippedItemInventoryTypeMask](spell_template#equippediteminventorytypemask) | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [Effect1](spell_template#effect1)                                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectDieSides1](spell_template#effectdiesides1)                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectBaseDice1](spell_template#effectbasedice1)                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectDicePerLevel1](spell_template#effectdiceperlevel1)                     | FLOAT                | NO       |         | 0           |           |
|        | [EffectRealPointsPerLevel1](spell_template#effectrealpointsperlevel1)         | FLOAT                | NO       |         | 0           |           |
|        | [EffectBasePoints1](spell_template#effectbasepoints1)                         | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectMechanic1](spell_template#effectmechanic1)                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectImplicitTargetA1](spell_template#effectimplicittargeta1)               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectImplicitTargetB1](spell_template#effectimplicittargetb1)               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectRadiusIndex1](spell_template#effectradiusindex1)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectApplyAuraName1](spell_template#effectapplyauraname1)                   | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectAmplitude1](spell_template#effectamplitude1)                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectMultipleValue1](spell_template#effectmultiplevalue1)                   | FLOAT                | NO       |         | 0           |           |
|        | [EffectChainTarget1](spell_template#effectchaintarget1)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectItemType1](spell_template#effectitemtype1)                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectMiscValue1](spell_template#effectmiscvalue1)                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectMiscValueB1](spell_template#effectmiscvalueb1)                         | INT (11)             | NO       |         | 0           |           |
|        | [EffectTriggerSpell1](spell_template#effecttriggerspell1)                     | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [EffectPointsPerComboPoint1](spell_template#effectpointspercombopoint1)       | FLOAT                | NO       |         | 0           |           |
|        | [SpellVisual](spell_template#spellvisual)                                     | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [SpellIconID](spell_template#spelliconid)                                     | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [activeIconID](spell_template#activeiconid)                                   | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [spellPriority](spell_template#spellpriority)                                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [SpellName](spell_template#spellname)                                         | TEXT                 | NO       |         | 0           |           |
|        | [Rank](spell_template#rank)                                                   | TEXT                 | NULL     |         | 0           |           |
|        | [ManaCostPercentage](spell_template#manacostpercentage)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [StartRecoveryCategory](spell_template#startrecoverycategory)                 | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [StartRecoveryTime](spell_template#startrecoverytime)                         | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [MaxTargetLevel](spell_template#maxtargetlevel)                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [SpellFamilyName](spell_template#spellfamilyname)                             | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [SpellFamilyFlags](spell_template#spellfamilyflags)                           | BIGINT (20) UNSIGNED | NO       |         | 0           |           |
|        | [MaxAffectedTargets](spell_template#maxaffectedtargets)                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [DmgClass](spell_template#dmgclass)                                           | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [PreventionType](spell_template#preventiontype)                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [DmgMultiplier1](spell_template#dmgmultiplier1)                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [TotemCategory1](spell_template#totemcategory1)                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [TotemCategory2](spell_template#totemcategory2)                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AreaId](spell_template#areaid)                                               | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [SchoolMask](spell_template#schoolmask)                                       | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [IsServerSide](spell_template#isserverside)                                   | INT (11) UNSIGNED    | NO       |         | 0           |           |
|        | [AttributesServerside](spell_template#attributesserverside)                   | INT (11) UNSIGNED    | NO       |         | 0           |           |

### Description of the fields

#### Id

The spell ID.

#### Category

Category ID based on which cooldown is determined. Spells with same category go into cooldown if one of them goes into cooldown.

| **ID** | **Description** |
|--------|-----------------|
| 0      | Default         |
| 1      | Summon guards   |
| 2      | Entry           |
| 4      | Entry           |

#### Dispel

Dispel type of a spell. Some spells can only dispel specific types of spells, for example poisons.

#### Mechanic

Spells effects utilize a mechanics. For example bleed, root, silence.

#### Attributes

Special rules for spells. There are several columns for attributes. These rules can do anything, and some can be name only.

#### AttributesEx

#### AttributesEx2

#### AttributesEx3

#### AttributesEx4

#### AttributesEx5

#### AttributesEx6

#### Stances

Determines specific stances in which caster must be for spell to be successfully cast.

#### StancesNot

Determines specific stances in which caster cannot be for spell to be successfully cast.

#### Targets

Determines the default targets for some effects. Seems to be connected to TARGET\_NONE.

#### TargetCreatureType

Specifies what creature types the spell can target, for example Humanoid or Beast.

#### RequiresSpellFocus

Specifies the spell focus GO, around which the caster has to be for a successful cast.

Indicates that this spell needs a GO near (e.g. forges). Required object has the type [GAMEOBJECT\_TYPE\_SPELLFOCUS](Gameobject_template#type) and [data0](Gameobject_template#data0-23) matches the RequiresSpellFocus value.

#### FacingCasterFlags

Specifies how the caster has to face the target so that the spell is successful. enum SpellFacingFlags in Unit.h

#### CasterAuraState

Specifies the caster AuraState required for the cast to be successful.

#### TargetAuraState

Specifies the target AuraState required for the cast to be successful.

#### CasterAuraStateNot

Specifies which AuraState the caster must not have for the cast to be successful.

#### TargetAuraStateNot

Specifies which AuraState the target must not have for the cast to be successful.

#### CastingTimeIndex

CastingTime (Id) that defines how long it takes for the spell to cast in milliseconds.

| ID  | CastTime | CastTimePerLevel | MinCastTime |
|-----|----------|------------------|-------------|
| 1   | 0        | 0                | 0           |
| 2   | 250      | 0                | 250         |
| 3   | 500      | 0                | 500         |
| 4   | 1000     | 0                | 1000        |
| 5   | 2000     | XXX              | XXX         |
| 6   | 5000     | XXX              | XXX         |
| 7   | 10000    | XXX              | XXX         |
| 8   | 20000    | XXX              | XXX         |
| 9   | 30000    | XXX              | XXX         |
| 10  | 1000     | -100             | 500         |
| 11  | 2000     | -100             | 1000        |
| 12  | 5000     | -100             | 2500        |
| 13  | 30000    | -1000            | 10000       |
| 14  | 3000     | XXX              | XXX         |
| 15  | 4000     | XXX              | XXX         |
| 16  | 1500     | XXX              | XXX         |
| 17  | XXX      | XXX              | XXX         |
| 18  | -1000000 | XXX              | XXX         |
| 19  | 2500     | XXX              | XXX         |
| 20  | 2500     | XXX              | XXX         |
| 21  | 2600     | XXX              | XXX         |
| 22  | 3500     | XXX              | XXX         |
| 23  | 1800     | XXX              | XXX         |
| 24  | XXX      | XXX              | XXX         |
| 25  | XXX      | XXX              | XXX         |
| 26  | XXX      | XXX              | XXX         |
| 27  | XXX      | XXX              | XXX         |
| 28  | XXX      | XXX              | XXX         |
| 29  | XXX      | XXX              | XXX         |
| 30  | XXX      | XXX              | XXX         |
| 31  | XXX      | XXX              | XXX         |
| 32  | XXX      | XXX              | XXX         |
| 33  | XXX      | XXX              | XXX         |
| 34  | XXX      | XXX              | XXX         |
| 35  | XXX      | XXX              | XXX         |
| 36  | XXX      | XXX              | XXX         |
| 37  | XXX      | XXX              | XXX         |
| 38  | XXX      | XXX              | XXX         |
| 39  | XXX      | XXX              | XXX         |
| 50  | XXX      | XXX              | XXX         |
| 70  | 300000   | XXX              | XXX         |
| 90  | XXX      | XXX              | XXX         |
| 91  | XXX      | XXX              | XXX         |
| 170 | 8000     | XXX              | XXX         |
| 170 | 6000     | XXX              | XXX         |
| 192 | 15000    | XXX              | XXX         |
| 193 | 12000    | XXX              | XXX         |

#### RecoveryTime

#### CategoryRecoveryTime

#### InterruptFlags

#### AuraInterruptFlags

#### ChannelInterruptFlags

#### procFlags

| **Bit** | **Flag**                      | **Comment** |
|---------|-------------------------------|-------------|
| 0       | Killed                        |             |
| 1       | Kill                          |             |
| 2       | Successful Melee Hit          |             |
| 3       | Taken Melee Hit               |             |
| 4       | Successful Melee Spell Hit    |             |
| 5       | Taken Melee Spell Hit         |             |
| 6       | Successful Ranged Hit         |             |
| 7       | Taken Ranged Hit              |             |
| 8       | Successful Ranged Spell Hit   |             |
| 9       | Taken Ranged Spell Hit        |             |
| 10      | Successful Positive Aoe Hit   |             |
| 11      | Taken Positive Aoe            |             |
| 12      | Successful Aoe Spell Hit      |             |
| 13      | Taken Aoe Spell Hit           |             |
| 14      | Successful Positive Spell     |             |
| 15      | Taken Positive Spell          |             |
| 16      | Successful Negative Spell Hit |             |
| 17      | Taken Negative Spell Hit      |             |
| 18      | On Do Periodic                |             |
| 19      | On Take Periodic              |             |
| 20      | Taken Any Damage              |             |
| 21      | On Trap Activation            |             |
| 22      | Successful Mainhand Hit       |             |
| 23      | Successful Offhand Hit        |             |
| 24      | Death                         |             |

#### procChance

#### procCharges

#### maxLevel

#### baseLevel

#### spellLevel

#### DurationIndex

#### powerType

| **ID** | **Description** |
|--------|-----------------|
| 0      | Mana            |
| 1      | Rage            |
| 2      | ?               |
| 3      | Energy          |

#### manaCost

#### manaCostPerlevel

#### manaPerSecond

#### manaPerSecondPerLevel

#### rangeIndex

#### speed

#### StackAmount

#### Totem1

#### Totem2

#### Reagent1

#### ReagentCount1

#### EquippedItemClass

#### EquippedItemSubClassMask

#### EquippedItemInventoryTypeMask

#### Effect1

#### EffectDieSides1

Random Value of the Die that is rolled for the SPELL\_EFFECT
Max(EffectDieSides1) + (EffectBaseDice1 + EffectBasePoints1) = MaxValue for SPELL\_EFFECT

#### EffectBaseDice1

Base Value for the SPELL\_EFFECT, mostly 1
EffectBaseDice1 + EffectBasePoints1 = MinValue for SPELL\_EFFECT

#### EffectDicePerLevel1

#### EffectRealPointsPerLevel1

#### EffectBasePoints1

Value added to EffectBaseDice1

#### EffectMechanic1

#### EffectImplicitTargetA1

#### EffectImplicitTargetB1

#### EffectRadiusIndex1

#### EffectApplyAuraName1

#### EffectAmplitude1

#### EffectMultipleValue1

#### EffectChainTarget1

#### EffectItemType1

#### EffectMiscValue1

#### EffectMiscValueB1

#### EffectTriggerSpell1

#### EffectPointsPerComboPoint1

#### SpellVisual

#### SpellIconID

#### activeIconID

#### spellPriority

#### SpellName

#### Rank

#### ManaCostPercentage

#### StartRecoveryCategory

#### StartRecoveryTime

#### MaxTargetLevel

#### SpellFamilyName

#### SpellFamilyFlags

#### MaxAffectedTargets

#### DmgClass

#### PreventionType

#### DmgMultiplier1

#### TotemCategory1

#### TotemCategory2

#### AreaId

Specifies the Allowed areas for a successful cast.
IDs taken from [AreaGroup.dbc](AreaGroup.dbc)

#### SchoolMask

#### IsServerSide

#### AttributesServerside

------------------------------------------------------------------------

TODO: Describe rest of columns
|24|casterAuraSpell|uint|
|25|targetAuraSpell|uint|
|26|excludeCasterAuraSpell|uint|
|27|excludeTargetAuraSpell|uint|
|28|CastingTimeIndex|uint|
|29|RecoveryTime|uint|
|30|CategoryRecoveryTime|uint|
|31|InterruptFlags|uint|
|32|AuraInterruptFlags|uint|
|33|ChannelInterruptFlags|uint|
|34|procFlags|uint|
|35|procChance|uint|
|36|procCharges|uint|
|37|maxLevel|uint|
|38|baseLevel|uint|
|39|spellLevel|uint|
|40|DurationIndex|uint|
|42|manaCost|uint|
|43|manaCostPerlevel|uint|
|44|manaPerSecond|uint|
|45|manaPerSecondPerLevel|uint|
|46|rangeIndex|uint|
|47|speed|float|
|48|modalNextSpell|uint|
|49|StackAmount|uint|
|50|Totem1|uint|
|51|Totem2|uint|
|52|Reagent1|int|
|53|Reagent2|int|
|54|Reagent3|int|
|55|Reagent4|int|
|56|Reagent5|int|
|57|Reagent6|int|
|58|Reagent7|int|
|59|Reagent8|int|
|60|ReagentCount1|uint|
|61|ReagentCount2|uint|
|62|ReagentCount3|uint|
|63|ReagentCount4|uint|
|64|ReagentCount5|uint|
|65|ReagentCount6|uint|
|66|ReagentCount7|uint|
|67|ReagentCount8|uint|
|68|EquippedItemClass|int|
|69|EquippedItemSubClassMask|int|
|70|EquippedItemInventoryTypeMask|int|
|71|Effect1|uint|
|72|Effect2|uint|
|73|Effect3|uint|
|75|EffectDieSides2|int|
|76|EffectDieSides3|int|
|77|EffectRealPointsPerLevel1|float|
|78|EffectRealPointsPerLevel2|float|
|79|EffectRealPointsPerLevel3|float|
|81|EffectBasePoints2|int|
|82|EffectBasePoints3|int|
|83|EffectMechanic1|uint|
|84|EffectMechanic2|uint|
|85|EffectMechanic3|uint|
|86|EffectImplicitTargetA1|uint|
|87|EffectImplicitTargetA2|uint|
|88|EffectImplicitTargetA3|uint|
|89|EffectImplicitTargetB1|uint|
|90|EffectImplicitTargetB2|uint|
|91|EffectImplicitTargetB3|uint|
|92|EffectRadiusIndex1|uint|
|93|EffectRadiusIndex2|uint|
|94|EffectRadiusIndex3|uint|
|95|EffectApplyAuraName1|uint|
|96|EffectApplyAuraName2|uint|
|97|EffectApplyAuraName3|uint|
|98|EffectAmplitude1|uint|
|99|EffectAmplitude2|uint|
|100|EffectAmplitude3|uint|
|101|EffectValueMultiplier1|float|
|102|EffectValueMultiplier2|float|
|103|EffectValueMultiplier3|float|
|104|EffectChainTarget1|uint|
|105|EffectChainTarget2|uint|
|106|EffectChainTarget3|uint|
|107|EffectItemType1|uint|
|108|EffectItemType2|uint|
|109|EffectItemType3|uint|
|110|EffectMiscValue1|int|
|111|EffectMiscValue2|int|
|112|EffectMiscValue3|int|
|113|EffectMiscValueB1|int|
|114|EffectMiscValueB2|int|
|115|EffectMiscValueB3|int|
|116|EffectTriggerSpell1|uint|
|117|EffectTriggerSpell2|uint|
|118|EffectTriggerSpell3|uint|
|119|EffectPointsPerComboPoint1|float|
|120|EffectPointsPerComboPoint2|float|
|121|EffectPointsPerComboPoint3|float|
|122|EffectSpellClassMask1|flag96|
|123|EffectSpellClassMask2|flag96|
|124|EffectSpellClassMask3|flag96|
|125|EffectSpellClassMask4|flag96|
|126|EffectSpellClassMask5|flag96|
|127|EffectSpellClassMask6|flag96|
|128|EffectSpellClassMask7|flag96|
|129|EffectSpellClassMask8|flag96|
|130|EffectSpellClassMask9|flag96|
|131|SpellVisual1|uint|
|132|SpellVisual2|uint|
|133|SpellIconID|uint|
|134|activeIconID|uint|
|135|spellPriority|uint|
|136|SpellName\_0|string|
|137|SpellName\_1|string|
|138|SpellName\_2|string|
|139|SpellName\_3|string|
|140|SpellName\_4|string|
|141|SpellName\_5|string|
|142|SpellName\_6|string|
|143|SpellName\_7|string|
|144|SpellName\_8|string|
|145|SpellName\_9|string|
|146|SpellName\_10|string|
|147|SpellName\_11|string|
|148|SpellName\_12|string|
|149|SpellName\_13|string|
|150|SpellName\_14|string|
|151|SpellName\_15|string|
|152|SpellNameFlag|uint|
|153|Rank\_0|string|
|154|Rank\_1|string|
|155|Rank\_2|string|
|156|Rank\_3|string|
|157|Rank\_4|string|
|158|Rank\_5|string|
|159|Rank\_6|string|
|160|Rank\_7|string|
|161|Rank\_8|string|
|162|Rank\_9|string|
|163|Rank\_10|string|
|164|Rank\_11|string|
|165|Rank\_12|string|
|166|Rank\_13|string|
|167|Rank\_14|string|
|168|Rank\_15|string|
|169|RankFlags|uint|
|170|Description\_0|string|
|171|Description\_1|string|
|172|Description\_2|string|
|173|Description\_3|string|
|174|Description\_4|string|
|175|Description\_5|string|
|176|Description\_6|string|
|177|Description\_7|string|
|178|Description\_8|string|
|179|Description\_9|string|
|180|Description\_10|string|
|181|Description\_11|string|
|182|Description\_12|string|
|183|Description\_13|string|
|184|Description\_14|string|
|185|Description\_15|string|
|186|DescriptionFlags|uint|
|187|ToolTip\_0|string|
|188|ToolTip\_1|string|
|189|ToolTip\_2|string|
|190|ToolTip\_3|string|
|191|ToolTip\_4|string|
|192|ToolTip\_5|string|
|193|ToolTip\_6|string|
|194|ToolTip\_7|string|
|195|ToolTip\_8|string|
|196|ToolTip\_9|string|
|197|ToolTip\_10|string|
|198|ToolTip\_11|string|
|199|ToolTip\_12|string|
|200|ToolTip\_13|string|
|201|ToolTip\_14|string|
|202|ToolTip\_15|string|
|203|ToolTipFlags|uint|
|204|ManaCostPercentage|uint|
|205|StartRecoveryCategory|uint|
|206|StartRecoveryTime|uint|
|207|MaxTargetLevel|uint|
|208|SpellFamilyName|uint|
|209|SpellFamilyFlagsLow|flag96|
|210|SpellFamilyFlagsHigh|flag96|
|211|SpellFamilyFlags2|flag96|
|212|MaxAffectedTargets|uint|
|213|DmgClass|uint|
|214|PreventionType|uint|
|215|StanceBarOrder|uint|
|216|EffectDamageMultiplier1|float|
|217|EffectDamageMultiplier2|float|
|218|EffectDamageMultiplier3|float|
|219|MinFactionId|uint|
|220|MinReputation|uint|
|221|RequiredAuraVision|uint|
|222|TotemCategory1|uint|
|223|TotemCategory2|uint|
|225|SchoolMask|uint|
|226|runeCostID|uint|
|227|spellMissileID|uint|
|228|PowerDisplayId|uint|
|229|EffectBonusMultiplier1|float|
|230|EffectBonusMultiplier2|float|
|231|EffectBonusMultiplier3|float|
|232|spellDescriptionVariableID|uint|
|233|SpellDifficultyId|uint|
