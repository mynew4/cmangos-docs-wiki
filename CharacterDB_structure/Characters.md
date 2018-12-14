Back to the [characters database](charactersdb_struct) list of tables.

The \`character\` table
-----------------------

This table holds vital static information for each character. This information loaded and used to create the player objects in-game.

### Structure

| **Field**                                                 | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Characters#guid)                                   | int(11) unsigned    | NO       | PRI     | 0           |           |
| [account](Characters#account)                             | int(11) unsigned    | NO       | MUL     | 0           |           |
| [data](Characters#data)                                   | longtext            | YES      |         | None        |           |
| [name](Characters#name)                                   | varchar(12)         | NO       |         |             |           |
| [race](Characters#race)                                   | tinyint(3) unsigned | NO       |         | 0           |           |
| [class](Characters#class)                                 | tinyint(3) unsigned | NO       |         | 0           |           |
| [position\_x](Characters#position_x)                      | float               | NO       |         | 0           |           |
| [position\_y](Characters#position_y)                      | float               | NO       |         | 0           |           |
| [position\_z](Characters#position_z)                      | float               | NO       |         | 0           |           |
| [map](Characters#map)                                     | int(11) unsigned    | NO       |         | 0           |           |
| [dungeon\_difficulty](Characters#dungeon_difficulty)      | tinyint(1) unsigned | NO       |         | 0           |           |
| [orientation](Characters#orientation)                     | float               | NO       |         | 0           |           |
| [taximask](Characters#taximask)                           | longtext            | YES      |         | None        |           |
| [online](Characters#online)                               | tinyint(3) unsigned | NO       | MUL     | 0           |           |
| [cinematic](Characters#cinematic)                         | tinyint(3) unsigned | NO       |         | 0           |           |
| [totaltime](Characters#totaltime)                         | int(11) unsigned    | NO       |         | 0           |           |
| [leveltime](Characters#leveltime)                         | int(11) unsigned    | NO       |         | 0           |           |
| [logout\_time](Characters#logout_time)                    | int(11)             | NO       |         | 0           |           |
| [is\_logout\_resting](Characters#is_logout_resting)       | tinyint(3)          | NO       |         | 0           |           |
| [rest\_bonus](Characters#rest_bonus)                      | float               | NO       |         | 0           |           |
| [resettalents\_cost](Characters#resettalents_cost)        | int(11) unsigned    | NO       |         | 0           |           |
| [resettalents\_time](Characters#resettalents_time)        | bigint(20) unsigned | NO       |         | 0           |           |
| [trans\_x](Characters#trans_x)                            | float               | NO       |         | 0           |           |
| [trans\_y](Characters#trans_y)                            | float               | NO       |         | 0           |           |
| [trans\_z](Characters#trans_z)                            | float               | NO       |         | 0           |           |
| [trans\_o](Characters#trans_o)                            | float               | NO       |         | 0           |           |
| [transguid](Characters#transguid)                         | bigint(20) unsigned | NO       |         | 0           |           |
| [extra\_flags](Characters#extra_flags)                    | tinyint(3) unsigned | NO       |         | 0           |           |
| [stable\_slots](Characters#stable_slots)                  | tinyint(1) unsigned | NO       |         | 0           |           |
| [at\_login](Characters#at_login)                          | int(11) unsigned    | NO       |         | 0           |           |
| [zone](Characters#zone)                                   | int(11) unsigned    | NO       |         | 0           |           |
| [death\_expire\_time](Characters#death_expire_time)       | bigint(20) unsigned | NO       |         | 0           |           |
| [taxi\_path](Characters#taxi_path)                        | text                | YES      |         |             |           |
| [arena\_pending\_points](Characters#arena_pending_points) | int(10) unsigned    | NO       |         | 0           |           |
| [bgid](Characters#bgid)                                   | int(10) unsigned    | NO       |         | 0           |           |
| [bgteam](Characters#bgteam)                               | int(10) unsigned    | NO       |         | 0           |           |
| [bgmap](Characters#bgmap)                                 | int(10) unsigned    | NO       |         | 0           |           |
| [bgx](Characters#bgx)                                     | float               | NO       |         | 0           |           |
| [bgy](Characters#bgy)                                     | float               | NO       |         | 0           |           |
| [bgz](Characters#bgz)                                     | float               | NO       |         | 0           |           |
| [bgo](Characters#bgo)                                     | float               | NO       |         | 0           |           |

### Description of the fields

#### guid

The character global unique identifier. This number must be unique and is the best way to identify separate characters.

#### account

The account ID in which this character resides. See account.id in the realm database.

#### data

Big text field holding many different numbers all separated by a space that can be separated into an array with an explode function on the space. Table on what values are stored at what index can be found at [character\_data](character_data)

#### name

The name of the character.

#### race

The race of the character.

| Index |  Decimal| Race      |
|-------|--------:|-----------|
| 1     |        1| Human     |
| 2     |        2| Orc       |
| 3     |        4| Dwarf     |
| 4     |        8| Night Elf |
| 5     |       16| Undead    |
| 6     |       32| Tauren    |
| 7     |       64| Gnome     |
| 8     |      128| Troll     |
| 10    |      512| Blood Elf |
| 11    |     1024| Draenei   |

#### class

The class of the character:

| Index | Class   |
|-------|---------|
| 1     | Warrior |
| 2     | Paladin |
| 3     | Hunter  |
| 4     | Rogue   |
| 5     | Priest  |
| 7     | Shaman  |
| 8     | Mage    |
| 9     | Warlock |
| 11    | Druid   |

#### position\_x

The x position of the character's location.

#### position\_y

The y position of the character's location.

#### position\_z

The z position of the character's location.

#### map

The map ID the character is in.

#### dungeon\_difficulty

The current difficulty that the player is in.

#### orientation

The orientation the character is facing. (North = 0.0, South = 3.14159)

#### taximask

#### online

Records whether the character is online (1) or offline (0).

#### cinematic

Boolean 1 or 0 controlling whether the start cinematic has been shown or not.

#### totaltime

The total time that the character has been active in the world, measured in seconds.

#### leveltime

The total time the character has spent in the world at the current level, measured in seconds.

#### logout\_time

The time when the character last logged out, measured in Unix time.

#### is\_logout\_resting

Boolean 1 or 0 controlling if the character is currently in a resting zone or not.

#### rest\_bonus

#### resettalents\_cost

The cost for the character to reset its talents, measured in copper.

#### resettalents\_time

#### trans\_x

#### trans\_y

#### trans\_z

#### trans\_o

#### transguid

#### extra\_flags

These flags control certain player specific attributes, mostly GM features

| Bit | Name                               | Description                                  |
|-----|------------------------------------|----------------------------------------------|
| 1   | PLAYER\_EXTRA\_GM\_ON              | Defines GM state                             |
| 2   | PLAYER\_EXTRA\_GM\_ACCEPT\_TICKETS | Defines if tickets are accepted              |
| 4   | PLAYER\_EXTRA\_ACCEPT\_WHISPERS    | Defines if whispers are accepted             |
| 8   | PLAYER\_EXTRA\_TAXICHEAT           | Sets taxicheat                               |
| 16  | PLAYER\_EXTRA\_GM\_INVISIBLE       | Control's GM's invisibly                     |
| 32  | PLAYER\_EXTRA\_GM\_CHAT            | Show GM badge in chat messages               |
| 64  | PLAYER\_EXTRA\_PVP\_DEATH          | Store PvP death status until corpse creating |

#### stable\_slots

The number of stable slots the player has available. Maximum is 2.

#### at\_login

This field is a bitmask controlling different actions taken once a player logs in with the character.

-   1 = Force character to change name
-   2 = Reset spells (professions as well)
-   4 = Reset talents
-   8 = Character Customization enabled

For multiple actions, add values together.

#### zone

The zone ID the character is in.

#### death\_expire\_time

Time when a character can be resurrected in case of a server crash or client exit while in ghost form.

#### taxi\_path

Stores the players current taxi path (TaxiPath.dbc) if logged off while on one.
