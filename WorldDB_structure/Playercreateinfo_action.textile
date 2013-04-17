Back to "world database":mangosdb_struct list of tables.

h2. The `playercreateinfo&#95;action` table

This table holds information on what default actions a brand new character should start out with. Each race-class combination can have a different default starting setup.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"race":Playercreateinfo_action#race|tinyint(3) unsigned|NO|MUL|0||
|"class":Playercreateinfo_action#class|tinyint(3) unsigned|NO||0||
|"button":Playercreateinfo_action#button|smallint(2) unsigned|NO||0||
|"action":Playercreateinfo_action#action|smallint(6) unsigned|NO||0||
|"type":Playercreateinfo_action#type|smallint(3) unsigned|NO||0||
|"misc":Playercreateinfo_action#misc|smallint(3) unsigned|NO||0||


h3. Description of the fields

h4. race

The character's race. 

h4. class

The character's class. 

h4. button

The ID of the button on the action bar where the action icon will be placed.
Special bars are used for stances, auras, pets, stealth, and other similar special modes.

|_. Button IDs|_. Set (key)|
|1-11|1 (SHIFT + 1)|
|12-23|2 (SHIFT + 2)|
|24-35|3 (SHIFT + 3) == Right Side Bar|
|36-47|4 (SHIFT + 4) == Right Side Bar 2|
|48-59|5 (SHIFT + 5) == Bottom Right Bar|
|60-71|6 (SHIFT + 6) == Bottom Left Bar|
|72-83|1 SpecialA|
|84-95|1 SpecialB|
|96-107|1 SpecialC|
|108-119|1 SpecialD|


h4. action

Depending on the type value, this could be either the spell ID (Spell.dbc), the "item ID":item_template#entry or macro ID.

h4. type

The type of action:


|0|Spell|
|64|Macro|
|128|Item|


h4. misc
