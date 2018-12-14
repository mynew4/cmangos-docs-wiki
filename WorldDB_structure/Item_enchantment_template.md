Back to "world database":mangosdb_struct list of tables.

h2. The `item&#95;enchantment&#95;template` table

This table holds enchantment chance information for items that should have either a random property or a random suffix attached to them.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Item_enchantment_template#entry|int(10) unsigned|NO|PRI|0||
|"ench":Item_enchantment_template#ench|int(10) unsigned|NO|PRI|0||
|"chance":Item_enchantment_template#chance|float unsigned|NO||0||


h3. Description of the fields

h4. entry

This field ties in with EITHER "RandomProperty":item_template#RandomProperty OR "RandomSuffix":item_template#RandomSuffix fields in the item&#95;template table. An item cannot have both of those fields set at non-zero values.

NOTE: For 4.3.4 Core Use Negative Values To Specify a Random Suffix Entry and a Positive Value for a Random Properties Value

This is to prevent overlapping values since in 4.3.4 Official Data we do have about 12 overlapping Random Property and Random Suffix entries.

h4. ench

The enchantment to apply on the item. If the entry for the current row is used in "RandomProperty":item_template#RandomProperty, then this field points to the ID in ItemRandomProperties.dbc. If the entry is used in "RandomSuffix":item_template#RandomSuffix, then this field points to the ID in ItemRandomSuffix.dbc.

h4. chance

The chance for a random property or suffix to be applied to the item. For each entry in this table, the combined chances of all properties/suffixes need to equal 100 otherwise the item may not get a random enchantment on it.
