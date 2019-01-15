Back to [world database](mangosdb_struct) list of tables.

The \`gossip\_menu\` table
--------------------------

This table is used for displaying gossip when a player talks to an NPC.

### Structure

| **Field**                                 | **Type**     | **Attributes** | **Key** | **Null** | **Default** |
|-------------------------------------------|--------------|----------------|---------|----------|-------------|
| [entry](Gossip_menu#entry)                | smallint(6)  | unsigned       | PRI     | NO       | 0           |
| [text\_id](Gossip_menu#text_id)           | mediumint(8) | unsigned       | PRI     | NO       | 0           |
| [script\_id](Gossip_menu#script_id)       | mediumint(8) | unsigned       |         | NO       | 0           |
| [condition\_id](Gossip_menu#condition_id) | mediumint(8) | unsigned       |         | NO       | 0           |

### Description of the fields

#### entry

Gossip ID from [gossip\_menu\_id](creature_template#gossip_menu_id) and [gameobject\_template.GAMEOBJECT\_TYPE\_QUESTGIVER.data3](gameobject_template#data0-23)

#### text\_id

Reference to [npc\_text.id](npc_text#ID).

#### script\_id

If set a DBScript with this ID will be started of the selected text<br>
NOTE: Called when menu shown (not when clicked)<br>
[dbscripts\_on\_gossip](DBScripts)

#### condition\_id

[condition\_id](conditions)<br>
If the gossip\_menu has more than one text with true conditions, then the text with highest condition\_id will be shown.
