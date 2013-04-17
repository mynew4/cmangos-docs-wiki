Back to "world database":mangosdb_struct list of tables.

h2. The `pet&#95;levelstats` table

This table holds information on individual pet base stats based on level.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"creature_entry":Pet_levelstats#creature_entry|int(10) unsigned|NO|PRI|||
|"level":Pet_levelstats#level|tinyint(3) unsigned|NO|PRI|||
|"hp":Pet_levelstats#hp|smallint(5) unsigned|NO||||
|"mana":Pet_levelstats#mana|smallint(5) unsigned|NO||||
|"armor":Pet_levelstats#armor|int(10) unsigned|NO||0||
|"str":Pet_levelstats#str|smallint(5) unsigned|NO||||
|"agi":Pet_levelstats#agi|smallint(5) unsigned|NO||||
|"sta":Pet_levelstats#sta|smallint(5) unsigned|NO||||
|"inte":Pet_levelstats#inte|smallint(5) unsigned|NO||||
|"spi":Pet_levelstats#spi|smallint(5) unsigned|NO||||


h3. Description of the fields

h4. creature&#95;entry

The pet creature template ID. See "creature&#95;template.entry":creature_template#entry

h4. level

The pet level.

h4. hp

The base health of the pet at level = "level":#level.

h4. mana

The base mana of the pet at level = "level":#level.

h4. armor

The base armor of the pet at level = "level":#level.

h4. str

The base strength of the pet at level = "level":#level.

h4. agi

The base agility of the pet at level = "level":#level.

h4. sta

The base stamina of the pet at level = "level":#level.

h4. inte

The base intelligence of the pet at level = "level":#level.

h4. spi

The base spirit of the pet at level = "level":#level.
