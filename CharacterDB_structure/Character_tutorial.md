Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;tutorial` table

This table is used to store the tutorial state of all the characters.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_tutorial#guid|int(11) unsigned|NO|PRI|0||
|"tut0":Character_tutorial#tut0-7|int(11) unsigned|NO||0||
|"tut1":Character_tutorial#tut0-7|int(11) unsigned|NO||0||
|"tut2":Character_tutorial#tut0-7|int(11) unsigned|NO||0||
|"tut3":Character_tutorial#tut0-7|int(11) unsigned|NO||0||
|"tut4":Character_tutorial#tut0-7|int(11) unsigned|NO||0||
|"tut5":Character_tutorial#tut0-7|int(11) unsigned|NO||0||
|"tut6":Character_tutorial#tut0-7|int(11) unsigned|NO||0||
|"tut7":Character_tutorial#tut0-7|int(11) unsigned|NO||0||


h3. Description of the fields

h4. guid

Guid of the player. See "character.guid":character#guid.

h4. tut0-7

These values 32bits flags. So 8 x 32bits values makes 256 bits available to store 256 tutorial messages status.

Each bit means:

bc.   0  -  Not yet shown
  1  -  Shown


This is used to diplay only tutorial messages the character did not see before.

Unselecting the &quot;Show tutorial&quot; option in game, makes all bits to be set, so all tutX columns will contain then 11111111111111111111111111111111 binary = 4294967295 in decimal after this option is changed.
