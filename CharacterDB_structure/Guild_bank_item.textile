Back to "characters database":charactersdb_struct list of tables.

h2. The `guild&#95;bank&#95;item` table

This table holds all item information for items that are stored in the guild bank.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guildid":Guild_bank_item#guildid|int(11) unsigned|NO|PRI|0||
|"TabId":Guild_bank_item#tabid|tinyint(1) unsigned|NO|PRI|0||
|"SlotId":Guild_bank_item#slotid|tinyint(3) unsigned|NO|PRI|0||
|"item_guid":Guild_bank_item#item_guid|int(11) unsigned|NO|MUL|0||
|"item_entry":Guild_bank_item#item_entry|int(11) unsigned|NO||0||


h3. Description of the fields

h4. guildid

The guild ID who owns the bank. See "guild.guildid":guild#guildid

h4. TabId

The tab ID where the item is currently placed in. See "guild&#95;bank&#95;tab.TabId":guild_bank_tab#TabId

h4. SlotId

The slot that the item is placed in in the tab.

h4. item&#95;guid

The item guid. See "item&#95;instance.guid":item_instance#guid

h4. item&#95;entry

The item template ID for the item. See "item&#95;template.entry":item_template#entry
