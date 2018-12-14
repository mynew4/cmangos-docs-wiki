Back to "realm database":realmdb_struct list of tables.

h2. The `realmcharacters` table

This table holds information on the number of characters each account has for each realm.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"realmid":Realmcharacters#realmid|int(11) unsigned|NO|PRI|0||
|"acctid":Realmcharacters#acctid|bigint(20) unsigned|NO|PRI|||
|"numchars":Realmcharacters#numchars|tinyint(3) unsigned|NO||0||


h3. Description of the fields

h4. realmid

The ID of the realm. See "realmlist.id":realmlist#id

h4. acctid

The account ID. See "account.id":account#id

h4. numchars

The number of characters the account has on the realm.

"Category: Realm database tables":Category: Realm database tables
