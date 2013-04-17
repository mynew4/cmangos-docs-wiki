Back to "realm database":realmdb_struct list of tables.

h2. The `account&#95;banned` table

This table lists all of the accounts that have been banned along with the date when (or if) the ban will expire.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Account_banned#id|int(11)|NO|PRI|0||
|"bandate":Account_banned#bandate|bigint(40)|NO|PRI|0||
|"unbandate":Account_banned#unbandate|bigint(40)|NO||0||
|"bannedby":Account_banned#bannedby|varchar(50)|NO||||
|"banreason":Account_banned#banreason|varchar(255)|NO||||
|"active":Account_banned#active|tinyint(4)|NO||1||


h3. Description of the fields

h4. id

The account ID. See "account.id":account#id

h4. bandate

The date when the account was banned, in Unix time.

h4. unbandate

The date when the account will be automatically unbanned, in Unix time. A value less than the current date means, in effect, a permanent ban.

h4. bannedby

The character with the rights to the .ban command that banned the account.

h4. banreason

The reason for the ban.

h4. active

Boolean 0 or 1 controlling if the ban is currently active or not.

"Category: Realm database tables":Category: Realm database tables
