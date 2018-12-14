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

<table>
<colgroup>
<col width="6%" />
<col width="31%" />
<col width="61%" />
</colgroup>
<thead>
<tr class="header">
<th>Index</th>
<th>Value Name</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>OBJECT_FIELD_GUID</td>
<td>Item GUID</td>
</tr>
<tr class="even">
<td>2</td>
<td>OBJECT_FIELD_TYPE</td>
<td>Should be 3 (TYPE_OBJECT + TYPE_ITEM)</td>
</tr>
<tr class="odd">
<td>3</td>
<td>OBJECT_FIELD_ENTRY</td>
<td>entry</td>
</tr>
<tr class="even">
<td>4</td>
<td>OBJECT_FIELD_SCALE_X</td>
<td>1.0</td>
</tr>
<tr class="odd">
<td>5</td>
<td>OBJECT_FIELD_PADDING</td>
<td></td>
</tr>
<tr class="even">
<td>6</td>
<td>ITEM_FIELD_OWNER</td>
<td>owner_guid</td>
</tr>
<tr class="odd">
<td>8</td>
<td>ITEM_FIELD_CONTAINED</td>
<td>If the item is in a bag, the GUID of the bag item; otherwise owner GUID.</td>
</tr>
<tr class="even">
<td>10</td>
<td>ITEM_FIELD_CREATOR</td>
<td>GUID of character who created the item.</td>
</tr>
<tr class="odd">
<td>12</td>
<td>ITEM_FIELD_GIFTCREATOR</td>
<td>GUID of character who created the <a href="character_gifts#item_guid.">item</a></td>
</tr>
<tr class="even">
<td>14</td>
<td>ITEM_FIELD_STACK_COUNT</td>
<td>Current number of item copies in the stack.</td>
</tr>
<tr class="odd">
<td>15</td>
<td>ITEM_FIELD_DURATION</td>
<td>Current duration (in milliseconds)</td>
</tr>
<tr class="even">
<td>16</td>
<td>ITEM_FIELD_SPELL_CHARGES</td>
<td></td>
</tr>
<tr class="odd">
<td>21</td>
<td>ITEM_FIELD_FLAGS</td>
<td>Flags (from <a href="Item_template#flags">item_template</a>)</td>
</tr>
<tr class="even">
<td>22</td>
<td>ITEM_FIELD_ENCHANTMENT</td>
<td></td>
</tr>
<tr class="odd">
<td>55</td>
<td>ITEM_FIELD_PROPERTY_SEED</td>
<td>Also called ITEM_FIELD_SUFFIX_FACTOR</td>
</tr>
<tr class="even">
<td>56</td>
<td>ITEM_FIELD_RANDOM_PROPERTIES_ID</td>
<td></td>
</tr>
<tr class="odd">
<td>57</td>
<td>ITEM_FIELD_ITEM_TEXT_ID</td>
<td>Text id used and shown by the item.</td>
</tr>
<tr class="even">
<td>58</td>
<td>ITEM_FIELD_DURABILITY</td>
<td>Current item durability.</td>
</tr>
<tr class="odd">
<td>59</td>
<td>ITEM_FIELD_MAXDURABILITY</td>
<td>Maximum item durability.</td>
</tr>
</tbody>
</table>


