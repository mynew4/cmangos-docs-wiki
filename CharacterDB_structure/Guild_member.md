Back to the "characters database":charactersdb_struct list of tables.

h2. The `guild&#95;member` table

This table holds information on the members of all guilds, their ranks in the guild, and any notes made by them or by guild officers.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guildid":Guild_member#guildid|int(6) unsigned|NO|MUL|0||
|"guid":Guild_member#guid|int(11) unsigned|NO|MUL|0||
|"rank":Guild_member#rank|tinyint(2) unsigned|NO||0||
|"pnote":Guild_member#pnote|varchar(255)|NO||||
|"offnote":Guild_member#offnote|varchar(255)|NO||||
|"BankResetTimeMoney":Guild_member#bankresettimemoney|int(11) unsigned|NO||0||
|"BankRemMoney":Guild_member#bankremmoney|int(11) unsigned|NO||0||
|"BankResetTimeTab0":Guild_member#bankresettimetab|int(11) unsigned|NO||0||
|"BankRemSlotsTab0":Guild_member#bankremslotstab|int(11) unsigned|NO||0||
|"BankResetTimeTab1":Guild_member#bankresettimetab|int(11) unsigned|NO||0||
|"BankRemSlotsTab1":Guild_member#bankremslotstab|int(11) unsigned|NO||0||
|"BankResetTimeTab2":Guild_member#bankresettimetab|int(11) unsigned|NO||0||
|"BankRemSlotsTab2":Guild_member#bankremslotstab|int(11) unsigned|NO||0||
|"BankResetTimeTab3":Guild_member#bankresettimetab|int(11) unsigned|NO||0||
|"BankRemSlotsTab3":Guild_member#bankremslotstab|int(11) unsigned|NO||0||
|"BankResetTimeTab4":Guild_member#bankresettimetab|int(11) unsigned|NO||0||
|"BankRemSlotsTab4":Guild_member#bankremslotstab|int(11) unsigned|NO||0||
|"BankResetTimeTab5":Guild_member#bankresettimetab|int(11) unsigned|NO||0||
|"BankRemSlotsTab5":Guild_member#bankremslotstab|int(11) unsigned|NO||0||


h3. Description of the fields

h4. guildid

The ID of the guild that the member is a part of. See "guild.guildid":guild#guildid

h4. guid

The GUID of the player. See "character.guid":character#guid

h4. rank

The rank that the player has in the guild. See "guild&#95;rank.rid":guild_rank#rid

h4. pnote

The note set by the player that can be read by everyone.

h4. offnote

The note set by officers in the guild that can only be read by other officers of the guild.

h4. BankResetTimeMoney

h4. BankRemMoney

h4. BankResetTimeTab

h4. BankRemSlotsTab
