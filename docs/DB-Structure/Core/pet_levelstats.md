Back to [world database](mangosdb_struct) list of tables.

The \`pet\_levelstats\` table
-----------------------------

This table holds information on individual pet base stats based on level.

### Structure

| **Field**                                        | **Type**             | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------------------|----------------------|----------|---------|-------------|-----------|
| [creature\_entry](Pet_levelstats#creature_entry) | int(10) unsigned     | NO       | PRI     |             |           |
| [level](Pet_levelstats#level)                    | tinyint(3) unsigned  | NO       | PRI     |             |           |
| [hp](Pet_levelstats#hp)                          | smallint(5) unsigned | NO       |         |             |           |
| [mana](Pet_levelstats#mana)                      | smallint(5) unsigned | NO       |         |             |           |
| [armor](Pet_levelstats#armor)                    | int(10) unsigned     | NO       |         | 0           |           |
| [str](Pet_levelstats#str)                        | smallint(5) unsigned | NO       |         |             |           |
| [agi](Pet_levelstats#agi)                        | smallint(5) unsigned | NO       |         |             |           |
| [sta](Pet_levelstats#sta)                        | smallint(5) unsigned | NO       |         |             |           |
| [inte](Pet_levelstats#inte)                      | smallint(5) unsigned | NO       |         |             |           |
| [spi](Pet_levelstats#spi)                        | smallint(5) unsigned | NO       |         |             |           |

### Description of the fields

#### creature\_entry

The pet creature template ID. See [creature\_template.entry](creature_template#entry)

#### level

The pet level.

#### hp

The base health of the pet at level = [level](#level).

#### mana

The base mana of the pet at level = [level](#level).

#### armor

The base armor of the pet at level = [level](#level).

#### str

The base strength of the pet at level = [level](#level).

#### agi

The base agility of the pet at level = [level](#level).

#### sta

The base stamina of the pet at level = [level](#level).

#### inte

The base intelligence of the pet at level = [level](#level).

#### spi

The base spirit of the pet at level = [level](#level).
