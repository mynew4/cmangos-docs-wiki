Back to [world database](mangosdb_struct) list of tables.

The \`locales\_page\_text\` table
---------------------------------

This table is used to provide localized clients with localized string for page\_texts.

### Structure

| **Field**                                 | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Locales_page_text#entry)          | int(11) unsigned | NO       | PRI     | 0           |           |
| [Text\_loc1](Locales_page_text#text_locx) | longtext         | YES      |         | None        |           |
| [Text\_loc2](Locales_page_text#text_locx) | longtext         | YES      |         | None        |           |
| [Text\_loc3](Locales_page_text#text_locx) | longtext         | YES      |         | None        |           |
| [Text\_loc4](Locales_page_text#text_locx) | longtext         | YES      |         | None        |           |
| [Text\_loc5](Locales_page_text#text_locx) | longtext         | YES      |         | None        |           |
| [Text\_loc6](Locales_page_text#text_locx) | longtext         | YES      |         | None        |           |
| [Text\_loc7](Locales_page_text#text_locx) | longtext         | YES      |         | None        |           |

### Description of the fields

#### entry

This entry must be the same as [page\_text.entry](page_text#entry) and then the row will be used to provide localization support for this page\_text record.

#### Text\_locX

Translated content for [page\_text.text](page_text#text) field for language X. See [localization languages](localization_lang) list to know which value to use for X.
