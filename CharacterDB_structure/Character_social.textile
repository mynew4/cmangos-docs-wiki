Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;social` table

Contains data about characters' friends/ignored list.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_social#guid|int(11) unsigned|NO|PRI|0||
|"name":Character_social#name|varchar(21)|NO||||
|"friend":Character_social#friend|int(11) unsigned|NO|PRI|0||
|"flags":Character_social#flags|varchar(21)|NO|PRI|||


h3. Description of the fields

h4. guid

The GUID of the character. See "character.guid":character#guid

h4. name

The name of the friend/ignored. See "character.name":character#name

h4. friend

The GUID of the friend/ignored. See "character.guid":character#guid

h4. flags

0 = Friend
1 = Ignored
