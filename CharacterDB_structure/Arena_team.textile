Back to "characters database":charactersdb_struct list of tables.

h2. The `arena&#95;team` table


h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|
|"arenateamid":Arena_team#arenateamid|int(10) unsigned|NO|PRI|0|
|"name":Arena_team#name|char(255)|NO|||
|"captainguid":Arena_team#captainguid|int(10) unsigned|NO||0|
|"type":Arena_team#type|tinyint(3) unsigned|NO||0|
|"EmblemStyle":Arena_team#emblemstyle|int(10) unsigned|NO||0|
|"EmblemColor":Arena_team#emblemcolor|int(10) unsigned|NO||0|
|"BorderStyle":Arena_team#borderstyle|int(10) unsigned|NO||0|
|"BorderColor":Arena_team#bordercolor|int(10) unsigned|NO||0|
|"BackgroundColor":Arena_team#backgroundcolor|int(10) unsigned|NO||0|


h3. Description of the fields

h4. arenateamid


h4. name

The name of the team

h4. captainguid

The character global unique identifier of leader. View Characters.guid

h4. type

0 = 2v2 1 = 3v3 2 = 5v5

h4. EmblemStyle


h4. EmblemColor


h4. BorderStyle


h4. BorderColor


h4. BackgroundColor

