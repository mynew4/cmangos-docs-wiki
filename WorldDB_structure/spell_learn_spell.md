Back to [world database](mangosdb_struct) list of tables.

The \`spell\_learn\_spell\` table
---------------------------------

This table holds information on spells that should be learned at the same time a player learns another spell. For example the few spells that are automatically learned when a player first learns a new profession. All fields in this table use spell IDs from Spell.dbc

NOTE: Spells with spell effects SPELL\_EFFECT\_LEARN\_SPELL should NOT be included in this table.

### Structure

| **Field**                            | **Type**             | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------|----------------------|----------|---------|-------------|-----------|
| [entry](Spell_learn_spell#entry)     | smallint(6) unsigned | NO       | PRI     | 0           |           |
| [SpellID](Spell_learn_spell#spellid) | smallint(6) unsigned | NO       | PRI     | 0           |           |
| [Active](Spell_learn_spell#active)   | smallint(6) unsigned | NO       |         | 0           |           |

### Description of the fields

#### entry

The entry of the spell that the player learns, either from a trainer or from anywhere else (.learn for example).

#### SpellID

The entry of the spell that will be automatically learned by the player when the player learns the spell specified in [entry](#entry).

#### Active

Controls if the spell appears in the players spell book upon learning.
0 - The spell does not appear in the spell book.
1 - The spell does appear in the spell book.
