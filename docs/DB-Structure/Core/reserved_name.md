Back to [world database](mangosdb_struct) list of tables.

The \`reserved\_name\` table
----------------------------

This table serves as a simple list of names that players (gmlevel == 0) cannot use when naming their characters.

### Structure

| **Field**                  | **Type**    | **Null** | **Key** | **Default** | **Extra** |
|----------------------------|-------------|----------|---------|-------------|-----------|
| [name](Reserved_name#name) | varchar(12) | NO       | PRI     |             |           |

### Description of the fields

#### name

The name that cannot be used by players when naming characters.
