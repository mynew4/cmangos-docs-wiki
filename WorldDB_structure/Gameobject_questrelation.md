Back to "world database":mangosdb_struct list of tables.

h2. The `gameobject&#95;questrelation` table

Holds game object quest giver relations. The game objects in this table should all be of type QUESTGIVER (2).

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Gameobject_questrelation#id|int(10) unsigned|NO|PRI|0||
|"quest":Gameobject_questrelation#quest|int(10) unsigned|NO|PRI|0||


h3. Description of the fields

h4. id

The template ID of the game object. See "gameobject&#95;template.entry":gameobject_template#entry

h4. quest

The quest ID that this game object starts. See "quest&#95;template.entry":quest_template#entry
