Back to [world database](https://github.com/cmangos/issues/wiki/mangosdb_struct) list of tables.

## The `game_event_quest` table

holds quests, which are only active during certain events.

### Structure

| Field| Type| Null| Key| Default| Extra|
| ---|---| ---|--- |--- |--- |
|[quest](https://github.com/cmangos/issues/wiki/Quest_template#entry)|int(8) unsigned|NO|PRI|||
|[event](https://github.com/cmangos/issues/wiki/Game_event#entry)|int(5) unsigned|NO|PRI|0||

#### quest

[quest_template.entry](https://github.com/cmangos/issues/wiki/Quest_template#entry) of the quest.

#### event

[game_event.entry](https://github.com/cmangos/issues/wiki/Game_event#entry) of the game event.