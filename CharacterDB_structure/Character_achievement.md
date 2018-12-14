Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;achievement` table

This table holds information for each character and its achievement.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_achievement#guid|int(11) unsigned|NO|PRIMARY|||
|"achievement":Character_achievement#achievement|int(11)|NO|PRIMARY|||
|"date":Character_achievement#date|int(11)|NO||||


h4. guid

The GUID of the character. See "character.guid":character#guid

h4. achievement

The ID of the achievement. See "achievements.dbc":achievements.dbc

h4. date

Unix timestamp when achievement was completed.
