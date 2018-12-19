Back to [world database](mangosdb_struct) list of tables.

The \`player\_xp\_for\_level\` table
------------------------------------

Includes information on how much experience needed for next level. Comes from sniffs.

### Structure

| **Field**                                                     | **Type** | **Attributes** | **Key** | **Null** | **Default** | **Extra** | **Comment** |
|---------------------------------------------------------------|----------|----------------|---------|----------|-------------|-----------|-------------|
| [lvl](Player_xp_for_level#lvl)                                | int(3)   | unsigned       | PRI     | NO       | NULL        |           |             |
| [xp\_for\_next\_level](Player_xp_for_level#xp_for_next_level) | int(10)  | unsigned       |         | NO       | NULL        |           |             |

### Description of the fields

This table sets the exp point needed to upgrade the player's level.

#### lvl

The player's level.

#### xp\_for\_next\_level

The experience needed to upgrade from the value in "lvl" field to "lvl" +1.
