Back to [world database](mangosdb_struct) list of tables.

The \`dbscripts\_on\_\*\` tables
--------------------------------

The manual reference for these tables is located in the [doc/script\_commands.txt](https://github.com/cmangos/mangos-wotlk/blob/master/doc/script_commands.txt) file.

**The information below may be outdated, use with caution!**

This table format is used for different tables to control possible scripts activated by different actions:

-   **\`dbscripts\_on\_go\_\[template\]\_use:** Holds possible scripts activated by gameobjects.
    Source: object user (unit); Target: gameobject.
    * dbscripts\_on\_go\_template\_use can be used for any type of gameobject.
    * dbscripts\_on\_go\_use can be used only for GAMEOBJECT\_TYPE\_DOOR (0) and GAMEOBJECT\_TYPE\_BUTTON (1)

<!-- -->
-   **\`dbscripts\_on\_spell:** Holds scripts that can be activated by spells with the following spell effects:
    * SPELL\_EFFECT\_DUMMY (3)
    * SPELL\_EFFECT\_TRIGGER\_SPELL (64) - only for missing triggered spells
    * SPELL\_EFFECT\_SCRIPT\_EFFECT (77)
    Source: caster; Target: target.

<!-- -->
-   **\`dbscripts\_on\_relay:** Holds scripts that can be activated by AI or other dbscripts. The usage of IDs is as following:
    * Classic - 1-9999
    * TBC - 10000-19999
    * WotLK - 20000+
    Source and Target are defined by the mechanism that launched it.

<!-- -->
-   **\`dbscripts\_on\_quest\_start:** Holds scripts activated when a player accepts a quest.
    Source: quest giver (creature); Target: player; Script execution unique by source.

<!-- -->
-   **\`dbscripts\_on\_quest\_end:** Holds scripts activated when a player finishes a quest.
    Source: quest taker (creature); Target: player; Script execution unique by source.

<!-- -->
-   **\`dbscripts\_on\_creature\_movement:** Holds scripts activated while a npc is moving.
    Source: moving creature; Target moving creature.

<!-- -->
-   **\`dbscripts\_on\_creature\_death:** Holds scripts activated when a creature dies.
    Source: killed creature; Target: responsible killer (unit or player).

<!-- -->
-   **\`dbscripts\_on\_event:** Holds scripts activated whenever an event is activated by spell, gameobject or taxi waypoints. The following spell effects and gameobjecs can activate an event:
    * SPELL\_EFFECT\_SEND\_EVENT (61)
    * GAMEOBJECT\_TYPE\_CHEST (3)
    * GAMEOBJECT\_TYPE\_GOOBER (10)
    * GAMEOBJECT\_TYPE\_TRANSPORT (11) \[not supported yet\]
    * GAMEOBJECT\_TYPE\_CAMERA (13)
    * GAMEOBJECT\_TYPE\_MO\_TRANSPORT (15) \[partially supported\]
    * GAMEOBJECT\_TYPE\_FLAGDROP (26) \[not supported yet\]
    * GAMEOBJECT\_TYPE\_CAPTURE\_POINT (29)
    * GAMEOBJECT\_TYPE\_DESTRUCTIBLE\_BUILDING (33)
    Source, Target and Script execution can be different based on the event activation source.

<!-- -->
-   **\`dbscripts\_on\_gossip:** Holds scripts activated on gossip\_menu\_option or gossip\_menu.
    * For gossip\_menu - Source: player; Target: gossip holder (creature or gameobject); Script execution unique by target.
    * For gossip\_menu\_option when gossip holder is creature - Source: gossip holder (creature); Target: player; Script execution unique by source.
    * For gossip\_menu\_option when gossip holder is gameobject - Source: player; Target: gossip holder (gameobject); Script execution unique by target.

NOTE: An entry in this table may have more than one row as a script may do more than just one action. Also each action the script may make can have a separate [delay](dbscripts#delay) attached to it. In that case, the core will activate the appropriate action after the correct [delay](dbscripts#delay).

### Structure

| **Field**                                 | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [id](dbscripts#id)                        | int(8) unsigned       | NO       |         | 0           |           |
| [delay](dbscripts#delay)                  | int(10) unsigned      | NO       |         | 0           |           |
| [command](dbscripts#command)              | mediumint(8) unsigned | NO       |         | 0           |           |
| [datalong](dbscripts#otherfields)         | mediumint(8) unsigned | NO       |         | 0           |           |
| [datalong2](dbscripts#otherfields)        | int(10) unsigned      | NO       |         | 0           |           |
| [datalong3](dbscripts#otherfields)        | int(11) unsigned      | NO       |         | 0           |           |
| [buddy\_entry](dbscripts#buddy_entry)     | int(10) unsigned      | NO       |         | 0           |           |
| [search\_radius](dbscripts#search_radius) | int(10) unsigned      | NO       |         | 0           |           |
| [data\_flags](dbscripts#data_flags)       | tinyint(3) unsigned   | NO       |         | 0           |           |
| [dataint](dbscripts#otherfields)          | int(11)               | NO       |         | 0           |           |
| [dataint2](dbscripts#otherfields)         | int(11)               | NO       |         | 0           |           |
| [dataint3](dbscripts#otherfields)         | int(11)               | NO       |         | 0           |           |
| [dataint4](dbscripts#otherfields)         | int(11)               | NO       |         | 0           |           |
| [x](dbscripts#otherfields)                | float                 | NO       |         | 0           |           |
| [y](dbscripts#otherfields)                | float                 | NO       |         | 0           |           |
| [z](dbscripts#otherfields)                | float                 | NO       |         | 0           |           |
| [o](dbscripts#otherfields)                | float                 | NO       |         | 0           |           |
| [comments](dbscripts#otherfields)         | VARCHAR (255)         | NO       |         | NULL        |           |

### Description of the fields

#### id

For **dbscripts\_on\_creature\_death**, it is the entry of the creature. See [creature\_template.entry](creature_template#entry).<br>
For **dbscripts\_on\_creature\_movement**, it is the [script id](Creature_movement#script_id) of the waypoint. The PROPER formatting for the ID field is as follows: Creature\_entry + 2-Digit Script ID (Starting at 01). Example: c.2386 has few movement\_scripts, so 2386+01 = 238601 ... 23602 ..etc<br>
For **dbscripts\_on\_event**, it is the event ID. There doesn't exist currently a full list of events. In any case, the event IDs are taken directly from gameobject WDB data or spell effect data. If both a gameobject and a spell activate the same event, the IDs will match.<br>
For **dbscripts\_on\_go\_template\_use**, it is the entry of the button/lever. See [gameobject\_template.entry](gameobject_template#entry).<br>
For **dbscripts\_on\_go\_use**, it is the guid of the button/lever. See [gameobject.guid](gameobject#guid).<br>
For **dbscripts\_on\_gossip**, it is the [action script id](Gossip_menu_option#action_script_id) of the gossip option.<br>
For **dbscripts\_on\_promo\_code\_use**, it is the ?<br>
For **dbscripts\_on\_quest\_end**, it is the ID that is used in [CompleteScript](quest_template#CompleteScript) in the quest template definition.<br>
For **dbscripts\_on\_quest\_start**, it is the ID that is used in [StartScript](quest_template#StartScript) in the quest template definition.<br>
For **dbsccripts\_on\_relay**, it is the entry of the creature. See [creature\_template.entry](creature_template#entry) + 2-Digit Script ID (Starting at 01). Example: c.21218 has few relay scripts, so 21218+01 = 2121801 ... 2121802 ..etc<br>
For **dbscripts\_on\_spell**, it is the Spell ID. See [spell\_template.Id](spell_template#Id)

#### delay

Delay in seconds before this current step of the script activates. 0 = instant.

NOTE: Delay is Cumulative From Script to Script with same ID.<br>
Example: Script 1 Has 5 seconds delay and then if you want script 2 to trigger 3 seconds later you would use delay value 8 (5+3) for script 2 in the sequence.

#### command

The type of action performed by the script after [delay](dbscripts#delay) seconds have passed. The value of this field affects what other fields also need to be set.

The following commands can be used (enum ScriptCommand):

| Command | Name                                   | Description                                                                             |
| ------- | -------------------------------------- | --------------------------------------------------------------------------------------- |
| 0       | SCRIPT_COMMAND_TALK                    | Creature say/whisper/yell/textemote.                                                    |
| 1       | SCRIPT_COMMAND_EMOTE                   | Plays emote on a player/creature.                                                       |
| 2       | SCRIPT_COMMAND_FIELD_SET               | Change the value at an index for the player.                                            |
| 3       | SCRIPT_COMMAND_MOVE_TO                 | Relocate creature to a destination                                                      |
| 4       | SCRIPT_COMMAND_FLAG_SET                | Turns on bits on a flag field at an index for the player.                               |
| 5       | SCRIPT_COMMAND_FLAG_REMOVE             | Turns off bits on a flag field at an index for the player.                              |
| 6       | SCRIPT_COMMAND_TELEPORT_TO             | Teleports the player to a location.                                                     |
| 7       | SCRIPT_COMMAND_QUEST_EXPLORED          | Satisfies the explore requirement for a quest.                                          |
| 8       | SCRIPT_COMMAND_KILL_CREDIT             | Satisfies the kill credit requirement for a quest.                                      |
| 9       | SCRIPT_COMMAND_RESPAWN_GAMEOBJECT      | Spawns a despawned gameobject.                                                          |
| 10      | SCRIPT_COMMAND_TEMP_SPAWN_CREATURE     | Temporarily summon a creature.                                                          |
| 11      | SCRIPT_COMMAND_OPEN_DOOR               | Opens a door gameobject (type == 0).                                                    |
| 12      | SCRIPT_COMMAND_CLOSE_DOOR              | Closes a door gameobject (type == 0).                                                   |
| 13      | SCRIPT_COMMAND_ACTIVATE_OBJECT         | Activate (use) a gameobject.                                                            |
| 14      | SCRIPT_COMMAND_REMOVE_AURA             | Removes an aura due to a spell.                                                         |
| 15      | SCRIPT_COMMAND_CAST_SPELL              | Casts a spell.                                                                          |
| 16      | SCRIPT_COMMAND_PLAY_SOUND              | Plays a sound.                                                                          |
| 17      | SCRIPT_COMMAND_CREATE_ITEM             | Creates an item.                                                                        |
| 18      | SCRIPT_COMMAND_DESPAWN_SELF            | Despawns a creature with some delay.                                                    |
| 19      | SCRIPT_COMMAND_PLAY_MOVIE              | Plays a movie to the target player.                                                     |
| 20      | SCRIPT_COMMAND_MOVEMENT                | Change the movement type of a creature (idle, random, waypoint).                        |
| 21      | SCRIPT_COMMAND_SET_ACTIVEOBJECT        | Set a creature as active object.                                                        |
| 22      | SCRIPT_COMMAND_SET_FACTION             | Changes the faction of a creature.                                                      |
| 23      | SCRIPT_COMMAND_MORPH_TO_ENTRY_OR_MODEL | Morphs a creature go a given model.                                                     |
| 24      | SCRIPT_COMMAND_MOUNT_TO_ENTRY_OR_MODEL | Mounts or dismounts a creature to mount entry or model.                                 |
| 25      | SCRIPT_COMMAND_SET_RUN                 | Makes a creature start or stop running.                                                 |
| 26      | SCRIPT_COMMAND_ATTACK_START            | Makes a creature attack things within a radius.                                         |
| 27      | SCRIPT_COMMAND_GO_LOCK_STATE           | Change the GO lock or interact flags.                                                   |
| 28      | SCRIPT_COMMAND_STAND_STATE             | Change the stand state of a creature.                                                   |
| 29      | SCRIPT_COMMAND_MODIFY_NPC_FLAGS        | Change NPC flags of a creature.                                                         |
| 30      | SCRIPT_COMMAND_SEND_TAXI_PATH          | Sends a player on a give taxi path.                                                     |
| 31      | SCRIPT_COMMAND_TERMINATE_SCRIPT        | Stop script execution if a given creature entry meets conditions.                       |
| 32      | SCRIPT_COMMAND_PAUSE_WAYPOINTS         | Pause or unpause waypoint movement.                                                     |
| 33      | SCRIPT_COMMAND_RESERVED_1              | Enable or disable experience gain for a player.                                         |
| 34      | SCRIPT_COMMAND_TERMINATE_COND          | Stop script execution when a give condition is met.                                     |
| 35      | SCRIPT_COMMAND_SEND_AI_EVENT           | Send a give AI event for EventAI around the source with a given radius.                 |
| 36      | SCRIPT_COMMAND_SET_FACING              | Turn resulting source to resulting target.                                              |
| 37      | SCRIPT_COMMAND_MOVE_DYNAMIC            | Move resulting source to a random point around resulting target or to resulting target. |
| 38      | SCRIPT_COMMAND_SEND_MAIL               | Send mail from resulting source to resulting target.                                    |
| 39      | SCRIPT_COMMAND_SET_FLY                 | Makes a creature start or stop flying.                                                  |
| 40      | SCRIPT_COMMAND_DESPAWN_GO              | Despawns a gameobject.                                                                  |
| 41      | SCRIPT_COMMAND_RESPAWN                 | Respawns a creature.                                                                    |
| 42      | SCRIPT_COMMAND_SET_EQUIPMENT_SLOTS     | Change equipment slots of the resulting source.                                         |
| 43      | SCRIPT_COMMAND_RESET_GO                | Reset a gameobject.                                                                     |
| 44      | SCRIPT_COMMAND_UPDATE_TEMPLATE         | Update creature entry.                                                                  |
| 45      | SCRIPT_COMMAND_START_RELAY_SCRIPT      | Launch relay script or relay template.                                                  |
| 46      | SCRIPT_COMMAND_CAST_CUSTOM_SPELL       | resSource = Unit, cast spell at resTarget = Unit                                        |

#### buddy\_entry

Commands except the ones requiring a player (like KILL\_CREDIT) have support for the buddy concept.

This means that if an entry for buddy\_entry is provided, aside from source and target as listed above also a "buddy" is available.

Which one on the three (originalSource, originalTarget, buddy) will be used in the [command](dbscripts#command), depends on the [data\_flags](dbscripts#data_flags) (enum ScriptInfoDataFlags) Note that some commands (like EMOTE) use only the resulting source for an action.

Possible combinations of the [data\_flags](dbscripts#data_flags) |SCRIPT\_FLAG\_BUDDY\_AS\_TARGET 0x01|SCRIPT\_FLAG\_REVERSE\_DIRECTION 0x02|SCRIPT\_FLAG\_SOURCE\_TARGETS\_SELF 0x04| are:

Where "A -> B" means that the [command](dbscripts#command) is executed from A with B as target.

| Hex  | A -> B                                                               |
|------|-------------------------------------------------------------------------|
| 0x00 | originalSource / buddyIfProvided -> originalTarget                   |
| 0x01 | originalSource -> buddy                                              |
| 0x02 | originalTarget -> originalSource / buddyIfProvided                   |
| 0x03 | buddy -> originalSource                                              |
| 0x04 | originalSource / buddyIfProvided -> originalSource / buddyIfProvided |
| 0x05 | originalSource -> originalSource                                     |
| 0x06 | originalTarget -> originalTarget                                     |
| 0x07 | buddy -> buddy                                                       |

#### search\_radius

Range in which the buddy defined in [buddy\_entry](dbscripts#buddy_entry) will be searched by [creature\_template.entry](creature_template#entry).

| &amp; data_flags                | Description                                                                                                                              |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| &amp; SCRIPT_FLAG_BUDDY_BY_GUID | [creature.guid](creature#guid) instead of [creature_template.entry](creature_template#entry)                                             |
| &amp; SCRIPT_FLAG_BUDDY_BY_POOL | [pool_creature.pool_entry](pool_creature#pool_entry) instead of [creature_template.entry](creature_template#entry)                       |

#### data\_flags

Defined in "enum ScriptInfoDataFlags"

| Hex | Type | Description                         |
|-----|------|-------------------------------------|
| 0   | 0x00 | DEFAULT                             |
| 1   | 0x01 | SCRIPT\_FLAG\_BUDDY\_AS\_TARGET     |
| 2   | 0x02 | SCRIPT\_FLAG\_REVERSE\_DIRECTION    |
| 4   | 0x04 | SCRIPT\_FLAG\_SOURCE\_TARGETS\_SELF |
| 8   | 0x08 | SCRIPT\_FLAG\_COMMAND\_ADDITIONAL   |
| 16  | 0x10 | SCRIPT\_FLAG\_BUDDY\_BY\_GUID       |
| 32  | 0x20 | SCRIPT\_FLAG\_BUDDY\_IS\_PET        |
| 64  | 0x40 | SCRIPT\_FLAG\_BUDDY\_IS\_DESPAWNED  |
| 128 | 0x80 | SCRIPT\_FLAG\_BUDDY\_BY\_POOL       |

#### OtherFields

Depending on what [command](dbscripts#command) was used, the meaning and use for the following fields varies.

-   **SCRIPT\_COMMAND\_TALK = 0**
    -   All information of the text (type, language, associated sound, emote) is stored in the [dbscript\_string.](dbscript_string) table
    -   datalong: [dbscript\_random\_templates.id](dbscript_random_templates#id) - will randomize between all dbscript\_strings in given template.
    -   dataint - 4: The text ID that the creature will say. See [dbscript\_string.](dbscript_string). ID must be between 2000000000 and 2000010000. In case more then only dataint field is filled the texts will be used randomly.

<!-- -->
-   **SCRIPT\_COMMAND\_EMOTE = 1**
    -   datalong: The [emote ID](Emote) to play.
    -   dataint1-dataint4 optionally, for random selection of emote
    -   Resulting source must be a unit.

<!-- -->
-   **SCRIPT\_COMMAND\_FIELD\_SET = 2**
    -   datalong: Index of the field.
    -   datalong2: Value to place at the index.

<!-- -->
-   **SCRIPT\_COMMAND\_MOVE\_TO = 3**
    -   datalong2: Length of the motion. This calculates as travel\_speed\*100. Use 0 for creature default movement.
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL will teleport the creature to the given location.
    -   x: X position to move to.
    -   y: Y position to move to.
    -   z: Z position to move to.
    -   o: Orientation to face.
    -   Resulting source must be a creature.
        *Side note: If position is very near to current position, or x=y=z=0, then only orientation is changed.*

<!-- -->
-   **SCRIPT\_COMMAND\_FLAG\_SET = 4**
    -   datalong: Field index to be set.
    -   datalong2: Flag bit(s) to set.

| FIELD TO MODIFY    | HEX VALUES      | DECIMAL INDEX VALUE | COMMENTS                                          |
| ------------------ | --------------- | ------------------- | ------------------------------------------------- |
| UNIT_FIELD_FLAGS   | 0x0006 + 0x0028 | 46-TBC 59-WOTLK     | Modify UnitFlags for NPC (Source Must Be Unit)    |
| UNIT_DYNAMIC_FLAGS | 0x0006 + 0x009E | 164-TBC 78-WOTLK    | Modify DynamicFlags for NPC (Source Must Be Unit) |
| UNIT_NPC_FLAGS     | 0x0006 + 0x00A2 | 168-TBC 82-WOTLK    | Modify NPCFlags for NPC (Source Must Be Unit)     |

More Examples Can Be Found At: UpdateFields.h In Core

-   **SCRIPT\_COMMAND\_FLAG\_REMOVE = 5**
    -   datalong: Field index to be unset.
    -   datalong2: Flag bit(s) to unset.

<!-- -->
-   **SCRIPT\_COMMAND\_TELEPORT\_TO = 6**
    -   datalong: Target Map ID. See [Map.dbc](Map.dbc).
    -   x: Teleport target x coordinate.
    -   y: Teleport target y coordinate.
    -   z: Teleport target z coordinate.
    -   o: Teleport target orientation.
    -   The source or target must be a player.

<!-- -->
-   **SCRIPT\_COMMAND\_QUEST\_EXPLORED = 7**
    -   datalong: [Quest ID](quest_template#entry) whose external status should be satisfied.
    -   datalong2: Distance away from the NPC/object that the player can be and have the script still take effect.
    -   The source or target must be a player.

<!-- -->
-   **SCRIPT\_COMMAND\_KILL\_CREDIT = 8**
    -   datalong: Kill credit entry for quest (entry in quest\_template.ReqCreatureOrGOId). If set to 0 then the creature source or target will be used.
    -   datalong2: Can be 0 = personal credit or 1 = group credit.
    -   The source or target must be a player.

<!-- -->
-   **SCRIPT\_COMMAND\_RESPAWN\_GAMEOBJECT = 9**
    -   datalong: Guid of the gameobject to respawn. See [gameobject.guid](gameobject#guid). Can be skipped for buddy.
    -   datalong2: Despawn time in seconds. If the value is < 5 seconds then 5 seconds is used instead.

<!-- -->
-   **SCRIPT\_COMMAND\_TEMP\_SPAWN\_CREATURE = 10**
    -   datalong: Entry of the summoned creature from [creature\_template.entry](creature_template#entry).
    -   datalong2: Despawn time (MILLIESECONDS). If set to 0 then the creature will be despawned only when killed.
    -   datalong3: The [pathId](creature_movement_template#pathId) you want the creature to immediately start moving on (if MovementType=2)
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL will summon the creature as active object.
    -   dataint: SetRun (bool). 0 = off (default), 1 = on
    -   dataint2 = factionId - if 0 is set, faction is from DB entry
    -   dataint3 = modelId - if 0 is set, model is from DB entry
    -   x: Summon target x coordinate.
    -   y: Summon target y coordinate.
    -   z: Summon target z coordinate.
    -   o: Summon target orientation.

<!-- -->
-   **SCRIPT\_COMMAND\_OPEN\_DOOR = 11**
    -   datalong: Guid of the activated door. It's a [gameobject.guid](gameobject#guid). Can be skipped for buddy.
    -   datalong2: Delay before closing again the door. If the value is < 15 seconds then 15 seconds is used instead.

<!-- -->
-   **SCRIPT\_COMMAND\_CLOSE\_DOOR = 12**
    -   datalong: Guid of the activated door. It's a [gameobject.guid](gameobject#guid). Can be skipped for buddy.
    -   datalong2: Delay before opening again the door. If the value is < 15 seconds then 15 is used instead.

<!-- -->
-   **SCRIPT\_COMMAND\_ACTIVATE\_OBJECT = 13**
    -   The source must be a unit and the target a gameobject.

<!-- -->
-   **SCRIPT\_COMMAND\_REMOVE\_AURA = 14**
    -   datalong: [Spell ID](spell_template#Id).
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL will remove aura from the source only for the target unit.

<!-- -->
-   **SCRIPT\_COMMAND\_CAST\_SPELL = 15**
    -   datalong: [Spell ID](spell_template#Id).
    -   datalong2: [TriggerCastFlags](dbscripts#TriggerCastFlags)
    -   buddy\_entry: [entry](creature_template#entry) of the target
    -   search\_radius: radius to search for [buddy\_entry](dbscripts#buddy_entry) or [guid](creature#guid) of the specific guid if [data\_flags](dbscripts#data_flags%7C16) is set
    -   dataint1-dataint4 optional. If some of these are set to a spell id, a random spell out of datalong, datint1, ..,dataintX is cast.

#### TriggerCastFlags

| Bit | Name                               | Description                                                                     |
| --- | ---------------------------------- | ------------------------------------------------------------------------------- |
| 0   | TRIGGERED_NONE                     | Not Triggered                                                                   |
| 1   | TRIGGERED_OLD_TRIGGERED            | Legacy bool support TODO: Restrict usage as much as possible.                   |
| 2   | TRIGGERED_IGNORE_HIT_CALCULATION   | Will ignore calculating hit in SpellHitResult                                   |
| 4   | TRIGGERED_IGNORE_UNSELECTABLE_FLAG | Ignores UNIT_FLAG_NOT_SELECTABLE in CheckTarget                                 |
| 8   | TRIGGERED_INSTANT_CAST             | Will ignore any cast time set in spell entry                                    |
| 16  | TRIGGERED_AUTOREPEAT               | Will signal spell system that this is internal autorepeat call                  |
| 32  | TRIGGERED_IGNORE_UNATTACKABLE_FLAG | Ignores UNIT_FLAG_NOT_ATTACKABLE in CheckTarget                                 |
| 64  | TRIGGERED_DO_NOT_PROC              | Spells from scripts should not proc - DBScripts for example                     |
| 128 | TRIGGERED_PET_CAST                 | Spell that should report error through pet opcode                               |
| 256 | TRIGGERED_NORMAL_COMBAT_CAST       | AI needs to be notified about change of target TODO: change into TRIGGERED_NONE |

-   **SCRIPT\_COMMAND\_PLAY\_SOUND = 16**
    -   datalong: [Sound ID](SoundEntries.dbc#Content).
    -   datalong2: bitmask: 0/1=anyone/target, 0/2=with distance dependent, 0/4=map wide, 0/8=zone wide; 1|2 = 3 is target with distance dependent.
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL: play music instead of sound
    -   Source may be any object. Target may be any player.

<!-- -->
-   **SCRIPT\_COMMAND\_CREATE\_ITEM = 17**
    -   datalong: [Item entry](item_template#Content).
    -   datalong2: Amount.
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL: remove the item from player by the given amount
    -   Source or target must be a player.

<!-- -->
-   **SCRIPT\_COMMAND\_DESPAWN\_SELF = 18**
    -   datalong: Despawn delay (MILLIESECONDS).
    -   Resulting source must be a creature.
    -   Despawns the target.

<!-- -->
-   **SCRIPT\_COMMAND\_PLAY\_MOVIE = 19**
    -   datalong: Plays a [movie\_id](Movie.dbc#Content) to the target player.
    -   Target must be a player.

<!-- -->
-   **SCRIPT\_COMMAND\_MOVEMENT = 20**
    -   datalong: Change the [MovementType](creature_template#MovementType) of a creature. Possible values: 0 = Idle, 1 = Random Movement, 2 = Waypoint Movement.
    -   datalong2: Wander distance (for random movement), [creature\_movement\_template.pathId](creature_movement_template#pathId) (for waypoint movement).
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL will set random movement around the current position.
    -   Resulting source must be a creature.

<!-- -->
-   **SCRIPT\_COMMAND\_SET\_ACTIVEOBJECT = 21**
    -   datalong: Can be defined as 1 = On or 0 = Off. Set a creature as active object, depending on the datalong value.
    -   Resulting source must be creature.

<!-- -->
-   **SCRIPT\_COMMAND\_SET\_FACTION = 22**
    -   datalong: [Faction Id](FactionTemplate.dbc). If set to 0 will restore original faction from creature\_template.
    -   Resulting source must be a creature.
    -   datalong2: Temporary faction flags

| Bit | Hex  | Description                             |
|-----|------|-----------------------------------------|
| 0   | 0x00 | TEMPFACTION\_NONE                       |
| 1   | 0x01 | TEMPFACTION\_RESTORE\_RESPAWN           |
| 2   | 0x02 | TEMPFACTION\_RESTORE\_COMBAT\_STOP      |
| 4   | 0x04 | TEMPFACTION\_RESTORE\_REACH\_HOME       |
| 8   | 0x08 | TEMPFACTION\_TOGGLE\_NON\_ATTACKABLE    |
| 16  | 0x10 | TEMPFACTION\_TOGGLE\_IMMUNE\_TO\_PLAYER |
| 32  | 0x20 | TEMPFACTION\_TOGGLE\_IMMUNE\_TO\_NPC    |
| 64  | 0x40 | TEMPFACTION\_TOGGLE\_PACIFIED           |
| 128 | 0x80 | TEMPFACTION\_TOGGLE\_NOT\_SELECTABLE    |

-   **SCRIPT\_COMMAND\_MORPH\_TO\_ENTRY\_OR\_MODEL = 23**
    -   datalong: Creature [entry](creature_template#entry) or [model\_id](creature_template#modelid) (depending on [data\_flags](dbscripts#data_flags)). If set to 0 then the creature will demorph.
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL to use datalong value as model\_id explicit.
    -   Resulting source must be a creature.

<!-- -->
-   **SCRIPT\_COMMAND\_MOUNT\_TO\_ENTRY\_OR\_MODEL = 24**
    -   datalong: Creature [entry](creature_template#entry) or [model\_id](creature_template#modelid) (depending on [data\_flags](dbscripts#data_flags)). If set to 0 then the creature will dismount.
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL to use datalong value as model\_id explicit.
    -   Resulting source must be creature.

<!-- -->
-   **SCRIPT\_COMMAND\_SET\_RUN = 25**
    -   datalong: Set run to 1 = On or 0 = Off
    -   Resulting source must be a creature.

<!-- -->
-   **SCRIPT\_COMMAND\_ATTACK\_START = 26**
    -   Resulting source must be a creature and resulting target must be a unit.

<!-- -->
-   **SCRIPT\_COMMAND\_GO\_LOCK\_STATE = 27**
    -   Resulting source must be gameobject.
    -   datalong:

| Bit | Hex  | Name                  |
|-----|------|-----------------------|
| 1   | 0x01 | flag\_go\_lock        |
| 2   | 0x02 | flag\_go\_unlock      |
| 4   | 0x04 | flag\_go\_nonInteract |
| 8   | 0x08 | flag\_go\_interact    |

-   **SCRIPT\_COMMAND\_STAND\_STATE = 28**
    -   Resulting source must be a creature.
    -   datalong: stand state (enum UnitStandStateType)

| Bit | Name                              | Comment                                                             |
| --- | --------------------------------- | ------------------------------------------------------------------- |
| 0   | UNIT_STAND_STATE_STAND            | normal behavior                                                     |
| 1   | UNIT_STAND_STATE_SIT              | sitting on ground                                                   |
| 2   | UNIT_STAND_STATE_SIT_CHAIR        | sitting on normal chair                                             |
| 3   | UNIT_STAND_STATE_SLEEP            | sleeping                                                            |
| 4   | UNIT_STAND_STATE_SIT_LOW_CHAIR    | sitting on low chair                                                |
| 5   | UNIT_STAND_STATE_SIT_MEDIUM_CHAIR | sitting on medium chair                                             |
| 6   | UNIT_STAND_STATE_SIT_HIGH_CHAIR   | sitting on high chair                                               |
| 7   | UNIT_STAND_STATE_DEAD             | play dead                                                           |
| 8   | UNIT_STAND_STATE_KNEEL            | kneel                                                               |
| 9   | UNIT_STAND_STATE_CUSTOM           | Depends on model animation. Submerge, freeze, hide, hibernate, rest |

-   **SCRIPT\_COMMAND\_MODIFY\_NPC\_FLAGS = 29**
    -   Resulting source must be a creature.
    -   datalong: NPC Flags
    -   datalong2:

| Hex  | Action |
|------|--------|
| 0x00 | Toggle |
| 0x01 | Add    |
| 0x02 | Remove |

-   **SCRIPT\_COMMAND\_SEND\_TAXY\_PATH = 30**
    -   datalong: [Taxi path id](TaxiPath.dbc#Content).
    -   Source or target must be a player.

<!-- -->
-   **SCRIPT\_COMMAND\_TERMINATE\_SCRIPT = 31**
    -   datalong: [Creature entry](creature_template#entry) if provided. (Or pool ID if SCRIPT\_FLAG\_BUDDY\_BY\_POOL)
    -   datalong2: Search distance.
    -   dataint: Change of [waittime](creature_movement#waittime) (MILLIESECONDS) of a current waypoint movement type. Negative values will decrease time.
    -   [data\_flags](dbscripts#data_flags)

| &amp; data_flags                            | Description                                              |
| ------------------------------------------- | -------------------------------------------------------- |
| &amp; SCRIPT_FLAG_COMMAND_ADDITIONAL 8 0x08 | If creature is found and alive, terminate script.        |
| ! SCRIPT_FLAG_COMMAND_ADDITIONAL            | If creature is not found or not alive, terminate script. |

-   **SCRIPT\_COMMAND\_PAUSE\_WAYPOINTS = 32**
    -   datalong: 1 = Pause or 0 = Unpause waypoint movement.
    -   Resulting source or target must be a creature.

<!-- -->
-   **SCRIPT\_COMMAND\_XP\_USER = 33**
    -   datalong: Set experience gain to 1 = On or 0 = Off
    -   Source or target must be a player.
        *Side note: Only available on wotlk version.*

<!-- -->
-   **SCRIPT\_COMMAND\_TERMINATE\_CONDITION = 34**
    -   datalong: [Condition entry](conditions#condition_entry) to check.
    -   datalong2: [Quest entry](quest_template#entry) to mark as failed for the player (if provided).
    -   [data\_flags](dbscripts#data_flags)

| &amp; data_flags                            | Description                        |
| ------------------------------------------- | ---------------------------------- |
| &amp; SCRIPT_FLAG_COMMAND_ADDITIONAL 8 0x08 | Terminate when condition is false. |
| ! SCRIPT_FLAG_COMMAND_ADDITIONAL            | Terminate when condition is true.  |

-   **SCRIPT\_COMMAND\_SEND\_AI\_EVENT = 35**
    -   datalong: AI event id. Only EventAI events are accepted. Supported types see CreatureAI.h enum AIEventType.
    -   datalong2: Radius. If radius isn't provided and the target is a creature, then send AIEvent to target.
    -   Source and target must be a creature.

<!-- -->
-   **SCRIPT\_COMMAND\_SET\_FACING = 36**
    -   Resulting source must be a creature; Resulting target must be a Worldobject.
    -   datalong != 0 Reset orientation

<!-- -->
-   **SCRIPT\_COMMAND\_MOVE\_DYNAMIC = 37**
    -   Resulting source must be a creature; Resulting target must be a Worldobject.
    -   datalong = 0: Move resulting source towards resulting target
    -   datalong != 0: Move resulting source to a random point between datalong2..datalong around resulting target.
    -   orientation != 0: Obtain a random point around resulting target in direction of orientation
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL Obtain a point in direction of resulting target -> GetOrientation + orientation
    -   for resulting target resulting source and orientation 0 this will mean resulting source moving forward

<!-- -->
-   **SCRIPT\_COMMAND\_SEND\_MAIL = 38**
    -   Resulting source should be a Creature OR NULL. Resulting target must be Player
    -   datalong = mailTemplateId
    -   datalong2: AlternativeSenderEntry. Use as sender-Entry of the sent mail
    -   dataint1: Delay (>= 0) in Seconds

<!-- -->
-   **SCRIPT\_COMMAND\_SET\_FLY = 39**
    -   Resulting source must be a creature.
    -   datalong = bool 0=off, 1=on
    -   [data\_flags](dbscripts#data_flags) & SCRIPT\_FLAG\_COMMAND\_ADDITIONAL set/unset byte flag UNIT\_BYTE1\_FLAG\_FLY\_ANIM

<!-- -->
-   **SCRIPT\_COMMAND\_DESPAWN\_GO = 40**
    -   Resulting target must be a Gameobject. Please note that not all gameobject types support this command.

<!-- -->
-   **SCRIPT\_COMMAND\_RESPAWN = 41**
    -   resultingSource = Creature. Requires SCRIPT\_FLAG\_BUDDY\_IS\_DESPAWNED to find dead or despawned targets

<!-- -->
-   **SCRIPT\_COMMAND\_SET\_EQUIPMENT\_SLOTS = 42**
    -   Resulting source must be a creature.
    -   datalong = resetDefault: bool 0=false, 1=true
    -   dataint = main hand slot; dataint2 = off hand slot; dataint3 = ranged slot

<!-- -->
-   **SCRIPT\_COMMAND\_RESET\_GO = 43**
    -   Resulting target must be a Gameobject. Only works for Gameobject which are doors or buttons (GO type 0 and 1)

<!-- -->
-   **SCRIPT\_COMMAND\_UPDATE\_TEMPLATE = 44**
    -   Resulting source must be a Creature.
    -   datalong = new creature entry. Must be different than the current one
    -   datalong2 = faction for which the entry is updated. 0 = Alliance, 1 = Horde. No other values are allowed

<!-- -->
-   **SCRIPT\_COMMAND\_START\_RELAY\_SCRIPT= 45**
    -   Resulting source must be a Unit. Target is not mandatory.
    -   datalong = dbscripts\_on\_relay Id which should be launched
    -   datalong2 = dbscript\_random\_template relay Id which should be launched. Takes precedence over relay Id.

<!-- -->
-   **SCRIPT\_COMMAND\_CAST\_CUSTOM\_SPELL= 46**
    -   Resulting source must be a Unit. Target is Unit.
    -   datalong = spellid
    -   datalong2 = castFlags, enum [TriggerCastFlags](dbscripts#TriggerCastFlags)
    -   dataint1-3 define the &bp value for the spell. At least one field is required.
