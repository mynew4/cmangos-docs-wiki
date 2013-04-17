Back to "world database":mangosdb_struct list of tables.

h2. The `achievement&#95;reward` table

This table contains the rewards for achievements added with Wrath of the Lichking.

h3. Structure


|Field|Type|Attributes|Can be null|Default|Comments|
|"entry":Achievement_reward#entry|mediumint(8)|unsigned|NO|0|Identifier|
|"gender":Achievement_reward#gender|TINYINT(3)|unsigned|YES|2||
|"title_A":Achievement_reward#title|mediumint(8)|unsigned|NO|0||
|"title_H":Achievement_reward#title|mediumint(8)|unsigned|NO|0||
|"item":Achievement_reward#item|mediumint(8)|unsigned|NO|0||
|"sender":Achievement_reward#sender|mediumint(8)|unsigned|NO|0||
|"subject":Achievement_reward#subject|varchar(255)||YES|NULL||
|"text":Achievement_reward#text|text||YES|NULL||


h3. Description of the fields

h4. entry

This is the achievement identifier from "Achievements.dbc":Achievements.dbc

h4. gender

Indicates characters of which gender may gain that reward. MALE = 0 FEMALE = 1 BOTH = 2

h4. title

This is the reference to "CharTitles.dbc.":CharTitles.dbc. Player has the right to wear the title as name affix.

h4. item

The item you get by mail for the achievement. Reference to "item&#95;template":item_template#entry.

h4. sender

You recieve mail from this sender. Reference to "creature&#95;template":creature_template#entry

h4. subject

The mail subject. Just plain text up to 255 chars.

h4. text

The mail text.
