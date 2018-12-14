Back to "characters database":charactersdb_struct list of tables.

h2. The `guild&#95;bank&#95;eventlog` table

To-do

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guildid":Guild_bank_eventlog#guildid|int(11) unsigned|NO|PRI|0||
|"LogGuid":Guild_bank_eventlog#logguid|int(11) unsigned|NO|PRI|0||
|"LogEntry":Guild_bank_eventlog#logentry|tinyint(1) unsigned|NO||0||
|"TabId":Guild_bank_eventlog#tabid|tinyint(1) unsigned|NO||0||
|"PlayerGuid":Guild_bank_eventlog#playerguid|int(11) unsigned|NO||0||
|"ItemOrMoney":Guild_bank_eventlog#itemormoney|int(11) unsigned|NO||0||
|"ItemStackCount":Guild_bank_eventlog#itemstackcount|tinyint(3) unsigned|NO||0||
|"DestTabId":Guild_bank_eventlog#desttabid|tinyint(1) unsigned|NO||0||
|"TimeStamp":Guild_bank_eventlog#timestamp|bigint(20) unsigned|NO||0||


h3. Description of the fields

h4. guildid

h4. LogGuid

h4. LogEntry

h4. TabId

h4. PlayerGuid

h4. ItemOrMoney

h4. ItemStackCount

h4. DestTabId

h4. TimeStamp
