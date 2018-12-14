Back to "world database":mangosdb_struct list of tables.

h2. The `game&#95;event&#95;creature&#95;quest` table

This table holds information on quests that should only be available when an event is currently taking place.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Game_event_creature_quest#id|int(11) unsigned|NO|PRI|0||
|"quest":Game_event_creature_quest#quest|int(11) unsigned|NO|PRI|0||
|"event":Game_event_creature_quest#event|mediumint(9) unsigned|NO||0||


h3. Description of the fields

h4. id

The NPC ID. See "creature&#95;template.entry":creature_template#entry

h4. quest

The quest ID. See "quest&#95;template.entry":quest_template#entry

h4. event

The event ID. See "game&#95;event.entry":game_event#entry
