Back to "world database":mangosdb_struct list of tables.

h2. The `playercreateinfo&#95;spell` table

This table holds information on what spells newly created characters should start out with. A character in this table is defined by his/her race and class combination.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"race":Playercreateinfo_spell#race|tinyint(3) unsigned|NO|PRI|0||
|"class":Playercreateinfo_spell#class|tinyint(3) unsigned|NO|PRI|0||
|"Spell":Playercreateinfo_spell#spell|bigint(20) unsigned|NO|PRI|0||
|"Note":Playercreateinfo_spell#note|varchar(255)|YES||||
|"Active":Playercreateinfo_spell#active|tinyint(3) unsigned|NO||1||


h3. Description of the fields

h4. race

The character's race. 

h4. class

The character's class. 

h4. Spell

The spell ID. See Spell.dbc

h4. Note

A note explaining what the spell is. This is only for reference purposes and not used by mangos.

h4. Active

Boolean 0 or 1 controlling if the spell is active or not.
