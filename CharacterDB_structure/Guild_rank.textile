Back to the "characters database":charactersdb_struct list of tables.

h2. The `guild&#95;rank` table

This table holds the information on all of the ranks available in a guild along with their names and what rights a person with that rank has.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guildid":Guild_rank#guildid|int(6) unsigned|NO|PRI|0||
|"rid":Guild_rank#rid|int(11) unsigned|NO|PRI|||
|"rname":Guild_rank#rname|varchar(255)|NO||||
|"rights":Guild_rank#rights|int(3) unsigned|NO||0||
|"BankMoneyPerDay":Guild_rank#bankmoneyperday|int(11) unsigned|NO||0||


h3. Description of the fields

h4. guildid

The guild ID that the rank is part of. See "guild.guildid":guild#guildid

h4. rid

The particular rank ID. This number must be unique to each rank in a guild.

h4. rname

The name of the rank that is displayed in-game.

h4. rights

The rights a player with this rank has in the guild. The calculation of multiple rights is a bit different in this case as the rights do not all have 2^n values. To combine ranks, you must do the OR operation (&#124;) on the two flags.

|_. Flag|_. Name|_. Comments|
|64|GR&#95;RIGHT&#95;EMPTY|Having just this flag by itself is equivalent to having no rights at all.|
|65|GR&#95;RIGHT&#95;GCHATLISTEN|Player can read messages in the guild general chat channel.|
|66|GR&#95;RIGHT&#95;GCHATSPEAK|Player can type messages in the guild general chat channel.|
|68|GR&#95;RIGHT&#95;OFFCHATLISTEN|Player can read messages in the guild officers channel.|
|72|GR&#95;RIGHT&#95;OFFCHATSPEAK|Player can type messages in the guild officers channel.|
|80|GR&#95;RIGHT&#95;INVITE|Can invite other players to guild.|
|96|GR&#95;RIGHT&#95;REMOVE|Can kick other players out of guild.|
|192|GR&#95;RIGHT&#95;PROMOTE|Can promote other players.|
|320|GR&#95;RIGHT&#95;DEMOTE|Can demote other players.|
|4160|GR&#95;RIGHT&#95;SETMOTD|Can change the guild message of the day.|
|8256|GR&#95;RIGHT&#95;EPNOTE|Can edit other players' personal notes.|
|16448|GR&#95;RIGHT&#95;VIEWOFFNOTE|Can view the officer notes of other players.|
|32832|GR&#95;RIGHT&#95;EOFFNOTE|Can edit officer notes of other players.|
|61951|GR&#95;RIGHT&#95;ALL|Has all of the rights.|


h4. BankMoneyPerDay

The total money per day, in copper, that a person with this rank can take out. Use the maximum value of an unsigned int (4294967295) to specify unlimited amount.
