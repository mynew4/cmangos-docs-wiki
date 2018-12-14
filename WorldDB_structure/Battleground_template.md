Back to "world database":mangosdb_struct list of tables.

h2. The `battleground&#95;template` table

Contains information about the different battlegrounds, like how many players are needed to start, how many can be inside the same one, and the locations where each side starts.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Battleground_template#id|mediumint(8) unsigned|NO|PRI|||
|"MinPlayersPerTeam":Battleground_template#minplayersperteam|smallint(5) unsigned|NO||0||
|"MaxPlayersPerTeam":Battleground_template#maxplayersperteam|smallint(5) unsigned|NO||0||
||
|"AllianceStartLoc":Battleground_template#alliancestartloc|mediumint(8) unsigned|NO||||
|"AllianceStartO":Battleground_template#alliancestarto|float|NO||||
|"HordeStartLoc":Battleground_template#hordestartloc|mediumint(8) unsigned|NO||||
|"HordeStartO":Battleground_template#hordestarto|float|NO||||


h3. Description of the fields

h4. id

The battleground ID. See BattlemasterList.dbc

|_. ID|_. Type|
|1|Alterac Valley|
|2|Warsong Gulch|
|3|Arathi Basin|
|4|Nagrand Arena|
|5|Blade's Edge Arena|
|6|Nagrand Arena|
|7|Eye of the Storm|
|8|Ruins of Lordaeron|
|9|Strand of the Ancients|
|10|Dalaran Sewers|
|11|The Ring of Valor|


h4. MinPlayersPerTeam

Controls the minimum number of players that need to join the battleground on each faction side for the battleground to start. For the battleground to start, all characters (between min and max player values) must be in the same tier. Tiers are set up in ranges of 10 levels except for level 70. So the first tier is 10-19, the next are 20-29, 30-39, 40-49, 50-59, 60-69, and finally 70. If characters of different tiers all join the queue, they will join their respective tier's queue and wait for more players of their tier to join the queue. Characters in different tiers can never join the same battleground.

h4. MaxPlayersPerTeam

Controls how many players from each team can join the battleground.
NOTE2: If left to be 0, mangos will use the default DBC value.

h4. MinLvl

The minimum level that players need to be in order to join the battleground.
NOTE: If left to be 0, mangos will use the default DBC value.

h4. MaxLvl

The maximum level that players can be to enter the battleground.
NOTE: If left to be 0, mangos will use the default DBC value.

h4. AllianceStartLoc

The location where the alliance players get teleported to when the battleground first starts. See "WorldSafeLocs.dbc":WorldSafeLocs.dbc

h4. AllianceStartO

The orientation of the alliance players upon teleport into the battleground. North is 0, south is Pi (3.14159).

h4. HordeStartLoc

The location where the horde players get teleported to when the battleground first starts. See "WorldSafeLocs.dbc":WorldSafeLocs.dbc

h4. HordeStartO

The orientation of the horde players upon teleport into the battleground. North is 0, south is Pi (3.14159).
