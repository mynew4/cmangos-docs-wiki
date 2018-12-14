Back to [world database](mangosdb_struct) list of tables.

The \`pet\_name\_generation\` table
-----------------------------------

This table holds pieces of names (first and last half) that are use for pet name generation.

### Structure

| **Field**                          | **Type**         | **Null** | **Key** | **Default** | **Extra**       |
|------------------------------------|------------------|----------|---------|-------------|-----------------|
| [id](Pet_name_generation#id)       | int(11) unsigned | NO       | PRI     | NULL        | auto\_increment |
| [word](Pet_name_generation#word)   | tinytext         | NO       |         |             |                 |
| [entry](Pet_name_generation#entry) | int(11) unsigned | NO       |         | 0           |                 |
| [half](Pet_name_generation#half)   | int(11)          | NO       |         | 0           |                 |

### Description of the fields

#### id

The ID of the entry. This is an auto increment field and this is an arbitrary number. When adding entries it is best to just let the database pick the next available ID number.

#### word

The name part for this entry.

#### entry

The entry from [creature\_template.entry](creature_template#entry) for the creature that you want this part of the name to be generated for.

#### half

This determines whether this is the first or last half of the name for this entry.

-   0 First half
-   1 Last half

