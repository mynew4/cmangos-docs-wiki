Back to "world database":mangosdb_struct list of tables.

h2. The `game&#95;event&#95;pool` table

Contains all pool instances that participate to any game event.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"pool_entry":Game_event_pool#pool_entry|mediumint(8) unsigned|NO||0||
|"event":Game_event_pool#event|smallint(6)|NO||0||


h3. Description of the fields

h4. pool&#95;entry

Pool's ID. See "pool_template":pool_template

h4. event

Event's ID. Put negatives values to remove during event. See "game_event":game_event
