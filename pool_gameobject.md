Back to [world database](mangosdb_struct) list of tables.

The \`pool\_gameobject\` table
------------------------------

Contains all gameobjects pooled by their [\`gameobject\`.\`guid\`](gameobject#guid).

### Structure

| **Field**                                 | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [guid](pool_gameobject#guid)              | int(10) unsigned      | NO       | PRI     | 0           |           |
| [pool\_entry](pool_gameobject#pool_entry) | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [chance](pool_gameobject#chance)          | float unsigned        | NO       |         | 0           |           |

### Description of the fields

#### guid

Gameobject's GUID. A reference to [\`gameobject\`.\`guid\`](gameobject#guid).

#### pool\_entry

Pool's ID. See [pool\_template](pool_template)

#### chance

Chance the gameobject will be spawned in the pool.
