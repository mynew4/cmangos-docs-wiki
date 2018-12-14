Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_reputation\` table
-----------------------------------

This table holds the reputation information for each character.

### Structure

| **Field**                                 | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Character_reputation#guid)         | int(11) unsigned | NO       | PRI     | 0           |           |
| [faction](Character_reputation#faction)   | int(11) unsigned | NO       | PRI     | 0           |           |
| [standing](Character_reputation#standing) | int(11)          | NO       |         | 0           |           |
| [flags](Character_reputation#flags)       | int(11)          | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the character. See [character.guid](character#guid)

#### faction

The faction ID that the character has the given reputation in. See [Faction.dbc](Faction.dbc)

#### standing

The current reputation value that the character has.

#### flags

This field is a bitmask containing flags that apply to the faction and how it's displayed to the character. Just like any flag field, you can combine flags by adding them together. If this field is 0, then it is not shown in the reputation list in-game.

| Flag | Name                     | Comments                                        |
|------|--------------------------|-------------------------------------------------|
| 1    | FACTION\_FLAG\_VISIBLE   | Displayed in the reputation tab                 |
| 2    | FACTION\_FLAG\_AT\_WAR   | Active when the player sets the at war checkbox |
| 4    | FACTION\_FLAG\_UNKNOWN   |                                                 |
| 8    | FACTION\_FLAG\_INVISIBLE |                                                 |
| 16   | FACTION\_FLAG\_OWN\_TEAM |                                                 |
| 32   | FACTION\_FLAG\_INACTIVE  |                                                 |


