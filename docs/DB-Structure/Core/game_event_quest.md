Back to [world database](mangosdb_struct) list of tables.

## The `game_event_quest` table

holds quests, which are only active during certain events.

### Structure

| Field| Type| Null| Key| Default| Extra|
| ---|---| ---|--- |--- |--- |
|[quest](Quest_template#entry)|int(8) unsigned|NO|PRI|||
|[event](Game_event#entry)|int(5) unsigned|NO|PRI|0||

#### quest

[quest_template.entry](Quest_template#entry) of the quest.

#### event

[game_event.entry](Game_event#entry) of the game event.