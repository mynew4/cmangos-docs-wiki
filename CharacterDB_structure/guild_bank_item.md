Back to [characters database](charactersdb_struct) list of tables.

The \`guild\_bank\_item\` table
-------------------------------

This table holds all item information for items that are stored in the guild bank.

### Structure

| **Field**                                 | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [guildid](Guild_bank_item#guildid)        | int(11) unsigned    | NO       | PRI     | 0           |           |
| [TabId](Guild_bank_item#tabid)            | tinyint(1) unsigned | NO       | PRI     | 0           |           |
| [SlotId](Guild_bank_item#slotid)          | tinyint(3) unsigned | NO       | PRI     | 0           |           |
| [item\_guid](Guild_bank_item#item_guid)   | int(11) unsigned    | NO       | MUL     | 0           |           |
| [item\_entry](Guild_bank_item#item_entry) | int(11) unsigned    | NO       |         | 0           |           |

### Description of the fields

#### guildid

The guild ID who owns the bank. See [guild.guildid](guild#guildid)

#### TabId

The tab ID where the item is currently placed in. See [guild\_bank\_tab.TabId](guild_bank_tab#TabId)

#### SlotId

The slot that the item is placed in in the tab.

#### item\_guid

The item guid. See [item\_instance.guid](item_instance#guid)

#### item\_entry

The item template ID for the item. See [item\_template.entry](item_template#entry)
