h3. *The `instance&#95;reset` table*

This table hold information about instance reset time.

h3. *Structure*


|<strong>*Field*</strong>|<strong>*Type*</strong>|<strong>*Null*</strong>|<strong>*Key*</strong>|<strong>*Default*</strong>|
|"mapid":Instance_reset#mapid|int(11) unsigned|NO|PRI|0|
|"difficulty":Instance_reset#difficulty|tinyint(1)|NO||0|
|"resettime":Instance_reset#resettime|bigint(40) unsigned|NO||0|
||


h3. *Description of the fields*

h2. mapid

The map ID of the instance. See Map.dbc

h2. difficulty

Dungeon difficulty

h2. resettime

Dungeon reset time in seconds.
