Back to the "characters database":charactersdb_struct list of tables.

h2. The `petition&#95;sign` table

This table holds information on all the signatures of a petition for either a guild or an arena team.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"ownerguid":Petition_sign#ownerguid|int(10) unsigned|NO||||
|"petitionguid":Petition_sign#petitionguid|int(11) unsigned|NO|PRI|0||
|"playerguid":Petition_sign#playerguid|int(11) unsigned|NO|PRI|0||
|"player_account":Petition_sign#player_account|int(11) unsigned|NO||0||
|"type":Petition_sign#type|int(10) unsigned|NO||0||


h3. Description of the fields

h4. ownerguid

The GUID of the owner that is trying to make the guild/arena team. See "character.guid":character#guid

h4. petitionguid

The GUID of the charter item. See "item&#95;template.guid":item_template#guid

h4. playerguid

The GUID of the player that has signed the charter. See "character.guid":character#guid

h4. player&#95;account

The account ID of the player that has signed the charter. No two players can sign the same charter from the same account.

h4. type

The type of the petition.

|_. ID|_. Type|
|2|2vs2 Arena charter|
|3|3vs3 Arena charter|
|5|5vs5 Arena charter|
|9|Guild charter|

