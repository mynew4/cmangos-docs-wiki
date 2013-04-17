Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;reputation` table

This table holds the reputation information for each character.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_reputation#guid|int(11) unsigned|NO|PRI|0||
|"faction":Character_reputation#faction|int(11) unsigned|NO|PRI|0||
|"standing":Character_reputation#standing|int(11)|NO||0||
|"flags":Character_reputation#flags|int(11)|NO||0||


h3. Description of the fields

h4. guid

The GUID of the character. See "character.guid":character#guid

h4. faction

The faction ID that the character has the given reputation in. See "Faction.dbc":Faction.dbc

h4. standing

The current reputation value that the character has. 

h4. flags

This field is a bitmask containing flags that apply to the faction and how it's displayed to the character. Just like any flag field, you can combine flags by adding them together. If this field is 0, then it is not shown in the reputation list in-game.

|_. Flag|_. Name|_. Comments|
|1|FACTION&#95;FLAG&#95;VISIBLE|Displayed in the reputation tab|
|2|FACTION&#95;FLAG&#95;AT&#95;WAR|Active when the player sets the at war checkbox|
|4|FACTION&#95;FLAG&#95;UNKNOWN||
|8|FACTION&#95;FLAG&#95;INVISIBLE||
|16|FACTION&#95;FLAG&#95;OWN&#95;TEAM||
|32|FACTION&#95;FLAG&#95;INACTIVE||

