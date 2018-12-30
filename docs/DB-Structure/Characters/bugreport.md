Back to the [characters database](charactersdb_struct) list of tables.

The \`bugreport\` table
-----------------------

This table stores all the Bug/Suggestion submitted ingame by Players.

### Structure

| **Field**                    | **Type**     | **Null** | **Key** | **Default** | **Extra**       |
|------------------------------|--------------|----------|---------|-------------|-----------------|
| [id](Bugreport#id)           | int(11)      | NO       | PRI     | None        | auto\_increment |
| [type](Bugreport#type)       | varchar(255) | NO       |         |             |                 |
| [content](Bugreport#content) | varchar(255) | NO       |         |             |                 |

### Description of the fields

#### id

Auto generated value when records are inserted by MaNGOS. This id is just here to be a primary key and eases the data insertion.

#### type

The text description of the type of bug/suggestion.

#### content

The text content of the bug/suggestion.
