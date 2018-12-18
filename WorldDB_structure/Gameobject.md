Back to [world database](mangosdb_struct) list of tables.

The \`gameobject\` table
------------------------

This table holds the individual object data on each spawned game object in the world. This data along with the object's template data is read and used to instantiate the objects in the world.

### Structure

| **Field**                                 | **Type**             | **Null** | **Key** | **Default** | **Extra**       |
|-------------------------------------------|----------------------|----------|---------|-------------|-----------------|
| [guid](Gameobject#guid)                   | int(10) unsigned     | NO       | PRI     | None        | auto\_increment |
| [id](Gameobject#id)                       | int(10) unsigned     | NO       |         | 0           |                 |
| [map](Gameobject#map)                     | int(10) unsigned     | NO       |         | 0           |                 |
| [spawnMask](Gameobject#spawnmask)         | tinyint(3) unsigned  | NO       |         | 1           |                 |
| [phaseMask](Gameobject#phasemask)         | smallint(5) unsigned | NO       |         | 1           |                 |
| [position\_x](Gameobject#position_x)      | float                | NO       |         | 0           |                 |
| [position\_y](Gameobject#position_y)      | float                | NO       |         | 0           |                 |
| [position\_z](Gameobject#position_z)      | float                | NO       |         | 0           |                 |
| [orientation](Gameobject#orientation)     | float                | NO       |         | 0           |                 |
| [rotation0](Gameobject#rotation0)         | float                | NO       |         | 0           |                 |
| [rotation1](Gameobject#rotation1)         | float                | NO       |         | 0           |                 |
| [rotation2](Gameobject#rotation2)         | float                | NO       |         | 0           |                 |
| [rotation3](Gameobject#rotation3)         | float                | NO       |         | 0           |                 |
| [spawntimesecs](Gameobject#spawntimesecs) | int(10) unsigned     | NO       |         | 0           |                 |
| [animprogress](Gameobject#animprogress)   | int(10) unsigned     | NO       |         | 0           |                 |
| [state](Gameobject#state)                 | int(10) unsigned     | NO       |         | 1           |                 |

### Description of the fields

#### guid

The global unique identifier for the game object. This field must be unique among all game objects.

#### id

The template ID of the gameobject. See [gameobject\_template.entry](gameobject_template#entry)

#### map

The map ID where this object is spawned. See [Map.dbc](Map.dbc)

#### spawnMask

Controls under which difficulties the object is spawned. Combine value to get wished case.

| Value | Comment                                                                                     |
| ----- | ------------------------------------------------------------------------------------------- |
| 0     | Not spawned                                                                                 |
| 1     | Spawned only in normal versions of maps (includes maps without additional difficulty modes) |
| 2     | Spawned only in difficulty = 1 versions of maps (mostly heroic)                             |
| 4     | Spawned only in difficulty = 2 versions of maps                                             |
| 8     | Spawned only in difficulty = 3 versions of maps                                             |
| 15    | Spawned in all versions of maps                                                             |

#### phaseMask

Controls what phase gameobject is at. 1=default phase. Phase masks are got from Aura 261 effect ( (Aura \#261) (4) ) = phasemask = 4.

#### position\_x

The X position.

#### position\_y

The Y position.

#### position\_z

The Z position.

#### orientation

The orientation. (North = 0, South = 3.14159)

#### rotation0

GameObject Rotation: X:

#### rotation1

GameObject Rotation: Y:

#### rotation2

GameObject Rotation: Z:

#### rotation3

GameObject Rotation: W:

#### spawntimesecs

Time in seconds for this object to respawn.

Using a negative value will result in the object starting out by being "despawned" until a script will spawn it. It will then despawn after the amount of time specified here has passed.

#### animprogress

Not really known what this is used for at this time. However, always set it to 100 for chests.

#### state

Only for chests.

-   1 = closed
-   0 = open
