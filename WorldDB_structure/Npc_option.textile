Back to "world database":mangosdb_struct list of tables.

h2. The `npc&#95;option` table

This table holds info about how gossip menus are presented to you. It also contains default gossip for option menus.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Npc_option#id|int(10) unsigned|NO|PRI|0||
|"gossip_id":Npc_option#gossip_id|int(10) unsigned|NO||0||
|"npcflag":Npc_option#npcflag|int(10) unsigned|NO||0||
|"icon":Npc_option#icon|int(10) unsigned|NO||0||
|"action":Npc_option#action|int(10) unsigned|NO||0||
|"option_text":Npc_option#option_text|text|YES||||


h3. Description of the fields

h4. id

An arbitrary number that is not associated with any other table.

h4. gossip&#95;id

Link to parent "npc&#95;option.id":npc_option#id.

h4. npcflag

This the is the "creature&#95;template.npcflag":creature_template#npcflag that is associated with this option.

h4. icon

This is the icon that is displayed next to the option in the gossip menu.

h4. action

The action to perform. (paste section of code that lists this)

h4. option&#95;text

The text for this particular option
