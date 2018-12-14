Back to [world database](mangosdb_struct) list of tables.

The \`npc\_gossip\` table
-------------------------

------------------------------------------------------------------------

**THIS TABLE IS OUTDATED. DO NOT USE**
**It should have been removed around 2009, but for some bad reasons it wasn't..**

Use table [gossip\_menu](gossip_menu) instead.

------------------------------------------------------------------------

This table is the link between NPCs and gossip text. When you click on an NPC that says something more than just "Greetings ", this is the table that links that NPC to the text.

### Structure

| **Field**                        | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------|------------------|----------|---------|-------------|-----------|
| [npc\_guid](Npc_gossip#npc_guid) | int(11) unsigned | NO       | PRI     | 0           |           |
| [textid](Npc_gossip#textid)      | int(11) unsigned | NO       |         | 0           |           |
|                                  |                  |

### Description of the fields

#### npc\_guid

You place the GUID from [creature.guid](creature#guid) in this field for the NPC that you want to have gossip.

#### textid

This is the ID from [npc\_text.ID](npc_text#ID) of the text that you want the NPC to say.

Now, to get your NPC to actually say something, you need to update [creature\_template.npcflag](creature_template#npcflag) with the gossip flag, which is 1.
