Back to "world database":mangosdb_struct list of tables.
To link creatures by entry, please refer to "Creature_linking_template":Creature_linking_template

h2. The `creature&#95;linking` table

h3. Structure


|*Name*|*Type*|*Null*|*Key*|*Default*|*Extra*|*Comment*|
|"guid":Creature_linking#guid|int(10) unsigned|NO|PRI|0||creature.guid of the slave mob that is linked|
|"master_guid":Creature_linking#master_guid|int(10) unsigned|NO||0||master to trigger events|
|"flag":Creature_linking#flag|mediumint(8) unsigned|NO||0||flag - describing what should happen when|

h3. Description of the fields

h4. guid

"creature.guid":creature#guid of the slave mob that is linked

h4. master&#95;guid

"creature.guid":creature#guid of the master to trigger events

h4. flag

flag - describing what should happen when

|_. Flag|_. Name|_. Comment|
|1|FLAG&#95;AGGRO&#95;ON&#95;AGGRO|the &quot;slave&quot; aggroes when the &quot;master&quot; aggroes|
|2|FLAG&#95;TO&#95;AGGRO&#95;ON&#95;AGGRO|the master aggroes when the slave aggroes|
|4|FLAG&#95;RESPAWN&#95;ON&#95;EVADE|the slave respawns when the master evades|
|8|FLAG&#95;TO&#95;RESPAWN&#95;ON&#95;EVADE|the master respawns when the slave evades|
|16|FLAG&#95;DESPAWN&#95;ON&#95;DEATH|the slave despawns when the master dies|
|32|FLAG&#95;SELFKILL&#95;ON&#95;DEATH|the slave goes suicide when the master dies|
|64|FLAG&#95;RESPAWN&#95;ON&#95;DEATH|the slave respawn when the master dies|
|128|FLAG&#95;RESPAWN&#95;ON&#95;RESPAWN|the slave respawns on master respawn|
|256|FLAG&#95;DESPAWN&#95;ON&#95;RESPAWN|the slave despawns on master respawn (TODO: check for slave != master)|
|512|FLAG&#95;FOLLOW|the slave follows the master, very basic, see TODO notes in commit, or post below|
|1024|FLAG&#95;CANT&#95;SPAWN&#95;IF&#95;BOSS&#95;DEAD|the slave cannot respawn while boss is dead|
|2048|FLAG&#95;CANT&#95;SPAWN&#95;IF&#95;BOSS&#95;ALIVE|the slave cannot respawn while boss is alive|
|4096|FLAG&#95;DESPAWN&#95;ON&#95;EVADE|the slave despawn after the master evade|
|8192|FLAG&#95;DESPAWN&#95;ON&#95;DESPAWN|the slave despawn after the master despawns|
