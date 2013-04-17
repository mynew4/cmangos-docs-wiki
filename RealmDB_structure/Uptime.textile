Back to "world database":mangosdb_struct list of tables.

h2. The `uptime` table

This table holds the server's uptime. Mangos will automatically update the latest entry's value until it crashes and a new record is added.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"starttime":Uptime#starttime|bigint(11) unsigned|NO|PRI|0||
|"startstring":Uptime#startstring|varchar(64)|NO||||
|"uptime":Uptime#uptime|bigint(11) unsigned|NO||0||
|"maxplayers":Uptime#maxplayers|int(11) unsigned|NO||0||


h3. Description of the fields

h4. starttime

The time when the server was started, in Unix time.

h4. startstring

The time when the server started, formated as a readable string.

h4. uptime

The uptime of the server, in seconds.

h4. maxplayers

The maximum number of players connected.
