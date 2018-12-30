Back to [world database](mangosdb_struct) list of tables.

The \`locales\_item\` table
---------------------------

This table is used to provide to localized clients with localized string for items.

### Structure

| **Field**                                          | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Locales_item#entry)                        | int(11) unsigned | NO       | PRI     | 0           |           |
| [name\_loc1](Locales_item#name_locx)               | varchar(100)     | NO       |         |             |           |
| [name\_loc2](Locales_item#name_locx)               | varchar(100)     | NO       |         |             |           |
| [name\_loc3](Locales_item#name_locx)               | varchar(100)     | NO       |         |             |           |
| [name\_loc4](Locales_item#name_locx)               | varchar(100)     | NO       |         |             |           |
| [name\_loc5](Locales_item#name_locx)               | varchar(100)     | NO       |         |             |           |
| [name\_loc6](Locales_item#name_locx)               | varchar(100)     | NO       |         |             |           |
| [name\_loc7](Locales_item#name_locx)               | varchar(100)     | NO       |         |             |           |
| [description\_loc1](Locales_item#description_locx) | varchar(255)     | YES      |         | None        |           |
| [description\_loc2](Locales_item#description_locx) | varchar(255)     | YES      |         | None        |           |
| [description\_loc3](Locales_item#description_locx) | varchar(255)     | YES      |         | None        |           |
| [description\_loc4](Locales_item#description_locx) | varchar(255)     | YES      |         | None        |           |
| [description\_loc5](Locales_item#description_locx) | varchar(255)     | YES      |         | None        |           |
| [description\_loc6](Locales_item#description_locx) | varchar(255)     | YES      |         | None        |           |
| [description\_loc7](Locales_item#description_locx) | varchar(255)     | YES      |         | None        |           |

### Description of the fields

#### entry

This entry must be the same as [item\_template.entry](item_template#entry) and then the row will be used to provide localization support for this creature record.

#### name\_locX

Translated content for [item\_template.name](item_template#name) field for language X. See [localization languages](localization_lang) list to know which value to use for X.

#### description\_locX

Translated content for [item\_template.description](item_template#description) field for language X. See [localization languages](localization_lang) list to know which value to use for X.
