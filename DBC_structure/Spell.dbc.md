Back to [dbc files](dbc_files) list.

### Spell.dbc

This DBC contains most information on all spells. These values are used by the core and a few spell\_\* tables.

**Version 3.3.5**

### Structure

| **ID** | **Name**                                           | **Type** |
|--------|----------------------------------------------------|----------|
| 0      | [Entry](Spell.dbc#entry)                           | uint     |
| 1      | [Category](Spell.dbc#category)                     | uint     |
| 2      | [Dispel](Spell.dbc#dispel)                         | uint     |
| 3      | [Mechanic](Spell.dbc#mechanic)                     | uint     |
| 4      | [Attributes](Spell.dbc#attributes)                 | uint     |
| 5      | [AttributesEx](Spell.dbc#attributes)               | uint     |
| 6      | [AttributesEx2](Spell.dbc#attributes)              | uint     |
| 7      | [AttributesEx3](Spell.dbc#attributes)              | uint     |
| 8      | [AttributesEx4](Spell.dbc#attributes)              | uint     |
| 9      | [AttributesEx5](Spell.dbc#attributes)              | uint     |
| 10     | [AttributesEx6](Spell.dbc#attributes)              | uint     |
| 11     | [AttributesEx7](Spell.dbc#attributes)              | uint     |
| 12     | [Stances](Spell.dbc#stances)                       | uint     |
| 13     | "unk\_320\_2"                                      | uint     |
| 14     | [StancesNot](Spell.dbc#stancesnot)                 | uint     |
| 15     | "unk\_320\_3"                                      | uint     |
| 16     | [Targets](Spell.dbc#targets)                       | uint     |
| 17     | [TargetCreatureType](Spell.dbc#targetcreaturetype) | uint     |
| 18     | [RequiresSpellFocus](Spell.dbc#requiresspellfocus) | uint     |
| 19     | [FacingCasterFlags](Spell.dbc#facingcasterflags)   | uint     |
| 20     | [CasterAuraState](Spell.dbc#casteraurastate)       | uint     |
| 21     | [TargetAuraState](Spell.dbc#targetaurastate)       | uint     |
| 22     | [CasterAuraStateNot](Spell.dbc#casteraurastatenot) | uint     |
| 23     | [TargetAuraStateNot](Spell.dbc#targetaurastatenot) | uint     |
| 24     | casterAuraSpell                                    | uint     |
| 25     | targetAuraSpell                                    | uint     |
| 26     | excludeCasterAuraSpell                             | uint     |
| 27     | excludeTargetAuraSpell                             | uint     |
| 28     | CastingTimeIndex                                   | uint     |
| 29     | RecoveryTime                                       | uint     |
| 30     | CategoryRecoveryTime                               | uint     |
| 31     | InterruptFlags                                     | uint     |
| 32     | AuraInterruptFlags                                 | uint     |
| 33     | ChannelInterruptFlags                              | uint     |
| 34     | procFlags                                          | uint     |
| 35     | procChance                                         | uint     |
| 36     | procCharges                                        | uint     |
| 37     | maxLevel                                           | uint     |
| 38     | baseLevel                                          | uint     |
| 39     | spellLevel                                         | uint     |
| 40     | DurationIndex                                      | uint     |
| 41     | [powerType](Spell.dbc#powertype)                   | uint     |
| 42     | manaCost                                           | uint     |
| 43     | manaCostPerlevel                                   | uint     |
| 44     | manaPerSecond                                      | uint     |
| 45     | manaPerSecondPerLevel                              | uint     |
| 46     | rangeIndex                                         | uint     |
| 47     | speed                                              | float    |
| 48     | modalNextSpell                                     | uint     |
| 49     | StackAmount                                        | uint     |
| 50     | Totem1                                             | uint     |
| 51     | Totem2                                             | uint     |
| 52     | Reagent1                                           | int      |
| 53     | Reagent2                                           | int      |
| 54     | Reagent3                                           | int      |
| 55     | Reagent4                                           | int      |
| 56     | Reagent5                                           | int      |
| 57     | Reagent6                                           | int      |
| 58     | Reagent7                                           | int      |
| 59     | Reagent8                                           | int      |
| 60     | ReagentCount1                                      | uint     |
| 61     | ReagentCount2                                      | uint     |
| 62     | ReagentCount3                                      | uint     |
| 63     | ReagentCount4                                      | uint     |
| 64     | ReagentCount5                                      | uint     |
| 65     | ReagentCount6                                      | uint     |
| 66     | ReagentCount7                                      | uint     |
| 67     | ReagentCount8                                      | uint     |
| 68     | EquippedItemClass                                  | int      |
| 69     | EquippedItemSubClassMask                           | int      |
| 70     | EquippedItemInventoryTypeMask                      | int      |
| 71     | Effect1                                            | uint     |
| 72     | Effect2                                            | uint     |
| 73     | Effect3                                            | uint     |
| 74     | EffectDieSides1                                    | int      |
| 75     | EffectDieSides2                                    | int      |
| 76     | EffectDieSides3                                    | int      |
| 77     | EffectRealPointsPerLevel1                          | float    |
| 78     | EffectRealPointsPerLevel2                          | float    |
| 79     | EffectRealPointsPerLevel3                          | float    |
| 80     | EffectBasePoints1                                  | int      |
| 81     | EffectBasePoints2                                  | int      |
| 82     | EffectBasePoints3                                  | int      |
| 83     | EffectMechanic1                                    | uint     |
| 84     | EffectMechanic2                                    | uint     |
| 85     | EffectMechanic3                                    | uint     |
| 86     | EffectImplicitTargetA1                             | uint     |
| 87     | EffectImplicitTargetA2                             | uint     |
| 88     | EffectImplicitTargetA3                             | uint     |
| 89     | EffectImplicitTargetB1                             | uint     |
| 90     | EffectImplicitTargetB2                             | uint     |
| 91     | EffectImplicitTargetB3                             | uint     |
| 92     | EffectRadiusIndex1                                 | uint     |
| 93     | EffectRadiusIndex2                                 | uint     |
| 94     | EffectRadiusIndex3                                 | uint     |
| 95     | EffectApplyAuraName1                               | uint     |
| 96     | EffectApplyAuraName2                               | uint     |
| 97     | EffectApplyAuraName3                               | uint     |
| 98     | EffectAmplitude1                                   | uint     |
| 99     | EffectAmplitude2                                   | uint     |
| 100    | EffectAmplitude3                                   | uint     |
| 101    | EffectValueMultiplier1                             | float    |
| 102    | EffectValueMultiplier2                             | float    |
| 103    | EffectValueMultiplier3                             | float    |
| 104    | EffectChainTarget1                                 | uint     |
| 105    | EffectChainTarget2                                 | uint     |
| 106    | EffectChainTarget3                                 | uint     |
| 107    | EffectItemType1                                    | uint     |
| 108    | EffectItemType2                                    | uint     |
| 109    | EffectItemType3                                    | uint     |
| 110    | EffectMiscValue1                                   | int      |
| 111    | EffectMiscValue2                                   | int      |
| 112    | EffectMiscValue3                                   | int      |
| 113    | EffectMiscValueB1                                  | int      |
| 114    | EffectMiscValueB2                                  | int      |
| 115    | EffectMiscValueB3                                  | int      |
| 116    | EffectTriggerSpell1                                | uint     |
| 117    | EffectTriggerSpell2                                | uint     |
| 118    | EffectTriggerSpell3                                | uint     |
| 119    | EffectPointsPerComboPoint1                         | float    |
| 120    | EffectPointsPerComboPoint2                         | float    |
| 121    | EffectPointsPerComboPoint3                         | float    |
| 122    | EffectSpellClassMask1                              | flag96   |
| 123    | EffectSpellClassMask2                              | flag96   |
| 124    | EffectSpellClassMask3                              | flag96   |
| 125    | EffectSpellClassMask4                              | flag96   |
| 126    | EffectSpellClassMask5                              | flag96   |
| 127    | EffectSpellClassMask6                              | flag96   |
| 128    | EffectSpellClassMask7                              | flag96   |
| 129    | EffectSpellClassMask8                              | flag96   |
| 130    | EffectSpellClassMask9                              | flag96   |
| 131    | SpellVisual1                                       | uint     |
| 132    | SpellVisual2                                       | uint     |
| 133    | SpellIconID                                        | uint     |
| 134    | activeIconID                                       | uint     |
| 135    | spellPriority                                      | uint     |
| 136    | SpellName\_0                                       | string   |
| 137    | SpellName\_1                                       | string   |
| 138    | SpellName\_2                                       | string   |
| 139    | SpellName\_3                                       | string   |
| 140    | SpellName\_4                                       | string   |
| 141    | SpellName\_5                                       | string   |
| 142    | SpellName\_6                                       | string   |
| 143    | SpellName\_7                                       | string   |
| 144    | SpellName\_8                                       | string   |
| 145    | SpellName\_9                                       | string   |
| 146    | SpellName\_10                                      | string   |
| 147    | SpellName\_11                                      | string   |
| 148    | SpellName\_12                                      | string   |
| 149    | SpellName\_13                                      | string   |
| 150    | SpellName\_14                                      | string   |
| 151    | SpellName\_15                                      | string   |
| 152    | SpellNameFlag                                      | uint     |
| 153    | Rank\_0                                            | string   |
| 154    | Rank\_1                                            | string   |
| 155    | Rank\_2                                            | string   |
| 156    | Rank\_3                                            | string   |
| 157    | Rank\_4                                            | string   |
| 158    | Rank\_5                                            | string   |
| 159    | Rank\_6                                            | string   |
| 160    | Rank\_7                                            | string   |
| 161    | Rank\_8                                            | string   |
| 162    | Rank\_9                                            | string   |
| 163    | Rank\_10                                           | string   |
| 164    | Rank\_11                                           | string   |
| 165    | Rank\_12                                           | string   |
| 166    | Rank\_13                                           | string   |
| 167    | Rank\_14                                           | string   |
| 168    | Rank\_15                                           | string   |
| 169    | RankFlags                                          | uint     |
| 170    | Description\_0                                     | string   |
| 171    | Description\_1                                     | string   |
| 172    | Description\_2                                     | string   |
| 173    | Description\_3                                     | string   |
| 174    | Description\_4                                     | string   |
| 175    | Description\_5                                     | string   |
| 176    | Description\_6                                     | string   |
| 177    | Description\_7                                     | string   |
| 178    | Description\_8                                     | string   |
| 179    | Description\_9                                     | string   |
| 180    | Description\_10                                    | string   |
| 181    | Description\_11                                    | string   |
| 182    | Description\_12                                    | string   |
| 183    | Description\_13                                    | string   |
| 184    | Description\_14                                    | string   |
| 185    | Description\_15                                    | string   |
| 186    | DescriptionFlags                                   | uint     |
| 187    | ToolTip\_0                                         | string   |
| 188    | ToolTip\_1                                         | string   |
| 189    | ToolTip\_2                                         | string   |
| 190    | ToolTip\_3                                         | string   |
| 191    | ToolTip\_4                                         | string   |
| 192    | ToolTip\_5                                         | string   |
| 193    | ToolTip\_6                                         | string   |
| 194    | ToolTip\_7                                         | string   |
| 195    | ToolTip\_8                                         | string   |
| 196    | ToolTip\_9                                         | string   |
| 197    | ToolTip\_10                                        | string   |
| 198    | ToolTip\_11                                        | string   |
| 199    | ToolTip\_12                                        | string   |
| 200    | ToolTip\_13                                        | string   |
| 201    | ToolTip\_14                                        | string   |
| 202    | ToolTip\_15                                        | string   |
| 203    | ToolTipFlags                                       | uint     |
| 204    | ManaCostPercentage                                 | uint     |
| 205    | StartRecoveryCategory                              | uint     |
| 206    | StartRecoveryTime                                  | uint     |
| 207    | MaxTargetLevel                                     | uint     |
| 208    | SpellFamilyName                                    | uint     |
| 209    | SpellFamilyFlagsLow                                | flag96   |
| 210    | SpellFamilyFlagsHigh                               | flag96   |
| 211    | SpellFamilyFlags2                                  | flag96   |
| 212    | MaxAffectedTargets                                 | uint     |
| 213    | DmgClass                                           | uint     |
| 214    | PreventionType                                     | uint     |
| 215    | StanceBarOrder                                     | uint     |
| 216    | EffectDamageMultiplier1                            | float    |
| 217    | EffectDamageMultiplier2                            | float    |
| 218    | EffectDamageMultiplier3                            | float    |
| 219    | MinFactionId                                       | uint     |
| 220    | MinReputation                                      | uint     |
| 221    | RequiredAuraVision                                 | uint     |
| 222    | TotemCategory1                                     | uint     |
| 223    | TotemCategory2                                     | uint     |
| 224    | AreaGroupId                                        | int      |
| 225    | SchoolMask                                         | uint     |
| 226    | runeCostID                                         | uint     |
| 227    | spellMissileID                                     | uint     |
| 228    | PowerDisplayId                                     | uint     |
| 229    | EffectBonusMultiplier1                             | float    |
| 230    | EffectBonusMultiplier2                             | float    |
| 231    | EffectBonusMultiplier3                             | float    |
| 232    | spellDescriptionVariableID                         | uint     |
| 233    | SpellDifficultyId                                  | uint     |

#### Category

| **ID** | **Description** |
|--------|-----------------|
| 0      | Default         |
| 1      | Summon guards   |
| 2      | Entry           |
| 4      | Entry           |

#### powerType

| **ID** | **Description** |
|--------|-----------------|
| 0      | Mana            |
| 1      | Rage            |
| 2      | ?               |
| 3      | Energy          |

#### RequiresSpellFocus

Indicates that this spell needs a GO near (e.g. forges). Required object has the type [GAMEOBJECT\_TYPE\_SPELLFOCUS](Gameobject_template#type) and [data0](Gameobject_template#data0-23) matches the RequiresSpellFocus value.

#### Entry

Unique identifier of a spell

#### Category

Category ID based on which cooldown is determined. Spells with same category go into cooldown if one of them goes into cooldown.

#### Dispel

Dispel type of a spell. Some spells can only dispel specific types of spells, for example poisons.

#### Mechanic

Spells effects utilize a mechanics. For example bleed, root, silence.

#### Attributes

Special rules for spells. There are several columns for attributes. These rules can do anything, and some can be name only.

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
|41|[powerType](Spell.dbc#powertype%7Cuint%7C)
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
|74|EffectDieSides1|int|
|75|EffectDieSides2|int|
|76|EffectDieSides3|int|
|77|EffectRealPointsPerLevel1|float|
|78|EffectRealPointsPerLevel2|float|
|79|EffectRealPointsPerLevel3|float|
|80|EffectBasePoints1|int|
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
|224|AreaGroupId|int|
|225|SchoolMask|uint|
|226|runeCostID|uint|
|227|spellMissileID|uint|
|228|PowerDisplayId|uint|
|229|EffectBonusMultiplier1|float|
|230|EffectBonusMultiplier2|float|
|231|EffectBonusMultiplier3|float|
|232|spellDescriptionVariableID|uint|
|233|SpellDifficultyId|uint|
