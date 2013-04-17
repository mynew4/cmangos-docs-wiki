Back to "dbc files":dbc_files list.

h3. Item.dbc

This DBC contains all item entries for real usable items and texture only ones used for creatures equipment. Any item in "item_template":item_template table with an entry not in this DBC will be displayed by client with a red ? symbol.

Corresponding "item_template":item_template records must match these values except Subclass (which contains erroneous values).

*Version is : 3.1.3*

h3. Structure


|*Field Nb*|*Name*|*Type*|
|1|ID|Int|
|2|Class|Int|
|3|SubClass|Int|
|4|Unk0|Int|
|5|Material|Int|
|6|DisplayId|Int|
|7|InventoryType|Int|
|8|Sheath|Int|


h3. Content

The content is too big and useless for the purpose of this wiki.

h3. MaNGOS usage

bc. struct ItemEntry
{
   uint32   ID;                        // 0
   uint32   Class;                     // 1
   uint32   SubClass;                  // 2 some items have strange subclasses
   int32    Unk0;                      // 3
   int32    Material;                  // 4
   uint32   DisplayId;                 // 5
   uint32   InventoryType;             // 6
   uint32   Sheath;                    // 7
};

