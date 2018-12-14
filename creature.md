Back to [world database](mangosdb_struct) list of tables.

The \`creature\` table
----------------------

contains individual creature spawn data. Spawn of a creature is an instance of the creature object in the world.

### Structure

| **Field**                                     | **Type**              | **Null** | **Key** | **Default** | **Extra**       |
|-----------------------------------------------|-----------------------|----------|---------|-------------|-----------------|
| [guid](creature#guid)                         | int(10) unsigned      | NO       | PRI     | None        | auto\_increment |
| [id](creature#id)                             | mediumint(8) unsigned | NO       | MUL     | 0           |                 |
| [map](creature#map)                           | smallint(5) unsigned  | NO       | MUL     | 0           |                 |
| [spawnMask](creature#spawnmask)               | tinyint(3) unsigned   | NO       |         | 1           |                 |
| [phaseMask](creature#phasemask)               | smallint(5) unsigned  | NO       |         | 1           | (WotLK)         |
| [modelid](creature#modelid)                   | mediumint(8) unsigned | YES      |         | 0           |                 |
| [equipment\_id](creature#equipment_id)        | mediumint(9)          | NO       |         | 0           |                 |
| [position\_x](creature#position_x)            | float                 | NO       |         | 0           |                 |
| [position\_y](creature#position_y)            | float                 | NO       |         | 0           |                 |
| [position\_z](creature#position_z)            | float                 | NO       |         | 0           |                 |
| [orientation](creature#orientation)           | float                 | NO       |         | 0           |                 |
| [spawntimesecsmin](creature#spawntimesecsmin) | int(10) unsigned      | NO       |         | 120         |                 |
| [spawntimesecsmax](creature#spawntimesecsmax) | int(10) unsigned      | NO       |         | 120         |                 |
| [spawndist](creature#spawndist)               | float                 | NO       |         | 5           |                 |
| [currentwaypoint](creature#currentwaypoint)   | mediumint(8) unsigned | NO       |         | 0           |                 |
| [curhealth](creature#curhealth)               | int(10) unsigned      | NO       |         | 1           |                 |
| [curmana](creature#curmana)                   | int(10) unsigned      | NO       |         | 0           |                 |
| [DeathState](creature#deathstate)             | tinyint(3) unsigned   | NO       |         | 0           |                 |
| [MovementType](creature#movementtype)         | tinyint(3) unsigned   | NO       |         | 0           |                 |

### Description of the fields

#### guid

A unique identifier given to each creature to distinguish one creature from another. Two creatures can NOT have same GUID.

#### id

The id of the template that is used when instantiating this creature. See [creature\_template.entry](creature_template#entry)

#### map

The Map ID of the position of the creature. See [Map.dbc](Map.dbc)

#### spawnMask

Controls under which difficulties the creature will be spawned.

<table>
<colgroup>
<col width="8%" />
<col width="91%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>Not spawned</td>
</tr>
<tr class="even">
<td>1</td>
<td>Spawned only in 10-man-normal versions of maps (includes maps without a heroic mode)</td>
</tr>
<tr class="odd">
<td>2</td>
<td>Spawned only in 25-man-normal versions of maps (or heroics pre 3.2)</td>
</tr>
<tr class="even">
<td>4</td>
<td>Spawned only in 10-man heroic versions of maps</td>
</tr>
<tr class="odd">
<td>8</td>
<td>Spawned only in 25-man-heroic versions of maps</td>
</tr>
<tr class="even">
<td>15</td>
<td>Spawned in all versions of maps</td>
</tr>
</tbody>
</table>

#### phaseMask

Defines which phase the creature belongs. 1 is default phase, rest are from spell's aura 261, (Aura \#261) (4) = phasemask = 4.

#### modelid

The model ID associated with this creature. Note that two creatures that use the same template can have different models. See [creature\_model\_info](creature_model_info) for more information on model-specific characteristics.

#### equipment\_id

The ID of the equipment that the creature is using. See [creature\_equip\_template.entry](creature_equip_template#entry)

#### position\_x

The X position of the creature.

#### position\_y

The Y position of the creature.

#### position\_z

The Z position of the creature.

#### orientation

The orientation of the creature. (North = 0.0; South = pi (3.14159))

#### spawntimesecsmin

The minimum respawn time of the creature in seconds.

#### spawntimesecsmax

The maximum respawn time of the creature in seconds.

#### spawndist

The maximum distance that the creature should spawn from its spawn point. Also controls how far away the creature can walk from its spawn point if its [MovementType](creature#MovementType) = 1.

| Value | Comment                       |
|-------|-------------------------------|
| 1     | Orientation change only       |
| 2     | Lowest random movement value  |
| 5     | Default random movement value |

#### currentwaypoint

The current waypoint number that the creature is on, if any. See [creature\_movement.point](creature_movement#point)

#### curhealth

The current health that the creature has.

#### curmana

The current mana that the creature has.

#### DeathState

The creature's death state.
A boolean, 0 = Alive, 1 = Corpse lying dead around (no gossip possible when dead, if you need corpse-gossip use dynamicflags|32)

#### MovementType

See [creature\_template.MovementType](creature_template#MovementType) for possible values.

creature\_movement and creature\_movement\_template need to have MovementType set to 2 for a guid.
