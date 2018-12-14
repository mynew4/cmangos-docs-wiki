Back to [world database](mangosdb_struct) list of tables.

The \`page\_text\` table
------------------------

This table holds the text for letter items or any items that when moused-over turn the cursor into a magnifying glass and on right-click will open up a window where you can read the contents of the letter.

### Structure

| **Field**                         | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Page_text#entry)          | int(11)          | NO       | PRI     | 0           |           |
| [text](Page_text#text)            | longtext         | YES      |         | None        |           |
| [next\_page](Page_text#next_page) | int(11) unsigned | NO       |         | 0           |           |

### Description of the fields

#### entry

The ID of the text in the page. This number is unique to every text entry.

#### text

The actual text. The message in this field will be shown as the text on a page.

#### next\_page

The ID of the next page's text [entry](#entry).
