Back to [world database](mangosdb_struct) list of tables.

The \`creature\_model\_info\` table
-----------------------------------

This table contains all models of mobs, their gender and other information that are model related. This means that when a creature uses another model, this information will change as well.

### Structure

| **Field**                                                          | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [modelid](Creature_model_info#modelid)                             | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [bounding\_radius](Creature_model_info#bounding_radius)            | float                 | NO       |         | 0           |           |
| [combat\_reach](Creature_model_info#combat_reach)                  | float                 | NO       |         | 0           |           |
| [SpeedWalk](Creature_model_info#SpeedWalk)                         | float                 | NO       |         | 1           |           |
| [SpeedRun](Creature_model_info#SpeedRun)                           | float                 | NO       |         | 1.14286     |           |
| [gender](Creature_model_info#gender)                               | tinyint(3) unsigned   | NO       |         | 2           |           |
| [modelid\_other\_gender](Creature_model_info#modelid_other_gender) | mediumint(8) unsigned | NO       |         | 0           |           |
| [modelid\_alternative](Creature_model_info#modelid_alternative)    | mediumint(8) unsigned | NO       |         | 0           |           |

### Description of the fields

#### modelid

Display ID from CreatureDisplayInfo.dbc

#### bounding\_radius

A field scaled with size.
Might or might not have any relation to some radius of a bowl enclosing the creature.
Currently badly used in the above suggested way in some cases, which is false in general.

#### combat\_reach

This is an additional distance that is added to range of attacks (both melee and spells) to check if an attack can reach the enemy.

#### SpeedWalk

This Field Controls How Fast An NPC Moves When Walking. This speed can be overridden by setting another value in [creature\_template.SpeedWalk](creature_template#SpeedWalk).

This Value Comes From Sniff Packet Data.

Divide sniffed value with 2.5.
Example: Sniffed WalkSpeed for a specific creature is 5. Divide it by 2.5 to get our DB value.
5/2.5=2

(Default Value Is: 1)

#### SpeedRun

This Field Controls How Fast An NPC Moves When Running. This speed can be overridden by setting another value in [creature\_template.SpeedRun](creature_template#SpeedRun).

This Value Comes From Sniff Packet Data.

Divide sniffed value with 7.
Example: Sniffed RunSpeed for a specific creature is 10. Divide it by 7 to get our DB value.
10/7=1,42857

(Default Value Is: 1.14286)

#### gender

Gender of the creature

-   0: Male
-   1: Female
-   2: None

#### modelid\_other\_gender

Point to [Creature\_model\_info.modelid](Creature_model_info#modelid). When the entry is gender male (0) or female (1), this value can point to the display id of the other gender.

### modelid\_alternative

Alternative to the current model.
