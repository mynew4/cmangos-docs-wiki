Back to [dbc files](dbc_files) list.

### LockType.dbc

This DBC contains data used with [Lock.dbc](Lock.dbc)

**Version is : 3.3.5a**

### Structure

<table>
<colgroup>
<col width="14%" />
<col width="15%" />
<col width="10%" />
<col width="58%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Field Nb</strong></th>
<th><strong>Name</strong></th>
<th><strong>Type</strong></th>
<th><strong>Comment</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>ID</td>
<td>Int</td>
<td></td>
</tr>
<tr class="even">
<td>2</td>
<td>Name</td>
<td>String</td>
<td></td>
</tr>
<tr class="odd">
<td>19</td>
<td>ItemStateName</td>
<td>String</td>
<td>The processed item's state (locked, unlocked, fish etc.)</td>
</tr>
<tr class="even">
<td>36</td>
<td>ProcessName</td>
<td>String</td>
<td>Opening processes' name</td>
</tr>
<tr class="odd">
<td>53</td>
<td>InternalName</td>
<td>String</td>
<td>Empty most of the time</td>
</tr>
</tbody>
</table>

<hr />
### Content

| **ID** | **Name**                   | **ItemStateName**    | **ProcessName** | **InternalName** |
|--------|----------------------------|----------------------|-----------------|------------------|
| 1      | Lockpicking                | Locked Items         | Pick            | PickLock         |
| 2      | Herbalism                  | Herbs                | Gather          | GatherHerbs      |
| 3      | Mining                     | Ore Deposits         | Mine            | Mine             |
| 4      | Disarm Trap                | Trap                 | Disarm          |                  |
| 5      | Open                       | Unlocked Items       | Open            |                  |
| 6      | Treasure (DND)             | Treasure             |                 |                  |
| 7      | Calcified Elven Gems (DND) | Calcified Elven Gems |                 |                  |
| 8      | Close                      | Unlocked Items       | Close           |                  |
| 9      | Arm Trap                   | Trap                 | Arm             |                  |
| 10     | Quick Open                 | Unlocked Items       | Open            |                  |
| 11     | Quick Close                | Unlocked Items       | Close           |                  |
| 12     | Open Tinkering             | Unlocked Items       | Open            |                  |
| 13     | Open Kneeling              | Unlocked Items       | Open            |                  |
| 14     | Open Attacking             | Unlocked Items       | Open            |                  |
| 15     | Gahz'ridian (DND)          | Gahz'ridian          |                 |                  |
| 16     | Blasting                   | Locked Items         | Blast           |                  |
| 17     | Pvp Open                   | Unlocked Items       | Open            |                  |
| 18     | Pvp Close                  | Unlocked Items       | Close           |                  |
| 19     | Fishing (DND)              | Fish                 | Fish            |                  |
| 20     | Inscription                | Tomes                | Decipher        |                  |
| 21     | Open From Vehicle          | Unlocked Items       | Open            |                  |


