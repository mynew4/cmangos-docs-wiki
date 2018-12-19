Back to [world database](mangosdb_struct) list of tables.

The \`locales\_gameobject\` table
---------------------------------

This table is used to provide to localized clients with localized string for gameobjects.

### Structure

| **Field**                                                      | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Locales_gameobject#entry)                              | int(11) unsigned | NO       | PRI     | 0           |           |
| [name\_loc1](Locales_gameobject#name_locx)                     | varchar(100)     | NO       |         |             |           |
| [name\_loc2](Locales_gameobject#name_locx)                     | varchar(100)     | NO       |         |             |           |
| [name\_loc3](Locales_gameobject#name_locx)                     | varchar(100)     | NO       |         |             |           |
| [name\_loc4](Locales_gameobject#name_locx)                     | varchar(100)     | NO       |         |             |           |
| [name\_loc5](Locales_gameobject#name_locx)                     | varchar(100)     | NO       |         |             |           |
| [name\_loc6](Locales_gameobject#name_locx)                     | varchar(100)     | NO       |         |             |           |
| [name\_loc7](Locales_gameobject#name_locx)                     | varchar(100)     | NO       |         |             |           |
| [castbarcaption\_loc1](Locales_gameobject#castbarcaption_locx) | varchar(100)     | NO       |         |             |           |
| [castbarcaption\_loc2](Locales_gameobject#castbarcaption_locx) | varchar(100)     | NO       |         |             |           |
| [castbarcaption\_loc3](Locales_gameobject#castbarcaption_locx) | varchar(100)     | NO       |         |             |           |
| [castbarcaption\_loc4](Locales_gameobject#castbarcaption_locx) | varchar(100)     | NO       |         |             |           |
| [castbarcaption\_loc5](Locales_gameobject#castbarcaption_locx) | varchar(100)     | NO       |         |             |           |
| [castbarcaption\_loc6](Locales_gameobject#castbarcaption_locx) | varchar(100)     | NO       |         |             |           |
| [castbarcaption\_loc7](Locales_gameobject#castbarcaption_locx) | varchar(100)     | NO       |         |             |           |

### Description of the fields

#### entry

This entry must be the same as [gameobject\_template.entry](gameobject_template#entry) and then the row will be used to provide localization support for this gameobject record.

#### name\_locX

Translated content for [gameobject\_template.name](gameobject_template#name) field for language X. See [localization languages](localization_lang) list to know which value to use for X.

#### castbarcaption\_locX

Translated content for [gameobject\_template.castBarCaption](gameobject_template#castBarCaption) field for language X. See [localization languages](localization_lang) list to know which value to use for X.
