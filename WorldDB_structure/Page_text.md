Back to "world database":mangosdb_struct list of tables.

h2. The `page&#95;text` table

This table holds the text for letter items or any items that when moused-over turn the cursor into a magnifying glass and on right-click will open up a window where you can read the contents of the letter.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Page_text#entry|int(11)|NO|PRI|0||
|"text":Page_text#text|longtext|YES||None||
|"next_page":Page_text#next_page|int(11) unsigned|NO||0||


h3. Description of the fields

h4. entry

The ID of the text in the page. This number is unique to every text entry.

h4. text

The actual text. The message in this field will be shown as the text on a page.

h4. next&#95;page

The ID of the next page's text "entry":#entry.
