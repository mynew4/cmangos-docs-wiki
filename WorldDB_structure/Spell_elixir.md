Back to "world database":mangosdb_struct list of tables.

h2. The `spell&#95;elixir` table

This table holds elixir information to be used to properly stack the elixirs.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Spell_elixir#entry|int(11) unsigned|NO|PRI|0||
|"mask":Spell_elixir#mask|tinyint(1) unsigned|NO||0||


h3. Description of the fields

h4. entry

The spell ID used by the elixir.

h4. mask

The type of elixir the spell is classified as.

|_. Value|_. Type|
|1|Battle|
|2|Guardian|
|3|Flask|
|7|Unstable flask|
|11|Shattrath flask|

