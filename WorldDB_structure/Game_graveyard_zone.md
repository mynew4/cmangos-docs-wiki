Back to [world database](mangosdb_struct) list of tables.

The \`game\_graveyard\_zone\` table
-----------------------------------

Contains informations about zones connected to world's graveyards.

This table set if character die in zone ghost\_zone and graveyard with id accept his team (HORDE or ALIANCE or both) and this is nearest graveyard then character's ghost will be teleported to graveyard id.

For a list of all existing graveyard zones and their respective IDs, check out [WorldSafeLocs.dbc](WorldSafeLocs.dbc)

### Structure

| **Field**                                     | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------|------------------|----------|---------|-------------|-----------|
| [id](Game_graveyard_zone#id)                  | int(10) unsigned | NO       |         | 0           |           |
| [ghost\_zone](Game_graveyard_zone#ghost_zone) | int(10) unsigned | NO       |         | 0           |           |
| [faction](Game_graveyard_zone#faction)        | int(10) unsigned | NO       |         | 0           |           |

### Description of the fields

#### id

Graveyard's ID. See [WorldSafeLocs.dbc](WorldSafeLocs.dbc)

#### ghost\_zone

Zone's Id of ghost position before teleportation to graveyard. See [AreaTable.dbc](AreaTable.dbc)

#### faction

Graveyard's team.

0 - Any team's accepted

469 - ALLIANCE team accepted only

67 - HORDE team accepted only
