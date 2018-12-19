Back to [world database](mangosdb_struct) list of tables.

The \`playercreateinfo\_item\` table
------------------------------------

This table holds information on what items each race-class combination of a new character starts out with.

### Structure

| **Field**                              | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [race](Playercreateinfo_item#race)     | tinyint(3) unsigned   | NO       | MUL     | 0           |           |
| [class](Playercreateinfo_item#class)   | tinyint(3) unsigned   | NO       |         | 0           |           |
| [itemid](Playercreateinfo_item#itemid) | mediumint(8) unsigned | NO       |         | 0           |           |
| [amount](Playercreateinfo_item#amount) | tinyint(8) unsigned   | NO       |         | 1           |           |

### Description of the fields

#### race

The character's race.

#### class

The character's class.

#### itemid

The template ID of the item. See [item\_template.entry](item_template#entry)

#### amount

The number of copies of that item.
