Back to "world database":mangosdb_struct list of tables.

h2. The `scripted&#95;areatrigger` table

This table links areatriggers to C++ scripts.

h3. Structure


|Field|Type|NULL|Key|Default|Comments|
|"entry":Scripted_areatrigger#entry|mediumint (8)|NO|PRI||Identifier|
|"ScriptName":Scripted_areatrigger#scriptname|CHAR (64)|NO|||Script Identifier|


h3. Description of the fields

h4. entry

This is the trigger identifier from AreaTrigger.dbc

h4. ScriptName

The name of the script that this areatrigger uses, if any. This ties a script from a scripting engine to this trigger.
