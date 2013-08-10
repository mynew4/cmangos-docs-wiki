Back to "characters database":charactersdb_struct list of tables.

h2. The `item&#95;instance` table

This table holds individual item instance information for all items currently equipped or in some kind of character bag or bank.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Item_instance#guid|int(11) unsigned|NO|PRI|0||
|"owner_guid":Item_instance#owner_guid|int(11) unsigned|NO|MUL|0||
|"data":Item_instance#data|longtext|YES||||


h3. Description of the fields

h4. guid

The GUID of the item. This number is unique for each item instance.

h4. owner&#95;guid

The GUID of the character who has ownership of this item. See "character.guid":character#guid

h4. data

Much like the data field in the character table, this field has many number fields all separated by a space which contain specific individual item information like any enchantments applied to the item, etc.

|_. Index|_. Value Name|_. Comments|
|0|OBJECT&#95;FIELD&#95;GUID|Item GUID|
|2|OBJECT&#95;FIELD&#95;TYPE|Should be 3 (TYPE&#95;OBJECT + TYPE&#95;ITEM)|
|3|OBJECT&#95;FIELD&#95;ENTRY|entry|
|4|OBJECT&#95;FIELD&#95;SCALE&#95;X|1.0|
|5|OBJECT&#95;FIELD&#95;PADDING||
|6|ITEM&#95;FIELD&#95;OWNER|owner&#95;guid|
|8|ITEM&#95;FIELD&#95;CONTAINED|If the item is in a bag, the GUID of the bag item; otherwise owner GUID.|
|10|ITEM&#95;FIELD&#95;CREATOR|GUID of character who created the item.|
|12|ITEM&#95;FIELD&#95;GIFTCREATOR|GUID of character who created the "item":character_gifts#item_guid.|
|14|ITEM&#95;FIELD&#95;STACK&#95;COUNT|Current number of item copies in the stack.|
|15|ITEM&#95;FIELD&#95;DURATION|Current duration (in milliseconds)|
|16|ITEM&#95;FIELD&#95;SPELL&#95;CHARGES||
|21|ITEM&#95;FIELD&#95;FLAGS|Flags (from "item&#95;template":Item_template#flags)|
|22|ITEM&#95;FIELD&#95;ENCHANTMENT||
|55|ITEM&#95;FIELD&#95;PROPERTY&#95;SEED|Also called ITEM&#95;FIELD&#95;SUFFIX&#95;FACTOR|
|56|ITEM&#95;FIELD&#95;RANDOM&#95;PROPERTIES&#95;ID||
|57|ITEM&#95;FIELD&#95;ITEM&#95;TEXT&#95;ID|Text id used and shown by the item.|
|58|ITEM&#95;FIELD&#95;DURABILITY|Current item durability.|
|59|ITEM&#95;FIELD&#95;MAXDURABILITY|Maximum item durability.|

