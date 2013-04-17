Back to "world database":mangosdb_struct list of tables.

h2. The `skill&#95;fishing&#95;base&#95;level` table

This table controls the minimum skill level required in fishing to fish in a certain area.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Skill_fishing_base_level#entry|mediumint(8) unsigned|NO|PRI|0||
|"skill":Skill_fishing_base_level#skill|smallint(6)|NO||0||


h3. Description of the fields

h4. entry

The area ID (see AreaTable.dbc).

h4. skill

The minimum skill points in fishing required to fish in the area.
