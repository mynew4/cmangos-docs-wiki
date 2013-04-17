Back to "world database":mangosdb_struct list of tables.

h2. The `scriped&#95;event&#95;id` table

This table links event id's to C++ scripts.

h3. Structure


|Field|Type|NULL|Key|Default|Comments|
|"entry":Scripted_event_id#entry|mediumint (8)|NO|PRI||Identifier|
|"ScriptName":Scripted_event_id#scriptname|CHAR (64)|NO|||Script Identifier|


h3. Description of the fields

h4. entry

This is the event id identifier

h4. ScriptName

The name of the script that this event uses, if any. This ties a script from a scripting engine to this trigger.
