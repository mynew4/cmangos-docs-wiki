Back to [world database](mangosdb_struct) list of tables.

The \`creature\_questrelation\` table
-------------------------------------

Holds NPC quest giver relations on which NPCs start which quests.

### Structure

| **Field**                             | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [id](Creature_questrelation#id)       | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [quest](Creature_questrelation#quest) | mediumint(8) unsigned | NO       | PRI     | 0           |           |

### Description of the fields

#### id

The ID of the creature. See [creature\_template.entry](creature_template#entry)

#### quest

The quest ID that the creature starts. See [quest\_template.entry](quest_template#entry)
