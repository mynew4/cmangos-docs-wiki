Back to [world database](mangosdb_struct) list of tables.

The \`game\_event\_creature\_quest\` table
------------------------------------------

This table holds information on quests that should only be available when an event is currently taking place.

### Structure

| **Field**                                | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [id](Game_event_creature_quest#id)       | int(11) unsigned      | NO       | PRI     | 0           |           |
| [quest](Game_event_creature_quest#quest) | int(11) unsigned      | NO       | PRI     | 0           |           |
| [event](Game_event_creature_quest#event) | mediumint(9) unsigned | NO       |         | 0           |           |

### Description of the fields

#### id

The NPC ID. See [creature\_template.entry](creature_template#entry)

#### quest

The quest ID. See [quest\_template.entry](quest_template#entry)

#### event

The event ID. See [game\_event.entry](game_event#entry)
