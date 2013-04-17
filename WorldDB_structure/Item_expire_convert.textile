Back to "world database":mangosdb_struct list of tables.

h2. The `item&#95;expire&#95;convert` table

This table contains pairs of times which turn into an other item after a certain amount of time.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Item_expire_convert#entry|mediumint(8) unsigned|NO|PRI|0||
|"item":Item_expire_convert#item|mediumint(8)|NO||0||


h3. Description of the fields

h4. entry

The entry of the item which suppose to change into a new item.

h4. item

The entry of the new item.
