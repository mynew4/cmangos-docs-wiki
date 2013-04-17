Back to "world database":mangosdb_struct list of tables.

h2. The `battlemaster&#95;entry` table

Holds information on which NPC can start what battleground or arena.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Battlemaster_entry#entry|mediumint(8) unsigned|NO|PRI|0|Entry of a creature|
|"bg_template":Battlemaster_entry#bg_template|mediumint(8) unsigned|NO||0|Battleground template id|


h3. Description of the fields

h4. entry

The ID of the creature. See "creature&#95;template.entry":creature_template#entry

h4. bg&#95;template

The battleground template ID. See "Battleground_template":Battleground_template
