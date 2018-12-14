Back to [world database](mangosdb_struct) list of tables.

The \`creature\_involvedrelation\` table
----------------------------------------

Holds NPC quest ender relations on which NPCs finishes which quests.

### Structure

| **Field**                                | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [id](Creature_involvedrelation#id)       | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [quest](Creature_involvedrelation#quest) | mediumint(8) unsigned | NO       | PRI     | 0           |           |

### Description of the fields

#### id

The ID of the creature. See [creature\_template.entry](creature_template#entry)

#### quest

The quest ID that the creature finishes. See [quest\_template.entry](quest_template#entry)
