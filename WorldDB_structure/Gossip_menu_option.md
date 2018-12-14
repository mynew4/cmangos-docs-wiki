Back to [world database](mangosdb_struct) list of tables.

The \`gossip\_menu\_option\` table
----------------------------------

This table holds infos about menu options a gossip NPC can have. Examples of options : "Train me!", "I want to unlearn my talents", ...

### Structure

| **Field**                                                     | **Type**     | **Attributes** | **Key** | **Null** | **Default** |
|---------------------------------------------------------------|--------------|----------------|---------|----------|-------------|
| [menu\_id](Gossip_menu_option#menu_id)                        | smallint(6)  | unsigned       | PRI     | NO       | 0           |
| [id](Gossip_menu_option#id)                                   | smallint(6)  | unsigned       | PRI     | NO       | 0           |
| [option\_icon](Gossip_menu_option#option_icon)                | smallint(6)  | unsigned       | PRI     | NO       | 0           |
| [option\_text](Gossip_menu_option#option_text)                | text         | signed         |         | YES      | NULL        |
| [option\_id](Gossip_menu_option#option_id)                    | tinyint(3)   | unsigned       |         | NO       | 0           |
| [npc\_option\_npcflag](Gossip_menu_option#npc_option_npcflag) | int(10)      | unsigned       |         | NO       | 0           |
| [action\_menu\_id](Gossip_menu_option#action_menu_id)         | mediumint(8) | unsigned       |         | NO       | 0           |
| [action\_poi\_id](Gossip_menu_option#action_poi_id)           | mediumint(8) | unsigned       |         | NO       | 0           |
| [action\_script\_id](Gossip_menu_option#action_script_id)     | mediumint(8) | unsigned       |         | NO       | 0           |
| [box\_coded](Gossip_menu_option#box_coded)                    | tinyint(3)   | unsigned       |         | NO       | 0           |
| [box\_money](Gossip_menu_option#box_money)                    | int(11)      | unsigned       |         | NO       | 0           |
| [box\_text](Gossip_menu_option#box_text)                      | text         | signed         |         | YES      | NULL        |
| [condition\_id](Gossip_menu_option#condition_id)              | mediumint(8) | unsigned       |         | NO       | 0           |

### Description of the fields

#### menu\_id

Gossip entry from [Gossip\_menu.entry](Gossip_menu#entry) this option is associated with.

#### id

The id associated with this gossip\_menu\_option. Must be unique for a given menu\_id

#### option\_icon

| Value | ICON Name                 | description                       |
|-------|---------------------------|-----------------------------------|
| 0     | GOSSIP\_ICON\_CHAT        | white chat bubble                 |
| 1     | GOSSIP\_ICON\_VENDOR      | brown bag                         |
| 2     | GOSSIP\_ICON\_TAXI        | flight                            |
| 3     | GOSSIP\_ICON\_TRAINER     | book                              |
| 4     | GOSSIP\_ICON\_INTERACT\_1 | interaction wheel                 |
| 5     | GOSSIP\_ICON\_INTERACT\_2 | interaction wheel                 |
| 6     | GOSSIP\_ICON\_MONEY\_BAG  | brown bag with yellow dot         |
| 7     | GOSSIP\_ICON\_TALK        | white chat bubble with black dots |
| 8     | GOSSIP\_ICON\_TABARD      | tabard                            |
| 9     | GOSSIP\_ICON\_BATTLE      | two swords                        |
| 10    | GOSSIP\_ICON\_DOT         | yellow dot                        |

#### option\_text

This is is the text that you want displayed for this option. Examples would be "Train Me!" "Get off my lawn", "Learn Dual Spec".

#### option\_id

| option\_id | Option name                       | npc\_option\_npcflag |
|------------|-----------------------------------|----------------------|
| 0          | GOSSIP\_OPTION\_NONE              | 0                    |
| 1          | GOSSIP\_OPTION\_GOSSIP            | 1                    |
| 2          | GOSSIP\_OPTION\_QUESTGIVER        | 2                    |
| 3          | GOSSIP\_OPTION\_VENDOR            | 128                  |
| 4          | GOSSIP\_OPTION\_TAXIVENDOR        | 8192                 |
| 5          | GOSSIP\_OPTION\_TRAINER           | 16                   |
| 6          | GOSSIP\_OPTION\_SPIRITHEALER      | 16384                |
| 7          | GOSSIP\_OPTION\_SPIRITGUIDE       | 32768                |
| 8          | GOSSIP\_OPTION\_INNKEEPER         | 65536                |
| 9          | GOSSIP\_OPTION\_BANKER            | 131072               |
| 10         | GOSSIP\_OPTION\_PETITIONER        | 262144               |
| 11         | GOSSIP\_OPTION\_TABARDDESIGNER    | 524288               |
| 12         | GOSSIP\_OPTION\_BATTLEFIELD       | 1048576              |
| 13         | GOSSIP\_OPTION\_AUCTIONEER        | 2097152              |
| 14         | GOSSIP\_OPTION\_STABLEPET         | 4194304              |
| 15         | GOSSIP\_OPTION\_ARMORER           | 4096                 |
| 16         | GOSSIP\_OPTION\_UNLEARNTALENTS    | 16\*                 |
| 17         | GOSSIP\_OPTION\_UNLEARNPETTALENTS | 16\*                 |
| 18         | GOSSIP\_OPTION\_LEARNDUALSPEC     | 16\*                 |

`*   bonus option for GOSSIP_OPTION_TRAINER` `NOTE: For NPC you must be combinate option_id and npc_option_npcflag, you also need the npc_flag in creature_template`

#### npc\_option\_npcflag

This is the npcflag that the NPC must have to have this option display. See [option\_id](#option_id)

#### action\_menu\_id

If you want to create a sub-menu, this is the ID to link to create that sub-menu.
This sub-menu will be displayed when you click on the current menu.

NOTE: If you want gossip window to close when selecting this gossip option use -1 for this value.

#### action\_poi\_id

If you want a POI (point of interest) to display on the minimap, this is the \`entry\` from \`points\_of\_interest\`

#### action\_script\_id

The ID from the \`dbscripts\_on\_gossip\` table if this gossip option has a script.

#### box\_coded

If you want a box to display where you have to enter a code, this is the field you use. I have no clue how it works, will have to look at the code...

#### box\_money

Money asked (in copper).

#### box\_text

Confirmation text before activating the gossip.

#### condition\_id

If set the option will only be displayed if the condition linked to [condition\_id](conditions) fits
