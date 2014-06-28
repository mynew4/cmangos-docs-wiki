Back to "world database":mangosdb_struct list of tables.

h2. The `creature&#95;onkill&#95;reputation` table

This table controls the reputation given by creatures when killed by other players.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"creature_id":Creature_onkill_reputation#creature_id|mediumint(8) unsigned|NO|PRI|0|Creature Identifier|
|"RewOnKillRepFaction1":Creature_onkill_reputation#rewonkillrepfaction|smallint(6)|NO||0||
|"RewOnKillRepFaction2":Creature_onkill_reputation#rewonkillrepfaction|smallint(6)|NO||0||
|"MaxStanding1":Creature_onkill_reputation#maxstanding|tinyint(4)|NO||0||
|"IsTeamAward1":Creature_onkill_reputation#isteamaward|tinyint(4)|NO||0||
|"RewOnKillRepValue1":Creature_onkill_reputation#rewonkillrepvalue|mediumint(9)|NO||0||
|"MaxStanding2":Creature_onkill_reputation#maxstanding|tinyint(4)|NO||0||
|"IsTeamAward2":Creature_onkill_reputation#isteamaward|tinyint(4)|NO||0||
|"RewOnKillRepValue2":Creature_onkill_reputation#rewonkillrepvalue|mediumint(9)|NO||0||
|"TeamDependent":Creature_onkill_reputation#teamdependent|tinyint(3) unsigned|NO||0||


h3. Description of the fields

h4. creature&#95;id

The template ID of the creature. See "creature&#95;template.entry":creature_template#entry

h4. RewOnKillRepFaction

The faction ID of the faction that the player will gain or lose points in. See "Faction.dbc":Faction.dbc

h4. MaxStanding

The maximum standing that the creature will award reputation until. If the player achieves standing higher than this, the creature will not award any reputation.

|_. ID|_. Rank|
|0|Hated|
|1|Hostile|
|2|Unfriendly|
|3|Neutral|
|4|Friendly|
|5|Honored|
|6|Revered|
|7|Exalted|


h4. IsTeamAward

Boolean 0 or 1 that controls if the player receives the reputation not only to the faction but also the faction team.

* 0: Player receives reputation only for the faction
* 1: Player receives reputation both for the faction and the faction's team

NOTE: The reputation value that the player gains for the team (if the field is 1) is half of the value specified in "RewOnKillRepValue":#RewOnKillRepValue

h4. RewOnKillRepValue

The reputation value that the player gains (or loses if it's negative) by killing the creature.

h4. TeamDependent

Boolean 0 or 1.

* 0: The creature will give reputation to the any player from both fields (RewOnKillRepFaction1 and RewOnKillRepFaction2) if both fields are non-zero.
* 1: The creature will award alliance players the reputation from RewOnKillRepFaction1 and will award horde players the reputation from RewOnKillRepFaction2
