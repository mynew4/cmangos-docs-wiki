Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_queststatus\` table
------------------------------------

Holds information on the quest status of each character.

### Structure

| **Field**                                      | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Character_queststatus#guid)             | int(11) unsigned    | NO       | PRI     | 0           |           |
| [quest](Character_queststatus#quest)           | int(11) unsigned    | NO       | PRI     | 0           |           |
| [status](Character_queststatus#status)         | int(11) unsigned    | NO       |         | 0           |           |
| [rewarded](Character_queststatus#rewarded)     | tinyint(1) unsigned | NO       |         | 0           |           |
| [explored](Character_queststatus#explored)     | tinyint(1) unsigned | NO       |         | 0           |           |
| [timer](Character_queststatus#timer)           | bigint(20) unsigned | NO       |         | 0           |           |
| [mobcount1](Character_queststatus#mobcount1)   | int(11) unsigned    | NO       |         | 0           |           |
| [mobcount2](Character_queststatus#mobcount2)   | int(11) unsigned    | NO       |         | 0           |           |
| [mobcount3](Character_queststatus#mobcount3)   | int(11) unsigned    | NO       |         | 0           |           |
| [mobcount4](Character_queststatus#mobcount4)   | int(11) unsigned    | NO       |         | 0           |           |
| [itemcount1](Character_queststatus#itemcount1) | int(11) unsigned    | NO       |         | 0           |           |
| [itemcount2](Character_queststatus#itemcount2) | int(11) unsigned    | NO       |         | 0           |           |
| [itemcount3](Character_queststatus#itemcount3) | int(11) unsigned    | NO       |         | 0           |           |
| [itemcount4](Character_queststatus#itemcount4) | int(11) unsigned    | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the character. See [character.guid](character#guid)

#### quest

The quest ID. See [quest\_template.entry](quest_template#entry)

#### status

The current quest status.

<table>
<caption>
Possible values

</caption>
<thead>
<tr class="header">
<th align="left">
Value

</th>
<th align="left">
Status

</th>
<th align="left">
Comments

</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">
0

</td>
<td align="left">
QUEST_STATUS_NONE

</td>
<td align="left">
Quest isn't shown in quest list; default

</td>
</tr>
<tr class="even">
<td align="left">
1

</td>
<td align="left">
QUEST_STATUS_COMPLETE

</td>
<td align="left">
Quest has been completed

</td>
</tr>
<tr class="odd">
<td align="left">
2

</td>
<td align="left">
QUEST_STATUS_UNAVAILABLE

</td>
<td align="left">
Quest is unavailable to the character

</td>
</tr>
<tr class="even">
<td align="left">
3

</td>
<td align="left">
QUEST_STATUS_INCOMPLETE

</td>
<td align="left">
Quest is active in quest log but incomplete

</td>
</tr>
<tr class="odd">
<td align="left">
4

</td>
<td align="left">
QUEST_STATUS_AVAILABLE

</td>
<td align="left">
Quest is available to be taken by character

</td>
</tr>
</tbody>
</table>
#### rewarded

Boolean 1 or 0 representing whether the quest has been rewarded or not.

#### explored

Boolean 1 or 0 representing if the character has explored what was needed to explore for the quest.

#### timer

Remaining time left on the quest if the quest has a timer. See [quest\_template.LimitTime](quest_template#LimitTime)

#### mobcount1

Current count of the number of kills or casts on the first creature or gameobject, if any. Corresponds with [quest\_template.ReqCreatureOrGOCount1](quest_template#ReqCreatureOrGOCount1)

#### mobcount2

Current count of the number of kills or casts on the second creature or gameobject, if any. Corresponds with [quest\_template.ReqCreatureOrGOCount2](quest_template#ReqCreatureOrGOCount2)

#### mobcount3

Current count of the number of kills or casts on the third creature or gameobject, if any. Corresponds with [quest\_template.ReqCreatureOrGOCount3](quest_template#ReqCreatureOrGOCount3)

#### mobcount4

Current count of the number of kills or casts on the fourth creature or gameobject, if any. Corresponds with [quest\_template.ReqCreatureOrGOCount4](quest_template#ReqCreatureOrGOCount4)

#### itemcount1

Current item count for the first item in a delivery quest, if any. Corresponds with [quest\_template.ReqItemCount1](quest_template#ReqItemCount1)

#### itemcount2

Current item count for the second item in a delivery quest, if any. Corresponds with [quest\_template.ReqItemCount2](quest_template#ReqItemCount2)

#### itemcount3

Current item count for the third item in a delivery quest, if any. Corresponds with [quest\_template.ReqItemCount3](quest_template#ReqItemCount3)

#### itemcount4

Current item count for the fourth item in a delivery quest, if any. Corresponds with [quest\_template.ReqItemCount4](quest_template#ReqItemCount4)
