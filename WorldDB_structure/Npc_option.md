Back to [world database](mangosdb_struct) list of tables.

The \`npc\_option\` table
-------------------------

This table holds info about how gossip menus are presented to you. It also contains default gossip for option menus.

### Structure

| **Field**                              | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------|------------------|----------|---------|-------------|-----------|
| [id](Npc_option#id)                    | int(10) unsigned | NO       | PRI     | 0           |           |
| [gossip\_id](Npc_option#gossip_id)     | int(10) unsigned | NO       |         | 0           |           |
| [npcflag](Npc_option#npcflag)          | int(10) unsigned | NO       |         | 0           |           |
| [icon](Npc_option#icon)                | int(10) unsigned | NO       |         | 0           |           |
| [action](Npc_option#action)            | int(10) unsigned | NO       |         | 0           |           |
| [option\_text](Npc_option#option_text) | text             | YES      |         |             |           |

### Description of the fields

#### id

An arbitrary number that is not associated with any other table.

#### gossip\_id

Link to parent [npc\_option.id](npc_option#id).

#### npcflag

This the is the [creature\_template.npcflag](creature_template#npcflag) that is associated with this option.

#### icon

This is the icon that is displayed next to the option in the gossip menu.

#### action

The action to perform. (paste section of code that lists this)

#### option\_text

The text for this particular option
