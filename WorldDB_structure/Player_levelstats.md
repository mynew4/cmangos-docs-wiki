Back to [world database](mangosdb_struct) list of tables.

The \`player\_levelstats\` table
--------------------------------

This table holds information on what stats are gained by characters when they level up. Each race-class combination has different level stats. All of the values in this table signify only the base stats of the race-class combination at a specific level.

### Structure

| **Field**                        | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------|---------------------|----------|---------|-------------|-----------|
| [race](Player_levelstats#race)   | tinyint(3) unsigned | NO       | PRI     |             |           |
| [class](Player_levelstats#class) | tinyint(3) unsigned | NO       | PRI     |             |           |
| [level](Player_levelstats#level) | tinyint(3) unsigned | NO       | PRI     |             |           |
| [str](Player_levelstats#str)     | tinyint(3) unsigned | NO       |         |             |           |
| [agi](Player_levelstats#agi)     | tinyint(3) unsigned | NO       |         |             |           |
| [sta](Player_levelstats#sta)     | tinyint(3) unsigned | NO       |         |             |           |
| [inte](Player_levelstats#inte)   | tinyint(3) unsigned | NO       |         |             |           |
| [spi](Player_levelstats#spi)     | tinyint(3) unsigned | NO       |         |             |           |

### Description of the fields

#### race

The character race. This field along with [class](#class) defines what stats to be applied on the character.

#### class

The character class. This field along with [race](#race) defines what stats to be applied on the character.

#### level

The level at which the stats should be applied.

#### str

The base strength of the character.

#### agi

The base agility of the character.

#### sta

The base stamina of the character.

#### inte

The base intellect of the character.

#### spi

The base spirit of the character.
