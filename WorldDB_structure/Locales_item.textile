Back to "world database":mangosdb_struct list of tables.

h2. The `locales&#95;item` table

This table is used to provide to localized clients with localized string for items.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Locales_item#entry|int(11) unsigned|NO|PRI|0||
|"name_loc1":Locales_item#name_locx|varchar(100)|NO||||
|"name_loc2":Locales_item#name_locx|varchar(100)|NO||||
|"name_loc3":Locales_item#name_locx|varchar(100)|NO||||
|"name_loc4":Locales_item#name_locx|varchar(100)|NO||||
|"name_loc5":Locales_item#name_locx|varchar(100)|NO||||
|"name_loc6":Locales_item#name_locx|varchar(100)|NO||||
|"name_loc7":Locales_item#name_locx|varchar(100)|NO||||
|"description_loc1":Locales_item#description_locx|varchar(255)|YES||None||
|"description_loc2":Locales_item#description_locx|varchar(255)|YES||None||
|"description_loc3":Locales_item#description_locx|varchar(255)|YES||None||
|"description_loc4":Locales_item#description_locx|varchar(255)|YES||None||
|"description_loc5":Locales_item#description_locx|varchar(255)|YES||None||
|"description_loc6":Locales_item#description_locx|varchar(255)|YES||None||
|"description_loc7":Locales_item#description_locx|varchar(255)|YES||None||


h3. Description of the fields

h4. entry

This entry must be the same as "item&#95;template.entry":item_template#entry and then the row will be used to provide localization support for this creature record.

h4. name&#95;locX

Translated content for "item&#95;template.name":item_template#name field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. description&#95;locX

Translated content for "item&#95;template.description":item_template#description field for language X. See "localization languages":localization_lang list to know which value to use for X.
