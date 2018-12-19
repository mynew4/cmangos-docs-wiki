Back to [world database](mangosdb_struct) list of tables.

The \`game\_event\_creature\_data\` table
-----------------------------------------

Contains all creature instances that need to change display id and/or equipment during defined game events.

### Structure

| **Field**                                              | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [guid](Game_event_creature_data#guid)                  | int(10) unsigned      | NO       | PRI     |             |           |
| [entry\_id](Game_event_creature_data#id)               | mediumint(8) unsigned | NO       |         |             |           |
| [modelid](Game_event_creature_data#modelid)            | mediumint(8) unsigned | NO       |         | 0           |           |
| [equipment\_id](Game_event_creature_data#equipment_id) | mediumint(8) unsigned | NO       |         | 0           |           |
| [spell\_start](Game_event_creature_data#spell_start)   | mediumint(8) unsigned | NO       |         | 0           |           |
| [spell\_end](Game_event_creature_data#spell_end)       | mediumint(8) unsigned | NO       |         | 0           |           |
| [event](Game_event_creature_data#event)                | mediumint(5) unsigned | NO       | PRI     | 0           |           |

### Description of the fields

#### guid

Guid of the creature participating in the event ([creature.guid](creature#guid))

#### entry\_id

Creature\_template entry to change the GUID to during the event

#### modelid

New model to be used while the event is active (Refers to [creature\_model\_info.modelid](creature_model_info#modelid)) Use 0 if only the [equipment](#equipment_id) is to be changed during event.

#### equipment\_id

New equipment to be used during the event (Refers to [creature\_equip\_template.entry](creature_equip_template#entry))) Use 0 if only the [model](#modelid) is to be changed during event.

#### spell\_start

Spell for NPC to cast when game event starts

#### spell\_end

Spell for NPC to cast when game event ends

#### event

Entry of the event ([game\_event.entry](game_event#entry))

-   In this table, event entry can only be positive

