Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;homebind` table

Contains information on the location where characters get teleported when they use for example the soul stone or the .start command.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_homebind#guid|int(11) unsigned|NO|PRI|0||
|"map":Character_homebind#map|int(11) unsigned|NO||0||
|"zone":Character_homebind#zone|int(11) unsigned|NO||0||
|"position_x":Character_homebind#position_x|float|NO||0||
|"position_y":Character_homebind#position_y|float|NO||0||
|"position_z":Character_homebind#position_z|float|NO||0||


h3. Description of the fields

h4. guid

The GUID of the character. See "character.guid":character#guid

h4. map

The map ID where the character gets teleported to. See "Map.dbc":Map.dbc column 1

h4. zone

The zone ID where the character gets teleported to. See WorldMapArea.dbc column 1

h4. position&#95;x

The x position where the character gets teleported to.

h4. position&#95;y

The y position where the character gets teleported to.

h4. position&#95;z

The z position where the character gets teleported to.
