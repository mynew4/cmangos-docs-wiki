Back to the [characters database](charactersdb_struct) list of tables.

The \`guild\_rank\` table
-------------------------

This table holds the information on all of the ranks available in a guild along with their names and what rights a person with that rank has.

### Structure

| **Field**                                     | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------|------------------|----------|---------|-------------|-----------|
| [guildid](Guild_rank#guildid)                 | int(6) unsigned  | NO       | PRI     | 0           |           |
| [rid](Guild_rank#rid)                         | int(11) unsigned | NO       | PRI     |             |           |
| [rname](Guild_rank#rname)                     | varchar(255)     | NO       |         |             |           |
| [rights](Guild_rank#rights)                   | int(3) unsigned  | NO       |         | 0           |           |
| [BankMoneyPerDay](Guild_rank#bankmoneyperday) | int(11) unsigned | NO       |         | 0           |           |

### Description of the fields

#### guildid

The guild ID that the rank is part of. See [guild.guildid](guild#guildid)

#### rid

The particular rank ID. This number must be unique to each rank in a guild.

#### rname

The name of the rank that is displayed in-game.

#### rights

The rights a player with this rank has in the guild. The calculation of multiple rights is a bit different in this case as the rights do not all have 2^n values. To combine ranks, you must do the OR operation (|) on the two flags.

<table>
<colgroup>
<col width="7%" />
<col width="24%" />
<col width="68%" />
</colgroup>
<thead>
<tr class="header">
<th>Flag</th>
<th>Name</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>64</td>
<td>GR_RIGHT_EMPTY</td>
<td>Having just this flag by itself is equivalent to having no rights at all.</td>
</tr>
<tr class="even">
<td>65</td>
<td>GR_RIGHT_GCHATLISTEN</td>
<td>Player can read messages in the guild general chat channel.</td>
</tr>
<tr class="odd">
<td>66</td>
<td>GR_RIGHT_GCHATSPEAK</td>
<td>Player can type messages in the guild general chat channel.</td>
</tr>
<tr class="even">
<td>68</td>
<td>GR_RIGHT_OFFCHATLISTEN</td>
<td>Player can read messages in the guild officers channel.</td>
</tr>
<tr class="odd">
<td>72</td>
<td>GR_RIGHT_OFFCHATSPEAK</td>
<td>Player can type messages in the guild officers channel.</td>
</tr>
<tr class="even">
<td>80</td>
<td>GR_RIGHT_INVITE</td>
<td>Can invite other players to guild.</td>
</tr>
<tr class="odd">
<td>96</td>
<td>GR_RIGHT_REMOVE</td>
<td>Can kick other players out of guild.</td>
</tr>
<tr class="even">
<td>192</td>
<td>GR_RIGHT_PROMOTE</td>
<td>Can promote other players.</td>
</tr>
<tr class="odd">
<td>320</td>
<td>GR_RIGHT_DEMOTE</td>
<td>Can demote other players.</td>
</tr>
<tr class="even">
<td>4160</td>
<td>GR_RIGHT_SETMOTD</td>
<td>Can change the guild message of the day.</td>
</tr>
<tr class="odd">
<td>8256</td>
<td>GR_RIGHT_EPNOTE</td>
<td>Can edit other players' personal notes.</td>
</tr>
<tr class="even">
<td>16448</td>
<td>GR_RIGHT_VIEWOFFNOTE</td>
<td>Can view the officer notes of other players.</td>
</tr>
<tr class="odd">
<td>32832</td>
<td>GR_RIGHT_EOFFNOTE</td>
<td>Can edit officer notes of other players.</td>
</tr>
<tr class="even">
<td>61951</td>
<td>GR_RIGHT_ALL</td>
<td>Has all of the rights.</td>
</tr>
</tbody>
</table>

#### BankMoneyPerDay

The total money per day, in copper, that a person with this rank can take out. Use the maximum value of an unsigned int (4294967295) to specify unlimited amount.
