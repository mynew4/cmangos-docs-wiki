Back to "world database":mangosdb_struct list of tables.

h2. The `exploration&#95;basexp` table

This table controls the XP gained by characters when they explore new zones.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"level":Exploration_basexp#level|tinyint(2)|NO|PRI|0||
|"basexp":Exploration_basexp#basexp|int(11)|NO||0||


h3. Description of the fields

h4. level

The level of the character.

h4. basexp

The XP the character receives at the specified level.
