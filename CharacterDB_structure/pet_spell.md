Back to [characters database](charactersdb_struct) list of tables.

The \`pet\_spell\` table
------------------------

This table holds information on individual pet spells.

### Structure

| **Field**                  | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|----------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Pet_spell#guid)     | int(11) unsigned | NO       | PRI     | 0           |           |
| [spell](Pet_spell#spell)   | int(11) unsigned | NO       | PRI     | 0           |           |
| [slot](Pet_spell#slot)     | int(11) unsigned | NO       |         | 0           |           |
| [active](Pet_spell#active) | int(11) unsigned | NO       |         | 0           |           |

### Description of the fields

#### guid

The pet GUID. See [character\_pet.id](character_pet#id)

#### spell

The spell ID. See Spell.dbc

#### slot

The slot the spell icon is in in the pet bar.

#### active

Boolean 0 or 1 controlling if the spell is active or not.
