Back to [world database](mangosdb_struct) list of tables.

The \`pool\_creature\` table
----------------------------

Contains all creatures pooled by their [\`creature\`.\`guid\`](Creature#guid).

### Structure

| **Field**                               | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [guid](pool_creature#guid)              | int(10) unsigned      | NO       | PRI     | 0           |           |
| [pool\_entry](pool_creature#pool_entry) | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [chance](pool_creature#chance)          | float unsigned        | NO       |         | 0           |           |

### Description of the fields

#### guid

Creature's GUID. See [\`creature\`.\`guid\`](Creature#guid).

#### pool\_entry

Pool's ID. See [pool\_template](pool_template)

#### chance

Chance the creature will be spawned in the pool.
