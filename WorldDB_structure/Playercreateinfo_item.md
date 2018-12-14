Back to "world database":mangosdb_struct list of tables.

h2. The `playercreateinfo&#95;item` table

This table holds information on what items each race-class combination of a new character starts out with.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"race":Playercreateinfo_item#race|tinyint(3) unsigned|NO|MUL|0||
|"class":Playercreateinfo_item#class|tinyint(3) unsigned|NO||0||
|"itemid":Playercreateinfo_item#itemid|mediumint(8) unsigned|NO||0||
|"amount":Playercreateinfo_item#amount|tinyint(8) unsigned|NO||1||


h3. Description of the fields

h4. race

The character's race. 

h4. class

The character's class. 

h4. itemid

The template ID of the item. See "item&#95;template.entry":item_template#entry

h4. amount

The number of copies of that item.
