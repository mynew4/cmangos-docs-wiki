Back to [world database](mangosdb_struct) list of tables.

The \`playercreateinfo\_spell\` table
-------------------------------------

This table holds information on what spells newly created characters should start out with. A character in this table is defined by his/her race and class combination.

### Structure

| **Field**                               | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------|---------------------|----------|---------|-------------|-----------|
| [race](Playercreateinfo_spell#race)     | tinyint(3) unsigned | NO       | PRI     | 0           |           |
| [class](Playercreateinfo_spell#class)   | tinyint(3) unsigned | NO       | PRI     | 0           |           |
| [Spell](Playercreateinfo_spell#spell)   | bigint(20) unsigned | NO       | PRI     | 0           |           |
| [Note](Playercreateinfo_spell#note)     | varchar(255)        | YES      |         |             |           |
| [Active](Playercreateinfo_spell#active) | tinyint(3) unsigned | NO       |         | 1           |           |

### Description of the fields

#### race

The character's race.

#### class

The character's class.

#### Spell

The spell ID. See Spell.dbc

#### Note

A note explaining what the spell is. This is only for reference purposes and not used by mangos.

#### Active

Boolean 0 or 1 controlling if the spell is active or not.
