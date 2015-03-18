Back to the "characters database":charactersdb_struct list of tables.

h2. The `character` table

This table holds vital static information for each character. This information loaded and used to create the player objects in-game.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Characters#guid|int(11) unsigned|NO|PRI|0||
|"account":Characters#account|int(11) unsigned|NO|MUL|0||
|"data":Characters#data|longtext|YES||None||
|"name":Characters#name|varchar(12)|NO||||
|"race":Characters#race|tinyint(3) unsigned|NO||0||
|"class":Characters#class|tinyint(3) unsigned|NO||0||
|"position_x":Characters#position_x|float|NO||0||
|"position_y":Characters#position_y|float|NO||0||
|"position_z":Characters#position_z|float|NO||0||
|"map":Characters#map|int(11) unsigned|NO||0||
|"dungeon_difficulty":Characters#dungeon_difficulty|tinyint(1) unsigned|NO||0||
|"orientation":Characters#orientation|float|NO||0||
|"taximask":Characters#taximask|longtext|YES||None||
|"online":Characters#online|tinyint(3) unsigned|NO|MUL|0||
|"cinematic":Characters#cinematic|tinyint(3) unsigned|NO||0||
|"totaltime":Characters#totaltime|int(11) unsigned|NO||0||
|"leveltime":Characters#leveltime|int(11) unsigned|NO||0||
|"logout_time":Characters#logout_time|int(11)|NO||0||
|"is_logout_resting":Characters#is_logout_resting|tinyint(3)|NO||0||
|"rest_bonus":Characters#rest_bonus|float|NO||0||
|"resettalents_cost":Characters#resettalents_cost|int(11) unsigned|NO||0||
|"resettalents_time":Characters#resettalents_time|bigint(20) unsigned|NO||0||
|"trans_x":Characters#trans_x|float|NO||0||
|"trans_y":Characters#trans_y|float|NO||0||
|"trans_z":Characters#trans_z|float|NO||0||
|"trans_o":Characters#trans_o|float|NO||0||
|"transguid":Characters#transguid|bigint(20) unsigned|NO||0||
|"extra_flags":Characters#extra_flags|tinyint(3) unsigned|NO||0||
|"stable_slots":Characters#stable_slots|tinyint(1) unsigned|NO||0||
|"at_login":Characters#at_login|int(11) unsigned|NO||0||
|"zone":Characters#zone|int(11) unsigned|NO||0||
|"death_expire_time":Characters#death_expire_time|bigint(20) unsigned|NO||0||
|"taxi_path":Characters#taxi_path|text|YES||||
|"arena_pending_points":Characters#arena_pending_points|int(10) unsigned|NO||0||
|"bgid":Characters#bgid|int(10) unsigned|NO||0||
|"bgteam":Characters#bgteam|int(10) unsigned|NO||0||
|"bgmap":Characters#bgmap|int(10) unsigned|NO||0||
|"bgx":Characters#bgx|float|NO||0||
|"bgy":Characters#bgy|float|NO||0||
|"bgz":Characters#bgz|float|NO||0||
|"bgo":Characters#bgo|float|NO||0||


h3. Description of the fields

h4. guid

The character global unique identifier. This number must be unique and is the best way to identify separate characters.

h4. account

The account ID in which this character resides. See account.id in the realm database.

h4. data

Big text field holding many different numbers all separated by a space that can be separated into an array with an explode function on the space. Table on what values are stored at what index can be found at "character_data":character_data

h4. name

The name of the character.

h4. race

The race of the character.

|_. Index |_. Decimal |_. Race |
|1 |>. 1 | Human |
|2 |>. 2 | Orc |
|3 |>. 4 | Dwarf |
|4 |>. 8 | Night Elf |
|5 |>. 16 | Undead |
|6 |>. 32 | Tauren |
|7 |>. 64 | Gnome |
|8 |>. 128 | Troll |
|10 |>. 512 | Blood Elf |
|11 |>. 1024 | Draenei | 

h4. class

The class of the character:

|_. Index |_. Class |
|1 | Warrior |
|2 | Paladin |
|3 | Hunter |
|4 | Rogue |
|5 | Priest |
|7 | Shaman |
|8 | Mage |
|9 | Warlock |
|11 | Druid | 

h4. position&#95;x

The x position of the character's location.

h4. position&#95;y

The y position of the character's location.

h4. position&#95;z

The z position of the character's location.

h4. map

The map ID the character is in.

h4. dungeon&#95;difficulty

The current difficulty that the player is in.

h4. orientation

The orientation the character is facing. (North = 0.0, South = 3.14159)

h4. taximask

h4. online

Records whether the character is online (1) or offline (0).

h4. cinematic

Boolean 1 or 0 controlling whether the start cinematic has been shown or not.

h4. totaltime

The total time that the character has been active in the world, measured in seconds.

h4. leveltime

The total time the character has spent in the world at the current level, measured in seconds.

h4. logout&#95;time

The time when the character last logged out, measured in Unix time.

h4. is&#95;logout&#95;resting

Boolean 1 or 0 controlling if the character is currently in a resting zone or not.

h4. rest&#95;bonus

h4. resettalents&#95;cost

The cost for the character to reset its talents, measured in copper.

h4. resettalents&#95;time

h4. trans&#95;x

h4. trans&#95;y

h4. trans&#95;z

h4. trans&#95;o

h4. transguid

h4. extra&#95;flags

These flags control certain player specific attributes, mostly GM features

|_. Bit|_. Name|_. Description|
|1|PLAYER&#95;EXTRA&#95;GM&#95;ON|Defines GM state|
|2|PLAYER&#95;EXTRA&#95;GM&#95;ACCEPT&#95;TICKETS|Defines if tickets are accepted|
|4|PLAYER&#95;EXTRA&#95;ACCEPT&#95;WHISPERS|Defines if whispers are accepted|
|8|PLAYER&#95;EXTRA&#95;TAXICHEAT|Sets taxicheat|
|16|PLAYER&#95;EXTRA&#95;GM&#95;INVISIBLE|Control's GM's invisibly|
|32|PLAYER&#95;EXTRA&#95;GM&#95;CHAT|Show GM badge in chat messages|
|64|PLAYER&#95;EXTRA&#95;PVP&#95;DEATH|Store PvP death status until corpse creating|


h4. stable&#95;slots

The number of stable slots the player has available. Maximum is 2.

h4. at&#95;login

This field is a bitmask controlling different actions taken once a player logs in with the character.

* 1 = Force character to change name
* 2 = Reset spells (professions as well)
* 4 = Reset talents
* 8 = Character Customization enabled

For multiple actions, add values together.

h4. zone

The zone ID the character is in.

h4. death&#95;expire&#95;time

Time when a character can be resurrected in case of a server crash or client exit while in ghost form.

h4. taxi&#95;path

Stores the players current taxi path (TaxiPath.dbc) if logged off while on one.
