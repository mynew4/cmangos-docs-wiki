Back to [world database](mangosdb_struct) list of tables.

The \`areatrigger\_teleport\` table
-----------------------------------

Contains all the teleport triggers definition. This table is used to complete .dbc file information.

### Structure

| **Field**                                                                        | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [id](Areatrigger_teleport#id)                                                    | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [name](Areatrigger_teleport#name)                                                | text                  | YES      |         |             |           |
| [required\_level](Areatrigger_teleport#required_level)                           | tinyint(3) unsigned   | NO       |         | 0           |           |
| [required\_item](Areatrigger_teleport#required_item)                             | mediumint(8) unsigned | NO       |         | 0           |           |
| [required\_item2](Areatrigger_teleport#required_item)                            | mediumint(8) unsigned | NO       |         | 0           |           |
| [heroic\_key](Areatrigger_teleport#heroic_key)                                   | mediumint(8) unsigned | NO       |         | 0           |           |
| [heroic\_key2](Areatrigger_teleport#heroic_key)                                  | mediumint(8) unsigned | NO       |         | 0           |           |
| [required\_quest\_done](Areatrigger_teleport#required_quest_done)                | int(11) unsigned      | NO       |         | 0           |           |
| [required\_quest\_done\_heroic](Areatrigger_teleport#required_quest_done_heroic) | int(11) unsigned      | NO       |         | 0           |           |
| [required\_failed\_text](Areatrigger_teleport#required_failed_text)              | text                  | YES      |         |             |           |
| [target\_map](Areatrigger_teleport#target_map)                                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [target\_position\_x](Areatrigger_teleport#target_position_x)                    | float                 | NO       |         | 0           |           |
| [target\_position\_y](Areatrigger_teleport#target_position_y)                    | float                 | NO       |         | 0           |           |
| [target\_position\_z](Areatrigger_teleport#target_position_z)                    | float                 | NO       |         | 0           |           |
| [target\_orientation](Areatrigger_teleport#target_orientation)                   | float                 | NO       |         | 0           |           |
| [condition\_id](Areatrigger_teleport#condition_id)                               | int(11) unsigned      | NO       |         | 0           |           |

### Description of the fields

#### id

This is the trigger identifier, it must match with the one from AreaTrigger.dbc

#### name

Name of the trigger. This can be an arbitrary name, and is for descriptive purposes only.

#### required\_level

Level necessary to activate this trigger

#### required\_item

The necessary item(s) to activate this trigger (see [item\_template.entry](item_template#entry))

#### heroic\_key

The key that unlocks heroic version for a trigger leading to an instatiable map with heroic mode support. If two are specified, you only need one to activate heroic mode.

#### required\_quest\_done

Required quest done as attunement to use the trigger (see [quest\_template.entry](quest_template#entry)).

#### required\_quest\_done\_heroic

Required Heroic quest done as attunement to use the trigger (see [quest\_template.entry](quest_template#entry)).

#### required\_failed\_text

Failed text shown to players who do have not done the attunement quest yet.

#### target\_map

Target map of the trigger (See [Map.dbc](Map.dbc))

#### target\_position\_x

X coordinate for the target destination of the trigger

#### target\_position\_y

Y coordinate for the target destination of the trigger

#### target\_position\_z

Z coordinate for the target destination of the trigger

#### target\_orientation

Orientation the player will get when appearing at this location

#### condition\_id

Necessary conditions to trigger the teleport
Note: Use the condition ID only as a last measure. The other columns have associated errors, while this one does not.
