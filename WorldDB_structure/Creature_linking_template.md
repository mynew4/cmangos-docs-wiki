Back to [world database](mangosdb_struct) list of tables.
To link creatures by GUID, please refer to [Creature\_linking](Creature_linking)

The \`Creature\_linking\_template\` table
-----------------------------------------

### Structure

| **Name**                                                | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry](Creature_linking_template#entry)                | int(10) unsigned      | NO       | PRI     | 0           |           |
| [map](Creature_linking_template#map)                    | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [master\_entry](Creature_linking_template#master_entry) | int(10) unsigned      | NO       |         | 0           |           |
| [flag](Creature_linking_template#flag)                  | mediumint(8) unsigned | NO       |         | 0           |           |
| [search\_range](Creature_linking_template#search_range) | mediumint(8) unsigned | NO       |         | 0           |           |

### Description of the fields

#### entry

[creature\_template.entry](creature_template#entry) of the slave mob that is linked

#### map

Id of map of the mobs

#### master\_entry

master to trigger events

#### flag

flag - describing what should happen when

<table>
<colgroup>
<col width="5%" />
<col width="28%" />
<col width="65%" />
</colgroup>
<thead>
<tr class="header">
<th>Flag</th>
<th>Name</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>FLAG_AGGRO_ON_AGGRO</td>
<td>the &quot;slave&quot; aggroes when the &quot;master&quot; aggroes</td>
</tr>
<tr class="even">
<td>2</td>
<td>FLAG_TO_AGGRO_ON_AGGRO</td>
<td>the master aggroes when the slave aggroes</td>
</tr>
<tr class="odd">
<td>4</td>
<td>FLAG_RESPAWN_ON_EVADE</td>
<td>the slave respawns when the master evades</td>
</tr>
<tr class="even">
<td>8</td>
<td>FLAG_TO_RESPAWN_ON_EVADE</td>
<td>the master respawns when the slave evades</td>
</tr>
<tr class="odd">
<td>16</td>
<td>FLAG_DESPAWN_ON_DEATH</td>
<td>the slave despawns when the master dies</td>
</tr>
<tr class="even">
<td>32</td>
<td>FLAG_SELFKILL_ON_DEATH</td>
<td>the slave goes suicide when the master dies</td>
</tr>
<tr class="odd">
<td>64</td>
<td>FLAG_RESPAWN_ON_DEATH</td>
<td>the slave respawn when the master dies</td>
</tr>
<tr class="even">
<td>128</td>
<td>FLAG_RESPAWN_ON_RESPAWN</td>
<td>the slave respawns on master respawn</td>
</tr>
<tr class="odd">
<td>256</td>
<td>FLAG_DESPAWN_ON_RESPAWN</td>
<td>the slave despawns on master respawn (TODO: check for slave != master)</td>
</tr>
<tr class="even">
<td>512</td>
<td>FLAG_FOLLOW</td>
<td>the slave follows the master, very basic, see TODO notes in commit, or post below</td>
</tr>
<tr class="odd">
<td>1024</td>
<td>FLAG_CANT_SPAWN_IF_BOSS_DEAD</td>
<td>the slave cannot respawn while boss is dead</td>
</tr>
<tr class="even">
<td>2048</td>
<td>FLAG_CANT_SPAWN_IF_BOSS_ALIVE</td>
<td>the slave cannot respawn while boss is alive</td>
</tr>
<tr class="odd">
<td>4096</td>
<td>FLAG_DESPAWN_ON_EVADE</td>
<td>the slave despawn after the master evade</td>
</tr>
<tr class="even">
<td>8192</td>
<td>FLAG_DESPAWN_ON_DESPAWN</td>
<td>the slave despawn after the master despawns</td>
</tr>
</tbody>
</table>

#### search\_range

IF given != 0 only mobs with spawn-dist &lt;= search\_range around the master\_entry will be linked to the master. Use this to model group behaviour.

IF = 0 all mobs on the map are linked to the master.
