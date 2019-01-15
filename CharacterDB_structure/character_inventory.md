Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_inventory\` table
----------------------------------

Contains all the character inventory data, including the bank data.

### Structure

| **Field**                                           | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Character_inventory#guid)                    | int(11) unsigned    | NO       |         | 0           |           |
| [bag](Character_inventory#bag)                      | int(11) unsigned    | NO       |         | 0           |           |
| [slot](Character_inventory#slot)                    | tinyint(3) unsigned | NO       |         | 0           |           |
| [item](Character_inventory#item)                    | int(11) unsigned    | NO       | PRI     | 0           |           |
| [item\_template](Character_inventory#item_template) | int(11) unsigned    | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### bag

If it isn't 0, then it is the bag's item GUID. See [item\_instance.guid](item_instance#guid)

#### slot

If the bag field is non-zero, then the slot is the slot in the bag where the item is kept. The range can differ depending on the number of slots the bag has.<br>
If the bag field is zero, then the slot has a range of 0 to 84 and the value stands for the following:

| Slot \# | Value         |
|---------|---------------|
| 0       | Head          |
| 1       | Neck          |
| 2       | Shoulders     |
| 3       | Body          |
| 4       | Chest         |
| 5       | Waist         |
| 6       | Legs          |
| 7       | Feet          |
| 8       | Wrists        |
| 9       | Hands         |
| 10      | Finger 1      |
| 11      | Finger 2      |
| 12      | Trinket 1     |
| 13      | Trinket 2     |
| 14      | Back          |
| 15      | Main Hand     |
| 16      | Off Hand      |
| 17      | Ranged        |
| 18      | Tabard        |
| 19-22   | Equipped Bags |
| 23-38   | Main Backpack |
| 39-67   | Main Bank     |
| 68-74   | Bank Bags     |

#### item

The item's GUID. See [item\_instance.guid](item_instance#guid)

#### item\_template

The item's template entry. See [item\_template.entry](item_template#entry)
