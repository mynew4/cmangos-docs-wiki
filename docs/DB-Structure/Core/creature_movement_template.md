Back to [world database](mangosdb_struct) list of tables.

The \`creature\_movement(\_template)\` table
--------------------------------------------

holds all the information on creature's waypoints by [\`creature\`.\`guid\`](Creature#guid) or [\`creature\_template\`.\`entry\`](Creature_template#entry). In essence, a waypoint just defines a path that the creature will follow by going from point to point. More specifically, once the creature arrives at a point, it can do different things like cast a spell, do an emote, etc. Usually this table is filled through the .wp command (and its various subcommands) in the world.

Please note that for a creature to use waypoints, its [MovementType](creature#MovementType) must be 2 for its [\`creature\`.\`guid\`](Creature#guid).

### Structure

| **Field**                                             | **Type**              | **Null** | **Key** | **Default** | **Extra**               |
|-------------------------------------------------------|-----------------------|----------|---------|-------------|-------------------------|
| [guid/entry](creature_movement_template#guid/entry)   | int(10) unsigned      | NO       | PRI     | 0           |                         |
| [pathId](creature_movement_template#pathId)           | int(11) unsigned      | NO       | PRI     | 0           | CURRENTLY TEMPLATE ONLY |
| [point](creature_movement_template#point)             | int(10) unsigned      | NO       | PRI     | 0           |                         |
| [position\_x](creature_movement_template#position_x)  | float                 | NO       |         | 0           |                         |
| [position\_y](creature_movement_template#position_y)  | float                 | NO       |         | 0           |                         |
| [position\_z](creature_movement_template#position_z)  | float                 | NO       |         | 0           |                         |
| [waittime](creature_movement_template#waittime)       | int(5) unsigned       | NO       |         | 0           |                         |
| [script\_id](creature_movement_template#script_id)    | mediumint(8) unsigned | NO       |         | 0           |                         |
| [orientation](creature_movement_template#orientation) | float                 | YES      |         | 0           |                         |

### Description of the fields

#### guid/entry

The [creature.guid](creature#guid) or [creature\_template.entry](Creature_template#Entry) of the creature.

#### pathId

0 means that this is the default path for any creature of the specified template. Any creature summoned, which is not assigned to another path, will start moving on pathId 0.
Setting this field to any other value allows you to use it for setting different paths to different creatures of the same template in DBScripts and in EventAI.

#### point

Defines the waypoint number. A creature will go from waypoint to waypoint in the order controlled by this field.

#### position\_x

The X position of the waypoint.

#### position\_y

The Y position of the waypoint.

#### position\_z

The Z position of the waypoint.

#### waittime

The time that the creature will wait before heading to the next waypoint, in milliseconds.

#### script\_id

Reference to [DBScripts\_on\_creature\_movement](DBScripts_on_creature_movement).

#### orientation

The orientation the creature will face once it reaches the waypoint.
(North = 0.0; South = pi (3.14159))

Setting this field to 100 means the creature will not change its orientation upon reaching the waypoint.
