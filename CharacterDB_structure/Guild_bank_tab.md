Back to "characters database":charactersdb_struct list of tables.

h2. The `guild&#95;bank&#95;tab` table

This table holds information on all of the tabs in use for all guilds who make use of the guild bank.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guildid":Guild_bank_tab#guildid|int(11) unsigned|NO|PRI|0||
|"TabId":Guild_bank_tab#tabid|tinyint(1) unsigned|NO|PRI|0||
|"TabName":Guild_bank_tab#tabname|varchar(100)|NO||||
|"TabIcon":Guild_bank_tab#tabicon|varchar(100)|NO||||
|"TabText":Guild_bank_tab#tabtext|varchar(100)|NO||||


h3. Description of the fields

h4. guildid

The guild ID that the guild bank belongs to.

h4. TabId

The tab ID.

h4. TabName

The name assigned to the tab.

h4. TabIcon

The icon assigned to the tab.

h4. TabText

The text assigned to the tab.
