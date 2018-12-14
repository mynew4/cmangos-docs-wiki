Back to [world database](mangosdb_struct) list of tables.

The \`locales\_creature\` table
-------------------------------

This table is used to provide to localized clients with localized string for creatures.

### Structure

| **Field**                                      | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Locales_creature#entry)                | int(11) unsigned | NO       | PRI     | 0           |           |
| [name\_loc1](Locales_creature#name_locx)       | varchar(100)     | NO       |         |             |           |
| [name\_loc2](Locales_creature#name_locx)       | varchar(100)     | NO       |         |             |           |
| [name\_loc3](Locales_creature#name_locx)       | varchar(100)     | NO       |         |             |           |
| [name\_loc4](Locales_creature#name_locx)       | varchar(100)     | NO       |         |             |           |
| [name\_loc5](Locales_creature#name_locx)       | varchar(100)     | NO       |         |             |           |
| [name\_loc6](Locales_creature#name_locx)       | varchar(100)     | NO       |         |             |           |
| [name\_loc7](Locales_creature#name_locx)       | varchar(100)     | NO       |         |             |           |
| [subname\_loc1](Locales_creature#subname_locx) | varchar(100)     | YES      |         | None        |           |
| [subname\_loc2](Locales_creature#subname_locx) | varchar(100)     | YES      |         | None        |           |
| [subname\_loc3](Locales_creature#subname_locx) | varchar(100)     | YES      |         | None        |           |
| [subname\_loc4](Locales_creature#subname_locx) | varchar(100)     | YES      |         | None        |           |
| [subname\_loc5](Locales_creature#subname_locx) | varchar(100)     | YES      |         | None        |           |
| [subname\_loc6](Locales_creature#subname_locx) | varchar(100)     | YES      |         | None        |           |
| [subname\_loc7](Locales_creature#subname_locx) | varchar(100)     | YES      |         | None        |           |

### Description of the fields

#### entry

This entry must be the same as [creature\_template.entry](creature_template#entry) and then the row will be used to provide localization support for this creature record.

#### name\_locX

Translated content for [creature\_template.name](creature_template#name) field for language X. See [localization languages](localization_lang) list to know which value to use for X.

#### subname\_locX

Translated content for [creature\_template.subname](creature_template#subname) field for language X. See [localization languages](localization_lang) list to know which value to use for X.
