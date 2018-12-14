h3. *The `guild&#95;eventlog` table*

This table holds information about changes in guilds membership.

h3. *Structure*


|<strong>*Field*</strong>|<strong>*Type*</strong>|<strong>*Null*</strong>|<strong>*Key*</strong>|<strong>*Default*</strong>|<strong>*Extra*</strong>|
|"guildid":Guild_eventlog#guildid|int(11) unsigned|NO|PRI|0||
|"LogGuid":Guild_eventlog#logguid|int(11) unsigned|NO|PRI|0||
|"EventType":Guild_eventlog#eventtype|tinyint(1) unsigned|NO||0||
|"PlayerGuid1":Guild_eventlog#playerguid|int(11) unsigned|NO||0||
|"PlayerGuid2":Guild_eventlog#playerguid|int(11) unsigned|NO||0||
|"NewRank":Guild_eventlog#newrank|tinyint(2) unsigned|NO||0||
|"TimeStamp":Guild_eventlog#timestamp|bigint(20) unsigned|NO||0||


h3. *Description of the fields*

h4. guildid

Id of related guild. See "guild.guildid":guild#guildid

h4. LogGuid

A unique identifier given to each log entry to distinguish one entry from another. Two guild event logs can NOT have same GUID.

h4. EventType

bc. GUILD_EVENT_LOG_INVITE_PLAYER     = 1
GUILD_EVENT_LOG_JOIN_GUILD        = 2
GUILD_EVENT_LOG_PROMOTE_PLAYER    = 3
GUILD_EVENT_LOG_DEMOTE_PLAYER     = 4
GUILD_EVENT_LOG_UNINVITE_PLAYER   = 5
GUILD_EVENT_LOG_LEAVE_GUILD       = 6


h4. PlayerGuid1

Guid of character who made the change. See "character.guid":character#guid

h4. PlayerGuid2

Guid of character who was &quot;changed&quot;. See "character.guid":character#guid

h4. NewRank

Id of new rank of PlayerGuid2. See "guild&#95;rank.rid":guild_rank#rid

h4. TimeStamp

Unix timestamp when event happens.
