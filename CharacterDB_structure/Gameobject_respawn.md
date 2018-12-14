Back to "world database":mangosdb_struct list of tables.

h2. The `gameobject&#95;respawn` table

This table holds the respawn time when game objects should be respawned in the world. In case of a server crash, this table holds the respawn data so that the game objects don't respawn immediately on server restart. How often the respawn time is saved for game objects can be controlled in mangosd.conf at SaveRespawnTimeImmediately. Usually the only objects that despawn and need to be respawned are chests and doors.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Gameobject_respawn#guid|int(11) unsigned|NO|PRI|0||
|"respawntime":Gameobject_respawn#respawntime|bigint(40)|NO||0||
|"instance":Gameobject_respawn#instance|int(11) unsigned|NO|PRI|0||


h3. Description of the fields

h4. guid

The GUID of the game object. See "gameobject.guid":gameobject#guid

h4. respawntime

The time when the game object should be respawned in Unix time.

h4. instance

If the game object belonged in an instance, this field holds the instance ID where this game object should be respawned. Each instance is different depending on the group so this field is vital in keeping track of which game objects should be respawned for which players at what time.
