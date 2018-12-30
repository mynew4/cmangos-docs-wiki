Back to [world database](mangosdb_struct) list of tables.

The \`petcreateinfo\_spell\` table
----------------------------------

This table controls what spells a tameable beast will have once tamed. It also controls the passive auras that the pet will get.

### Structure

| **Field**                            | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Petcreateinfo_spell#entry)   | int(11) unsigned | NO       | PRI     | 0           |           |
| [Spell1](Petcreateinfo_spell#spelln) | int(11) unsigned | NO       |         | 0           |           |
| [Spell2](Petcreateinfo_spell#spelln) | int(11) unsigned | NO       |         | 0           |           |
| [Spell3](Petcreateinfo_spell#spelln) | int(11) unsigned | NO       |         | 0           |           |
| [Spell4](Petcreateinfo_spell#spelln) | int(11) unsigned | NO       |         | 0           |           |
|                                      |                  |

### Description of the fields

#### entry

The template ID of the beast. See [creature\_template.entry](creature_template#entry)

#### SpellN

The spell that the pet will have automatically in its pet bar once tamed. Also, the spells in this field need to be "learn" spells because the hunter character will learn the spells so that they can teach other pets those spells. See Spell.dbc
