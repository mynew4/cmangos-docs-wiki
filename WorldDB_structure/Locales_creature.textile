Back to "world database":mangosdb_struct list of tables.

h2. The `locales&#95;creature` table

This table is used to provide to localized clients with localized string for creatures.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Locales_creature#entry|int(11) unsigned|NO|PRI|0||
|"name_loc1":Locales_creature#name_locx|varchar(100)|NO||||
|"name_loc2":Locales_creature#name_locx|varchar(100)|NO||||
|"name_loc3":Locales_creature#name_locx|varchar(100)|NO||||
|"name_loc4":Locales_creature#name_locx|varchar(100)|NO||||
|"name_loc5":Locales_creature#name_locx|varchar(100)|NO||||
|"name_loc6":Locales_creature#name_locx|varchar(100)|NO||||
|"name_loc7":Locales_creature#name_locx|varchar(100)|NO||||
|"subname_loc1":Locales_creature#subname_locx|varchar(100)|YES||None||
|"subname_loc2":Locales_creature#subname_locx|varchar(100)|YES||None||
|"subname_loc3":Locales_creature#subname_locx|varchar(100)|YES||None||
|"subname_loc4":Locales_creature#subname_locx|varchar(100)|YES||None||
|"subname_loc5":Locales_creature#subname_locx|varchar(100)|YES||None||
|"subname_loc6":Locales_creature#subname_locx|varchar(100)|YES||None||
|"subname_loc7":Locales_creature#subname_locx|varchar(100)|YES||None||


h3. Description of the fields

h4. entry

This entry must be the same as "creature&#95;template.entry":creature_template#entry and then the row will be used to provide localization support for this creature record.

h4. name&#95;locX

Translated content for "creature&#95;template.name":creature_template#name field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. subname&#95;locX

Translated content for "creature&#95;template.subname":creature_template#subname field for language X. See "localization languages":localization_lang list to know which value to use for X.
