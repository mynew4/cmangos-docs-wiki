Back to "world database":mangosdb_struct list of tables.

h2. The `game&#95;tele` table

This table contains a list of teleport locations that can be used with the .tele command in-game. Entries in this table can be added/deleted manually or with the .addtele/.deltele commands.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Game_tele#id|int(10) unsigned|NO|PRI|None|auto&#95;increment|
|"position_x":Game_tele#position_x|float|NO||0||
|"position_y":Game_tele#position_y|float|NO||0||
|"position_z":Game_tele#position_z|float|NO||0||
|"orientation":Game_tele#orientation|float|NO||0||
|"map":Game_tele#map|int(10) unsigned|NO||0||
|"name":Game_tele#name|varchar(100)|NO||||


h3. Description of the fields

h4. id

The ID of the teleport location. This number is unique to every location added.

h4. position&#95;x

The X position where the location exists.

h4. position&#95;y

The Y position where the location exists.

h4. position&#95;z

The Z position where the location exists.

h4. orientation

The orientation to face after teleport. (North = 0, South = 3.14159)

h4. map

The map ID of the location. See "Map.dbc":Map.dbc

h4. name

The name given to the location. The name must not have a space as this will be read in from the .tele command.
