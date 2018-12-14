Back to "world database":mangosdb_struct list of tables.

h2. The `playercreateinfo` table

This table holds the start positions of each class-race combinations for all newly created characters.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"race":Playercreateinfo#race|tinyint(3) unsigned|NO|PRI|0||
|"class":Playercreateinfo#class|tinyint(3) unsigned|NO|PRI|0||
|"map":Playercreateinfo#map|mediumint(8) unsigned|NO||0||
|"zone":Playercreateinfo#zone|mediumint(8) unsigned|NO||0||
|"position_x":Playercreateinfo#position_x|float|NO||0||
|"position_y":Playercreateinfo#position_y|float|NO||0||
|"position_z":Playercreateinfo#position_z|float|NO||0||
|"orientation":Playercreateinfo#orientation|float|NO||0||


h3. Description of the fields

h4. race

The character's race. 

h4. class

The character's class. 

h4. map

The map ID. See "Map.dbc":Map.dbc

h4. zone

The zone ID. See "AreaTable.dbc":AreaTable.dbc

h4. position&#95;x

The X position.

h4. position&#95;y

The Y position.

h4. position&#95;z

The Z position.
