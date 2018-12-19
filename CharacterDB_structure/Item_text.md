Back to the [characters database](charactersdb_struct) list of tables.

The \`item\_text\` table
------------------------

This table is part of the mail system and holds the text information of every letter.

### Structure

| **Field**              | **Type** | **Null** | **Key** | **Default** | **Extra** |
|------------------------|----------|----------|---------|-------------|-----------|
| [id](Item_text#id)     | int(11)  | NO       | PRI     | 0           |           |
| [text](Item_text#text) | longtext | YES      |         | None        |           |

### Description of the fields

#### id

The text entry ID. This number is unique to every text entry in this table.

#### text

The actual text that was sent as mail using the mail system. There are some special messages that are sent through the mail and therefore use this table but have a special format to them:

-   Auction won (sent to bidder): "<owner's GUID as hex>:<winning bid in copper>:<buyout price in copper>"
-   Auction successful (sent to owner): "<bidder's GUID as hex>:<winning bid in copper>:0:<deposit in copper>:<auction cut in copper>"

