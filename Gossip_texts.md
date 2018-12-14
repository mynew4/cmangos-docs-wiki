Back to [world database](mangosdb_struct) list of tables.

The \`gossip\_texts\` table
---------------------------

This table stores gossip texts used in ScriptDevAI, for normal gossip implementation see [Gossip\_menu](Gossip_menu) and [npc\_text](npc_text).

### Structure

| **Field**                                        | **Type**     | **Attributes** | **Key** | **Null** | **Default** |
|--------------------------------------------------|--------------|----------------|---------|----------|-------------|
| [entry](Gossip_texts#entry)                      | mediumint(8) | unsigned       | PRI     | NO       | 0           |
| [content\_default](Gossip_texts#content_default) | text         | signed         |         | YES      | NULL        |
| [content\_loc1](Gossip_texts#content_locX)       | text         | signed         |         | NO       | NULL        |
| [content\_loc2](Gossip_texts#content_locX)       | text         | signed         |         | NO       | NULL        |
| [content\_loc3](Gossip_texts#content_locX)       | text         | signed         |         | NO       | NULL        |
| [content\_loc4](Gossip_texts#content_locX)       | text         | signed         |         | NO       | NULL        |
| [content\_loc5](Gossip_texts#content_locX)       | text         | signed         |         | NO       | NULL        |
| [content\_loc6](Gossip_texts#content_locX)       | text         | signed         |         | NO       | NULL        |
| [content\_loc7](Gossip_texts#content_locX)       | text         | signed         |         | NO       | NULL        |
| [content\_loc8](Gossip_texts#content_locX)       | text         | signed         |         | NO       | NULL        |
| [comment](Gossip_texts#comment)                  | text         | signed         |         | NO       | NULL        |

### Description of the fields

#### entry

ID of the text. This has the be negative and in the range ~~3000000~~&gt; -3999999.

#### content\_default

The text shown if no localized text is available?

#### content\_locX

Localized texts. See [Localization\_lang](Localization_lang)

#### comment
