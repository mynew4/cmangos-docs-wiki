Back to [world database](mangosdb_struct) list of tables.

The \`item\_expire\_convert\` table
-----------------------------------

This table contains pairs of times which turn into an other item after a certain amount of time.

### Structure

| **Field**                          | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry](Item_expire_convert#entry) | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [item](Item_expire_convert#item)   | mediumint(8)          | NO       |         | 0           |           |

### Description of the fields

#### entry

The entry of the item which suppose to change into a new item.

#### item

The entry of the new item.
