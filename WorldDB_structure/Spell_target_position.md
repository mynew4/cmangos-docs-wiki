Back to [world database](mangosdb_struct) list of tables.

The \`spell\_teleport\` table
-----------------------------

This table holds coordinate information on where the player should be teleported to when a spell with effect SPELL\_EFFECT\_TELEPORT\_UNITS.

### Structure

| **Field**                                                       | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [id](Spell_target_position#id)                                  | int(11) unsigned | NO       | PRI     | 0           |           |
| [target\_map](Spell_target_position#target_map)                 | int(11) unsigned | NO       |         | 0           |           |
| [target\_position\_x](Spell_target_position#target_position_x)  | float            | NO       |         | 0           |           |
| [target\_position\_y](Spell_target_position#target_position_y)  | float            | NO       |         | 0           |           |
| [target\_position\_z](Spell_target_position#target_position_z)  | float            | NO       |         | 0           |           |
| [target\_orientation](Spell_target_position#target_orientation) | float            | NO       |         | 0           |           |

### Description of the fields

#### id

The spell ID. See Spell.dbc

#### target\_map

Map where the player should be teleported to. (See [Map.dbc](Map.dbc))

#### target\_position\_x

X coordinate for the target destination of the spell.

#### target\_position\_y

Y coordinate for the target destination of the spell.

#### target\_position\_z

Z coordinate for the target destination of the spell.

#### target\_orientation

Orientation the player will get when appearing at this location
