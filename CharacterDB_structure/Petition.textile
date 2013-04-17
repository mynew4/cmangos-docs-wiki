Back to the "characters database":charactersdb_struct list of tables.

h2. The `petition` table

This table holds information on all ongoing petitions for a guild or for an arena team.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"ownerguid":Petition#ownerguid|int(10) unsigned|NO|PRI|||
|"petitionguid":Petition#petitionguid|int(10) unsigned|YES||0||
|"name":Petition#name|varchar(255)|NO||||
|"type":Petition#type|int(10) unsigned|NO||0||


h3. Description of the fields

h4. ownerguid

The petition's owner's GUID. See "character.guid":character#guid

h4. petitionguid

The GUID of the petition item. See "item&#95;instance.guid":item_instance#guid

h4. name

The name of the guild or arena team that the player is trying to ask for petitions for.

h4. type

The type of the petition.

|_. ID|_. Type|
|2|2vs2 Arena charter|
|3|3vs3 Arena charter|
|5|5vs5 Arena charter|
|9|Guild charter|

