Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_homebind\` table
---------------------------------

Contains information on the location where characters get teleported when they use for example the soul stone or the .start command.

### Structure

| **Field**                                    | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Character_homebind#guid)              | int(11) unsigned | NO       | PRI     | 0           |           |
| [map](Character_homebind#map)                | int(11) unsigned | NO       |         | 0           |           |
| [zone](Character_homebind#zone)              | int(11) unsigned | NO       |         | 0           |           |
| [position\_x](Character_homebind#position_x) | float            | NO       |         | 0           |           |
| [position\_y](Character_homebind#position_y) | float            | NO       |         | 0           |           |
| [position\_z](Character_homebind#position_z) | float            | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### map

The map ID where the character gets teleported to. See [Map.dbc](Map.dbc) column 1

#### zone

The zone ID where the character gets teleported to. See WorldMapArea.dbc column 1

#### position\_x

The x position where the character gets teleported to.

#### position\_y

The y position where the character gets teleported to.

#### position\_z

The z position where the character gets teleported to.
