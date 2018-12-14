Back to [world database](mangosdb_struct) list of tables.

The \`spell\_elixir\` table
---------------------------

This table holds elixir information to be used to properly stack the elixirs.

### Structure

| **Field**                   | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------|---------------------|----------|---------|-------------|-----------|
| [entry](Spell_elixir#entry) | int(11) unsigned    | NO       | PRI     | 0           |           |
| [mask](Spell_elixir#mask)   | tinyint(1) unsigned | NO       |         | 0           |           |

### Description of the fields

#### entry

The spell ID used by the elixir.

#### mask

The type of elixir the spell is classified as.

| Value | Type            |
|-------|-----------------|
| 1     | Battle          |
| 2     | Guardian        |
| 3     | Flask           |
| 7     | Unstable flask  |
| 11    | Shattrath flask |


