Back to "world database":mangosdb_struct list of tables.

h2. The `mangos&#95;string` table

This table holds all of the strings used internally by the server. This table is provided with the main purpose of translation in mind.

To see which locale IDs correspond to what languages, visit the "Localization_lang":Localization_lang page.

NOTE: The % arguments need to stay in the exact same order as they are provided by default in the English translation.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Mangos_string#entry|int(11) unsigned|NO|PRI|0||
|"content_default":Mangos_string#content_default|text|YES||||
|"content_loc1":Mangos_string#content_loc|text|YES||||
|"content_loc2":Mangos_string#content_loc|text|YES||||
|"content_loc3":Mangos_string#content_loc|text|YES||||
|"content_loc4":Mangos_string#content_loc|text|YES||||
|"content_loc5":Mangos_string#content_loc|text|YES||||
|"content_loc6":Mangos_string#content_loc|text|YES||||
|"content_loc7":Mangos_string#content_loc|text|YES||||


h3. Description of the fields

h4. entry

The ID that the core uses to identify a string. These IDs are contained and used internally and need to correspond to what the core expects. The core will not operate if all IDs aren't in this table.

h4. content&#95;default

The English translation (locale ID 0).

h4. content&#95;loc

The translation in another language depending on the locale ID of that language.
