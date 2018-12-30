Back to [world database](mangosdb_struct) list of tables.

The \`creature\_battleground\` table
------------------------------------

This table contains the description of creatures spawned on battlegrounds.

### Structure

| **Field**                              | **Type**            | **Null** | **Key** | **Default** |
|----------------------------------------|---------------------|----------|---------|-------------|
| [guid](Creature_battleground#guid)     | int(10) unsigned    | NO       | PRI     | NULL        |
| [event1](Creature_battleground#event1) | tinyint(3) unsigned | NO       |         | NULL        |
| [event2](Creature_battleground#event2) | tinyint(3) unsigned | NO       |         | NULL        |

### Description of the fields

#### guid

A unique identifier given to each creature to distinguish one creature from another. Two creatures can NOT have same GUID. This GUID is linked to the creature-table.

#### event1

main event

#### event2

sub event
