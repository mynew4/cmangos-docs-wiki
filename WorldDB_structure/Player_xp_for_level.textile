Back to "world database":mangosdb_struct list of tables.

h2. The `player&#95;xp&#95;for&#95;level` table

Includes information on how much experience needed for next level. Comes from sniffs.

h3. Structure


|*Field*|*Type*|*Attributes*|*Key*|*Null*|*Default*|*Extra*|*Comment*|
|"lvl":Player_xp_for_level#lvl|int(3)|unsigned|PRI|NO|NULL|||
|"xp_for_next_level":Player_xp_for_level#xp_for_next_level|int(10)|unsigned||NO|NULL|||


h3. Description of the fields

This table sets the exp point needed to upgrade the player's level.

h4. lvl

The player's level.

h4. xp&#95;for&#95;next&#95;level

The experience needed to upgrade from the value in &quot;lvl&quot; field to &quot;lvl&quot; +1.
