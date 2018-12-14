Back to "world database":mangosdb_struct list of tables.

h2. The `player&#95;classlevelstats` table

This table holds information on the base health and mana of characters when they level up. Each class has different level stats. All of the values in this table signify only the base health and mana of the class at a specific level.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"class":Player_classlevelstats#class|tinyint(3) unsigned|NO|PRI|||
|"level":Player_classlevelstats#level|tinyint(3) unsigned|NO|PRI|||
|"basehp":Player_classlevelstats#basehp|smallint(5) unsigned|NO||||
|"basemana":Player_classlevelstats#basemana|smallint(5) unsigned|NO||||
||


h3. Description of the fields

h4. class

The character class. 

h4. level

The level at which the stats should be applied.

h4. basehp

The base health of the character (before stamina bonuses).

h4. basemana

The base mana of the character (before intellect bonuses).
