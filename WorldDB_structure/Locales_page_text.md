Back to "world database":mangosdb_struct list of tables.

h2. The `locales&#95;page&#95;text` table

This table is used to provide localized clients with localized string for page&#95;texts.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Locales_page_text#entry|int(11) unsigned|NO|PRI|0||
|"Text_loc1":Locales_page_text#text_locx|longtext|YES||None||
|"Text_loc2":Locales_page_text#text_locx|longtext|YES||None||
|"Text_loc3":Locales_page_text#text_locx|longtext|YES||None||
|"Text_loc4":Locales_page_text#text_locx|longtext|YES||None||
|"Text_loc5":Locales_page_text#text_locx|longtext|YES||None||
|"Text_loc6":Locales_page_text#text_locx|longtext|YES||None||
|"Text_loc7":Locales_page_text#text_locx|longtext|YES||None||


h3. Description of the fields

h4. entry

This entry must be the same as "page&#95;text.entry":page_text#entry and then the row will be used to provide localization support for this page&#95;text record.

h4. Text&#95;locX

Translated content for "page&#95;text.text":page_text#text field for language X. See "localization languages":localization_lang list to know which value to use for X.
