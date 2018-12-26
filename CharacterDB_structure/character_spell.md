Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_spell\` table
------------------------------

Holds information for each character's spells.

### Structure

| **Field**                        | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Character_spell#guid)     | int(11) unsigned    | NO       | PRI     | 0           |           |
| [spell](Character_spell#spell)   | int(11) unsigned    | NO       | PRI     | 0           |           |
| [slot](Character_spell#slot)     | int(11) unsigned    | NO       |         | 0           |           |
| [active](Character_spell#active) | tinyint(3) unsigned | NO       |         | 1           |           |

### Description of the fields

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### spell

The spell ID. See Spell.dbc column 1

#### slot

The slot in the spell book that the spell is in.

#### active

Boolean 1 or 0 signifying whether the spell is active (appears in the spell book).
