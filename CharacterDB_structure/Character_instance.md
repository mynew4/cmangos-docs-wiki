Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;instance` table

Contains the instance data for characters.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_instance#guid|int(11) unsigned|NO|PRI|0||
|"instance":Character_instance#instance|bigint(40)|NO|MUL|0||
|"permanent":Character_instance#permanent|tinyint(1) unsigned|NO||0||


h3. Description of the fields

h4. guid

The GUID of the character. See "characters.guid":characters#guid

h4. instance

The instance ID. See "instance.id":instance#id

h4. permanent

Boolean 0 or 1 controlling if the player has been bound to the instance. A player is bound to the instance only when he (or his party/raid) kills a creature with the CREATURE&#95;FLAG&#95;EXTRA&#95;INSTANCE&#95;BIND flag set in the "flags&#95;extra":creature_template#flags_extra field.
