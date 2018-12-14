Back to "characters database":charactersdb_struct list of tables.

h2. The `instance` table

This table holds static information on all current instances that have not yet been reset.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Instance#id|int(11) unsigned|NO|PRI|0||
|"map":Instance#map|int(11) unsigned|NO|MUL|0||
|"resettime":Instance#resettime|bigint(40)|NO|MUL|0||
|"difficulty":Instance#difficulty|tinyint(1)|NO||0||
|"data":Instance#data|longtext|YES||||


h3. Description of the fields

h4. id

The instance ID. This number is unique to every instance.

h4. map

The map ID the instance is in. See "Map.dbc":Map.dbc

h4. resettime

The time when the instance will be reset, in Unix time. This field is zero for raid and heroic instances.

h4. difficulty

The difficulty of the current instance. 1 = heroic, 0 = normal

h4. data

Specific data belonging to the individual instance.
