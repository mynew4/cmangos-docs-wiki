Back to [world database](mangosdb_struct) list of tables.

The \`game\_event\_pool\` table
-------------------------------

Contains all pool instances that participate to any game event.

### Structure

| **Field**                                 | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [pool\_entry](Game_event_pool#pool_entry) | mediumint(8) unsigned | NO       |         | 0           |           |
| [event](Game_event_pool#event)            | smallint(6)           | NO       |         | 0           |           |

### Description of the fields

#### pool\_entry

Pool's ID. See [pool\_template](pool_template)

#### event

Event's ID. Put negatives values to remove during event. See [game\_event](game_event)
