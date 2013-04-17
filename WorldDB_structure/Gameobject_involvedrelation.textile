Back to "world database":mangosdb_struct list of tables.

h2. The `gameobject&#95;involvedrelation` table

Holds game object quest taker relations. The game objects in this table should all be of type QUESTGIVER (2).

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Gameobject_involvedrelation#id|int(10) unsigned|NO|PRI|0||
|"quest":Gameobject_involvedrelation#quest|int(10) unsigned|NO|PRI|0||


h3. Description of the fields

h4. id

The template ID of the game object. See "gameobject&#95;template.entry":gameobject_template#entry

h4. quest

The quest ID that this game object finishes. See "quest&#95;template.entry":quest_template#entry
