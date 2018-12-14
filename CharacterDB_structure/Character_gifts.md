Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;gifts` table

This table holds data about wrapped/gift items.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_gifts#guid|int(20) unsigned|NO|MUL|0||
|"item_guid":Character_gifts#item_guid|int(11) unsigned|NO|PRI|0||
|"entry":Character_gifts#entry|int(20) unsigned|NO||0||
|"flags":Character_gifts#flags|int(20) unsigned|NO||0||


h3. Description of the fields

h4. guid

The GUID of the character. See "character.guid":character#guid

h4. item&#95;guid

The GUID of the item. See "item&#95;instance.guid":item_instance#guid

h4. entry

The entry of the item. See "item&#95;template.entry":item_template#entry

h4. flags
