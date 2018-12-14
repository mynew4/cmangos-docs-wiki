Back to [world database](mangosdb_struct) list of tables.

The \`game\_event\_creature\` table
-----------------------------------

Contains all creature instances that have to be spawned/unspawned during defined game events.

### Structure

| **Field**                          | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Game_event_creature#guid)   | int(10) unsigned | NO       | PRI     |             |           |
| [event](Game_event_creature#event) | mediumint(9)     | NO       |         | 0           |           |

### Description of the fields

#### guid

Guid of the creature participating in the event ([creature.guid](creature#guid))

#### event

Entry of the event ([game\_event.entry](game_event#entry))

-   Use **+**[entry](game_event#entry) to have the creature added during the event
-   Use **-**[entry](game_event#entry) to have it removed during the event

