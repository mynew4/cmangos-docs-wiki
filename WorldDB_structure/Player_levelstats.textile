Back to "world database":mangosdb_struct list of tables.

h2. The `player&#95;levelstats` table

This table holds information on what stats are gained by characters when they level up. Each race-class combination has different level stats. All of the values in this table signify only the base stats of the race-class combination at a specific level.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"race":Player_levelstats#race|tinyint(3) unsigned|NO|PRI|||
|"class":Player_levelstats#class|tinyint(3) unsigned|NO|PRI|||
|"level":Player_levelstats#level|tinyint(3) unsigned|NO|PRI|||
|"str":Player_levelstats#str|tinyint(3) unsigned|NO||||
|"agi":Player_levelstats#agi|tinyint(3) unsigned|NO||||
|"sta":Player_levelstats#sta|tinyint(3) unsigned|NO||||
|"inte":Player_levelstats#inte|tinyint(3) unsigned|NO||||
|"spi":Player_levelstats#spi|tinyint(3) unsigned|NO||||


h3. Description of the fields

h4. race

The character race. This field along with "class":#class defines what stats to be applied on the character. 

h4. class

The character class. This field along with "race":#race defines what stats to be applied on the character. 

h4. level

The level at which the stats should be applied.

h4. str

The base strength of the character.

h4. agi

The base agility of the character.

h4. sta

The base stamina of the character.

h4. inte

The base intellect of the character.

h4. spi

The base spirit of the character.
