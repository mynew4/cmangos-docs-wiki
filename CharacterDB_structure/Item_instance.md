Back to [characters database](charactersdb_struct) list of tables.

The \`item\_instance\` table
----------------------------

This table holds individual item instance information for all items currently equipped or in some kind of character bag or bank.

### Structure

| **Field**                               | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Item_instance#guid)              | int(11) unsigned | NO       | PRI     | 0           |           |
| [owner\_guid](Item_instance#owner_guid) | int(11) unsigned | NO       | MUL     | 0           |           |
| [data](Item_instance#data)              | longtext         | YES      |         |             |           |

### Description of the fields

#### guid

The GUID of the item. This number is unique for each item instance.

#### owner\_guid

The GUID of the character who has ownership of this item. See [character.guid](character#guid)

#### data

Much like the data field in the character table, this field has many number fields all separated by a space which contain specific individual item information like any enchantments applied to the item, etc.

| Index | Value Name                      | Comments                                                                        |
| ----- | ------------------------------- | ------------------------------------------------------------------------------- |
| 0     | OBJECT_FIELD_GUID               | Item GUID                                                                       |
| 2     | OBJECT_FIELD_TYPE               | Should be 3 (TYPE_OBJECT + TYPE_ITEM)                                           |
| 3     | OBJECT_FIELD_ENTRY              | entry                                                                           |
| 4     | OBJECT_FIELD_SCALE_X            | 1.0                                                                             |
| 5     | OBJECT_FIELD_PADDING            |                                                                                 |
| 6     | ITEM_FIELD_OWNER                | owner_guid                                                                      |
| 8     | ITEM_FIELD_CONTAINED            | If the item is in a bag, the GUID of the bag item; otherwise owner GUID.        |
| 10    | ITEM_FIELD_CREATOR              | GUID of character who created the item.                                         |
| 12    | ITEM_FIELD_GIFTCREATOR          | GUID of character who created the <a href="character_gifts#item_guid.">item</a> |
| 14    | ITEM_FIELD_STACK_COUNT          | Current number of item copies in the stack.                                     |
| 15    | ITEM_FIELD_DURATION             | Current duration (in milliseconds)                                              |
| 16    | ITEM_FIELD_SPELL_CHARGES        |                                                                                 |
| 21    | ITEM_FIELD_FLAGS                | Flags (from <a href="Item_template#flags">item_template</a>)                    |
| 22    | ITEM_FIELD_ENCHANTMENT          |                                                                                 |
| 55    | ITEM_FIELD_PROPERTY_SEED        | Also called ITEM_FIELD_SUFFIX_FACTOR                                            |
| 56    | ITEM_FIELD_RANDOM_PROPERTIES_ID |                                                                                 |
| 57    | ITEM_FIELD_ITEM_TEXT_ID         | Text id used and shown by the item.                                             |
| 58    | ITEM_FIELD_DURABILITY           | Current item durability.                                                        |
| 59    | ITEM_FIELD_MAXDURABILITY        | Maximum item durability.                                                        |
