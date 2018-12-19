Back to [world database](mangosdb_struct) list of tables.

The \`exploration\_basexp\` table
---------------------------------

This table controls the XP gained by characters when they explore new zones.

### Structure

| **Field**                           | **Type**   | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------|------------|----------|---------|-------------|-----------|
| [level](Exploration_basexp#level)   | tinyint(2) | NO       | PRI     | 0           |           |
| [basexp](Exploration_basexp#basexp) | int(11)    | NO       |         | 0           |           |

### Description of the fields

#### level

The level of the character.

#### basexp

The XP the character receives at the specified level.
