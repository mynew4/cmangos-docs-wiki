Back to [world database](mangosdb_struct) list of tables.

The \`command\` table
---------------------

Holds help and security information for commands.

### Structure

| **Field**                    | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|------------------------------|---------------------|----------|---------|-------------|-----------|
| [name](Command#name)         | varchar(50)         | NO       | PRI     |             |           |
| [security](Command#security) | tinyint(3) unsigned | NO       |         | 0           |           |
| [help](Command#help)         | longtext            | YES      |         | None        |           |

### Description of the fields

#### name

The name of the command.

#### security

The security level required to use the command. Corresponds with [account.gmlevel](account#gmlevel) in the realm database.

#### help

The help text displayed by the .help command.
