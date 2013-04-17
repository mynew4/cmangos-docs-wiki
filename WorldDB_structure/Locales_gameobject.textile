Back to "world database":mangosdb_struct list of tables.

h2. The `locales&#95;gameobject` table

This table is used to provide to localized clients with localized string for gameobjects.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Locales_gameobject#entry|int(11) unsigned|NO|PRI|0||
|"name_loc1":Locales_gameobject#name_locx|varchar(100)|NO||||
|"name_loc2":Locales_gameobject#name_locx|varchar(100)|NO||||
|"name_loc3":Locales_gameobject#name_locx|varchar(100)|NO||||
|"name_loc4":Locales_gameobject#name_locx|varchar(100)|NO||||
|"name_loc5":Locales_gameobject#name_locx|varchar(100)|NO||||
|"name_loc6":Locales_gameobject#name_locx|varchar(100)|NO||||
|"name_loc7":Locales_gameobject#name_locx|varchar(100)|NO||||
|"castbarcaption_loc1":Locales_gameobject#castbarcaption_locx|varchar(100)|NO||||
|"castbarcaption_loc2":Locales_gameobject#castbarcaption_locx|varchar(100)|NO||||
|"castbarcaption_loc3":Locales_gameobject#castbarcaption_locx|varchar(100)|NO||||
|"castbarcaption_loc4":Locales_gameobject#castbarcaption_locx|varchar(100)|NO||||
|"castbarcaption_loc5":Locales_gameobject#castbarcaption_locx|varchar(100)|NO||||
|"castbarcaption_loc6":Locales_gameobject#castbarcaption_locx|varchar(100)|NO||||
|"castbarcaption_loc7":Locales_gameobject#castbarcaption_locx|varchar(100)|NO||||


h3. Description of the fields

h4. entry

This entry must be the same as "gameobject&#95;template.entry":gameobject_template#entry and then the row will be used to provide localization support for this gameobject record.

h4. name&#95;locX

Translated content for "gameobject&#95;template.name":gameobject_template#name field for language X. See "localization languages":localization_lang list to know which value to use for X.

h4. castbarcaption&#95;locX

Translated content for "gameobject&#95;template.castBarCaption":gameobject_template#castBarCaption field for language X. See "localization languages":localization_lang list to know which value to use for X.
