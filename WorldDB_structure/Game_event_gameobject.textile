Back to "world database":mangosdb_struct list of tables.

h2. The `game&#95;event&#95;gameobject` table

Contains all gameobjects instances that participate to any game event.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Game_event_gameobject#guid|int(10) unsigned|NO|PRI|||
|"event":Game_event_gameobject#event|mediumint(9)|NO||0||


h3. Description of the fields

h4. guid

Guid of the gameobject participating in the event ("gameobject.guid":gameobject#guid)

h4. event

Entry of the event ("game&#95;event.entry":game_event#entry)

* Use *+*"entry":game_event#entry to have the gameobject added during the event
* Use *-*"entry":game_event#entry to have it removed during the event
