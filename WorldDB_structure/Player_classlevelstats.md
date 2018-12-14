Back to [world database](mangosdb_struct) list of tables.

The \`player\_classlevelstats\` table
-------------------------------------

This table holds information on the base health and mana of characters when they level up. Each class has different level stats. All of the values in this table signify only the base health and mana of the class at a specific level.

### Structure

| **Field**                                   | **Type**             | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------------|----------------------|----------|---------|-------------|-----------|
| [class](Player_classlevelstats#class)       | tinyint(3) unsigned  | NO       | PRI     |             |           |
| [level](Player_classlevelstats#level)       | tinyint(3) unsigned  | NO       | PRI     |             |           |
| [basehp](Player_classlevelstats#basehp)     | smallint(5) unsigned | NO       |         |             |           |
| [basemana](Player_classlevelstats#basemana) | smallint(5) unsigned | NO       |         |             |           |
|                                             |                      |

### Description of the fields

#### class

The character class.

#### level

The level at which the stats should be applied.

#### basehp

The base health of the character (before stamina bonuses).

#### basemana

The base mana of the character (before intellect bonuses).
