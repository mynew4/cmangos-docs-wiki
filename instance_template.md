Back to "world database":mangosdb_struct list of tables.

h2. The `instance_template` table

This table has all the templates for every instance. When a group enters an instance, a new copy of that instance is made from the values in these fields.

h3. Structure

|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"map":Instance_template#map|int(10) unsigned|NO|PRI|||
|"parent":Instance_template#parent|int(11) unsigned|NO||||
|"levelMin":Instance_template#levelmin|int(10) unsigned|NO||0||
|"levelMax":Instance_template#levelmax|int(10) unsigned|NO||0||
|"maxPlayers":Instance_template#maxplayers|int(10) unsigned|NO||0||
|"reset_delay":Instance_template#reset_delay|int(10) unsigned|NO||0||
|"ScriptName":Instance_template#ScriptName|varchar(255)|NO||||
|"mountAllowed":Instance_template#mountAllowed|tinyint(3) unsigned|NO||0||

h3. Description of the fields

h4. map

The map ID of the instance. See Map.dbc

h4. parent

If the instance is a subinstance of another instance, this field has the parent instance's map ID.

h4. levelMin

The minimum level required to enter the instance.

h4. levelMax

The maximum level required to be able to be summoned by the meeting stone for this instance.

h4. maxPlayers

The maximum number of players that can enter as a group/raid in the instance.

h4. reset_delay

The number of days between each global reset for the map. If zero, the value is taken from DBC files. The resulting value is multiplied by the Rate.InstanceResetTime config.

h4. ScriptName

The name of the instance script that the instance will use and apply (if any).

h4. mountAllowed

Possible or not use mounts in this instance.