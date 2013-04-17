Back to the "characters database":charactersdb_struct list of tables.

h2. The `item&#95;text` table

This table is part of the mail system and holds the text information of every letter.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Item_text#id|int(11)|NO|PRI|0||
|"text":Item_text#text|longtext|YES||None||


h3. Description of the fields

h4. id

The text entry ID. This number is unique to every text entry in this table.

h4. text

The actual text that was sent as mail using the mail system. There are some special messages that are sent through the mail and therefore use this table but have a special format to them:

* Auction won (sent to bidder): &quot;<owner's GUID as hex>:<winning bid in copper>:<buyout price in copper>&quot;
* Auction successful (sent to owner): &quot;<bidder's GUID as hex>:<winning bid in copper>:0:<deposit in copper>:<auction cut in copper>&quot;
