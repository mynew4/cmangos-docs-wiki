Back to "world database":mangosdb_struct list of tables.

h2. The `gameobject&#95;battleground` table

This table contains the events of gameobjects which are spawned on battlegrounds.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|
|"guid":Gameobject_battleground#guid|int(10) unsigned|NO|PRI|NULL|
|"event1":Gameobject_battleground#event1|tinyint(3) unsigned|NO||NULL|
|"event2":Gameobject_battleground#event2|tinyint(3) unsigned|NO||NULL|


h3. Description of the fields

h4. guid

The global unique identifier for the game object. This field must be unique among all game objects and is linked to the gameobject-table.

h4. event1

main event

h4. event2

sub event
