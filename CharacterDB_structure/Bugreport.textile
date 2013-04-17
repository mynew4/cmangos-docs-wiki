Back to the "characters database":charactersdb_struct list of tables.

h2. The `bugreport` table

This table stores all the Bug/Suggestion submitted ingame by Players.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Bugreport#id|int(11)|NO|PRI|None|auto&#95;increment|
|"type":Bugreport#type|varchar(255)|NO||||
|"content":Bugreport#content|varchar(255)|NO||||


h3. Description of the fields

h4. id

Auto generated value when records are inserted by MaNGOS. This id is just here to be a primary key and eases the data insertion.

h4. type

The text description of the type of bug/suggestion.

h4. content

The text content of the bug/suggestion.
