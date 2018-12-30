Back to [world database](mangosdb_struct) list of tables.

The \`playercreateinfo\` table
------------------------------

This table holds the start positions of each class-race combinations for all newly created characters.

### Structure

| **Field**                                   | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [race](Playercreateinfo#race)               | tinyint(3) unsigned   | NO       | PRI     | 0           |           |
| [class](Playercreateinfo#class)             | tinyint(3) unsigned   | NO       | PRI     | 0           |           |
| [map](Playercreateinfo#map)                 | mediumint(8) unsigned | NO       |         | 0           |           |
| [zone](Playercreateinfo#zone)               | mediumint(8) unsigned | NO       |         | 0           |           |
| [position\_x](Playercreateinfo#position_x)  | float                 | NO       |         | 0           |           |
| [position\_y](Playercreateinfo#position_y)  | float                 | NO       |         | 0           |           |
| [position\_z](Playercreateinfo#position_z)  | float                 | NO       |         | 0           |           |
| [orientation](Playercreateinfo#orientation) | float                 | NO       |         | 0           |           |

### Description of the fields

#### race

The character's race.

#### class

The character's class.

#### map

The map ID. See [Map.dbc](Map.dbc)

#### zone

The zone ID. See [AreaTable.dbc](AreaTable.dbc)

#### position\_x

The X position.

#### position\_y

The Y position.

#### position\_z

The Z position.
