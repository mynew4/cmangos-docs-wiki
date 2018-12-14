Back to [world database](mangosdb_struct) list of tables.

The \`game\_tele\` table
------------------------

This table contains a list of teleport locations that can be used with the .tele command in-game. Entries in this table can be added/deleted manually or with the .addtele/.deltele commands.

### Structure

| **Field**                            | **Type**         | **Null** | **Key** | **Default** | **Extra**       |
|--------------------------------------|------------------|----------|---------|-------------|-----------------|
| [id](Game_tele#id)                   | int(10) unsigned | NO       | PRI     | None        | auto\_increment |
| [position\_x](Game_tele#position_x)  | float            | NO       |         | 0           |                 |
| [position\_y](Game_tele#position_y)  | float            | NO       |         | 0           |                 |
| [position\_z](Game_tele#position_z)  | float            | NO       |         | 0           |                 |
| [orientation](Game_tele#orientation) | float            | NO       |         | 0           |                 |
| [map](Game_tele#map)                 | int(10) unsigned | NO       |         | 0           |                 |
| [name](Game_tele#name)               | varchar(100)     | NO       |         |             |                 |

### Description of the fields

#### id

The ID of the teleport location. This number is unique to every location added.

#### position\_x

The X position where the location exists.

#### position\_y

The Y position where the location exists.

#### position\_z

The Z position where the location exists.

#### orientation

The orientation to face after teleport. (North = 0, South = 3.14159)

#### map

The map ID of the location. See [Map.dbc](Map.dbc)

#### name

The name given to the location. The name must not have a space as this will be read in from the .tele command.
