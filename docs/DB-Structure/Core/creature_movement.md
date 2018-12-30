Back to [world database](mangosdb_struct) list of tables

## The `creature_movement` table
***
This table holds information on each unique creature (guid) waypoint.  In essence, a waypoint just defines a path that the creature will follow by going from point to point. More specifically, once the creature arrives at a point, it can do different things like cast a spell, do an emote, etc. Usually this table is filled through the .wp command (and its various subcommands) in the world.

Please note that for a creature to use waypoints, its MovementType must be 2.

To add waypoints in-game:
- .npc setmovetype way creature guid or select npc
- .wp add guid or select npc

### Structure:

*Field* | *Type* | *Null* | *Key* | *Default* | *Extra*
------------ | ------------- | -----------  | -----------  | -----------  | -----------
[id](creature_movement#id)|int(10) unsigned|NO|PRI|0||
[point](creature_movement#point)|mediumint(8)|NO|PRI|0||
[position_x](creature_movement#position_x)|float|NO||0||
[position_y](creature_movement#position_y)|float|NO||0||
[position_z](creature_movement#position_z)|float|NO||0||
[waittime](creature_movement#waittime)|int(10)|NO||0||
[script_id](creature_movement#script_id)|mediumint(8)|NO||0||
[orientation](creature_movement#orentation)|float|NO||0||


### Description of the fields

#### id
The guid of the creature if creature_movement. See [creature_guid](creature)

#### point

Defines the waypoint number. A creature will go from waypoint to waypoint in the order controlled by this field.

#### position&#95;x

The X position of the waypoint.

#### position&#95;y

The Y position of the waypoint.

#### position&#95;z

The Z position of the waypoint.

#### waittime

The time that the creature will wait before heading to the next waypoint, in milliseconds.

#### script&#95;id

Reference to [DBScripts_on_creature_movement](DBScripts_on_creature_movement)

#### orientation

The orientation the creature will face once it reaches the waypoint. 
(North = 0.0; South = pi (3.14159))


Setting this field to 100 means the creature will not change its orientation upon reaching the waypoint.
