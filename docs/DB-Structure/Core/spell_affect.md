Back to [world database](mangosdb_struct) list of tables.

The \`spell\_affect\` table
---------------------------

This table holds information on what spells are affected by what spell mods. All spells in this table need to apply an aura that either adds a flat modifier to other spells or adds a percent modifier to other spells. Also, a single row in this table only holds information on a single spell effect that applies the aura. Therefore since a spell may have up to three effects, a maximum of 3 rows per spell is allowed. However, only the spell effects that apply the flat or percent auras will be used.

### Structure

| **Field**                                      | **Type**             | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------------|----------------------|----------|---------|-------------|-----------|
| [entry](Spell_affect#entry)                    | smallint(5) unsigned | NO       | PRI     | 0           |           |
| [effectId](Spell_affect#effectid)              | tinyint(3) unsigned  | NO       | PRI     | 0           |           |
| [SpellClassMask0](Spell_affect#spellclassmask) | int(5) unsigned      | NO       |         | 0           |           |
| [SpellClassMask1](Spell_affect#spellclassmask) | int(5) unsigned      | NO       |         | 0           |           |
| [SpellClassMask2](Spell_affect#spellclassmask) | int(5) unsigned      | NO       |         | 0           |           |

### Description of the fields

#### entry

The modifying spell entry ID. See Spell.dbc

#### effectId

The effect index of the effect that applies the aura with the flat or percent modifier. This field along with [entry](#entry) defines a single modifying entry. The effect IDs are numbered starting with 0, so the first effect is 0, the next is 1, and finally the last is 2.

#### SpellClassMask

This field controls what class a spell needs to have to be affected by the modifier. This is the main field that defines which spells are affected by modifiers. For SpellClass see spell.dbc (in WoW-3.0.3 column 211)

#### SpellFamilyName

SpellFamilyName need to align for affecting/affected Spell(s). Note that only (Rank 1) of a spell needs to be inserted, which then applies to all ranks of a spell.

| ID  | Family Name | ID  | Family Name  |
|-----|-------------|-----|--------------|
| 0   | Generic     | 9   | Hunter       |
| 3   | Mage        | 10  | Paladin      |
| 4   | Warrior     | 11  | Shaman       |
| 5   | Warlock     | 13  | Potion       |
| 6   | Priest      | 15  | Death Knight |
| 7   | Druid       | 53  | Monk         |
| 8   | Rogue       | 107 | Demon Hunter |


