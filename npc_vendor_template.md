Back to [world database](mangosdb_struct) list of tables.

The \`npc\_vendor(\_template)\` table
-------------------------------------

holds the vendor data for all NPCs that sell items by [\`creature\_template\`.\`entry\`](Creature_template#entry) or [creature\_template.VendorTemplateId](creature_template#VendorTemplateId).

The gold price for each item is in its item template as [BuyPrice](item_template#BuyPrice).

### Structure

| **Field**                                                | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry/VendorTemplateId](npc_vendor_template#guid/entry) | int(10) unsigned      | NO       | PRI     | 0           |           |
| [item](npc_vendor_template#item)                         | int(10) unsigned      | NO       | PRI     | 0           |           |
| [maxcount](npc_vendor_template#maxcount)                 | int(10) unsigned      | NO       |         | 0           |           |
| [incrtime](npc_vendor_template#incrtime)                 | int(10) unsigned      | NO       |         | 0           |           |
| [ExtendedCost](npc_vendor_template#extendedcost)         | mediumint(8) unsigned | NO       |         | 0           |           |

### Description of the fields

#### entry/VendorTemplateId

For npc\_vendor it's the [\`creature\_template\`.\`entry\`](Creature_template#entry) of the creature

For npc\_vendor\_template it's the [creature\_template.VendorTemplateId](creature_template#VendorTemplateId) of the vending\_list which is sold by this entry.

#### item

The item ID. See [item\_template.entry](item_template#entry)

#### maxcount

The maximum number of copies of the item the vendor has available to be sold. If 0, then it is an unlimited number of copies.

#### incrtime

Combined with [maxcount](#maxcount), this field tells how often (in seconds) the vendor list is refreshed and the limited item copies are restocked. For limited item copies, every refresh, the quantity is increased by [item\_template.BuyCount](item_template#BuyCount)

#### ExtendedCost

The value here corresponds to the ID in ItemExtendedCost.dbc and that ID controls the item's non monetary price, be it honor points, arena points, different types of badges or any combination of the above.
