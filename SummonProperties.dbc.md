Back to [dbc files](https://github.com/cmangos/issues/wiki/dbc_files) list of tables.

## The `SummonProperties` dbc

This dbc contains information on how a newly spawned entity will interact with its owner and other entities. (e.g.: hostility, friendliness, or neutrality)

### Structure

| Field| Name| Type| Description|
| ---| ---| ---| ---|
|1|id|Int|EffectMiscValueB1|
|2|[field1](cmangos/issues/wiki/SummonProperties.dbc#field1)|Int|???|
|3|[field2](cmangos/issues/wiki/SummonProperties.dbc#field2)|Int|???|
|4|[field3](cmangos/issues/wiki/SummonProperties.dbc#field3)|Int|???|
|5|[field4](cmangos/issues/wiki/SummonProperties.dbc#field4)|Int|???|
|6|[field5](cmangos/issues/wiki/SummonProperties.dbc#field5)|Int|???|

#### field1

#### field2

#### field3

#### field4

#### field5

| SummonPropGroup| Value|
| ---| ---|
|SUMMON_PROP_GROUP_WILD|0|
|SUMMON_PROP_GROUP_FRIENDLY|1|
|SUMMON_PROP_GROUP_PETS|2|
|SUMMON_PROP_GROUP_CONTROLLABLE|3|

| UnitNameSummonTitle| Value| Description
| ---| ---| ---|
|UNITNAME_SUMMON_TITLE_NONE|0|no default title, different summons, 730 spells in 2.4.3|
|UNITNAME_SUMMON_TITLE_PET|1|'s Pet, generic summons, 59 spells in 2.4.3|
|UNITNAME_SUMMON_TITLE_GUARDIAN|2|'s Guardian, summon guardian, 311 spells in 2.4.3
|UNITNAME_SUMMON_TITLE_MINION|3|'s Minion, summon army, 0 spells in 2.4.3|
|UNITNAME_SUMMON_TITLE_TOTEM|4|'s Totem, summon totem, 148 spells in 2.4.3|
|UNITNAME_SUMMON_TITLE_COMPANION|5|'s Companion, critter/minipet, 159 spells in 2.4.3|

Current Summon Categories are: Group, Title, Slot which are processed differently in the Core `void Spell::EffectSummonType(SpellEffectIndex eff_idx)`

## Content

*Version is : 2.4.3*

| id| Name| Description| Comment|
| ---| ---| ---| ---|
|41|???|???|???|
|61|UNITNAME_SUMMON_TITLE_GUARDIAN|Creature Summon "Totems"|???|
|63|???|???|???|
|64|???|???|???|
|65|???|???|???|
|66|???|???|???|
|67|???|???|???|
|81|???|???|???|
|82|???|???|???|
|83|???|???|???|
|121|UNITNAME_SUMMON_TITLE_TOTEM|Player Summon Totems|???|
|181|???|???|???|
|187|???|???|???|
|247|???|???|???|
|307|???|???|???|
|407|???|???|???|
|409|???|???|???|
|427|???|???|???|
|428|???|???|???|

*Version is : 3.3.5a*

|647|UNITNAME_SUMMON_TITLE_TOTEM|Player Summon Totems|???|