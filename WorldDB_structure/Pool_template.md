Back to [world database](mangosdb_struct) list of tables.

The \`pool\_template\` table
----------------------------

Contains all pool instances that participate to any game event.

### Structure

| **Field**                             | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry](Pool_template#entry)          | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [max\_limit](Pool_template#max_limit) | int(10) unsigned      | NO       |         | 0           |           |

### Description of the fields

#### entry

Pool's ID.

#### max\_limit

Max number of objects (0) is no limit.
