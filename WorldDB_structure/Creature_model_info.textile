Back to "world database":mangosdb_struct list of tables.

h2. The `creature&#95;model&#95;info` table

This table contains all models of mobs, their gender and other information that are model related. This means that when a creature uses another model, this information will change as well.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"modelid":Creature_model_info#modelid|mediumint(8) unsigned|NO|PRI|0||
|"bounding_radius":Creature_model_info#bounding_radius|float|NO||0||
|"combat_reach":Creature_model_info#combat_reach|float|NO||0||
|"SpeedWalk":Creature_model_info#SpeedWalk|float|NO||1||
|"SpeedRun":Creature_model_info#SpeedRun|float|NO||1.14286||
|"gender":Creature_model_info#gender|tinyint(3) unsigned|NO||2||
|"modelid_other_gender":Creature_model_info#modelid_other_gender|mediumint(8) unsigned|NO||0||
|"modelid_alternative":Creature_model_info#modelid_alternative|mediumint(8) unsigned|NO||0||


h3. Description of the fields

h4. modelid

Display ID from CreatureDisplayInfo.dbc

h4. bounding&#95;radius

A field scaled with size.
Might or might not have any relation to some radius of a bowl enclosing the creature.
Currently badly used in the above suggested way in some cases, which is false in general.

h4. combat&#95;reach

This is an additional distance that is added to range of attacks (both melee and spells) to check if an attack can reach the enemy.

h4. SpeedWalk

This Field Controls How Fast An NPC Moves When Walking. This speed can be overridden by setting another value in "creature_template.SpeedWalk":creature_template#SpeedWalk.

This Value Comes From Sniff Packet Data.

Divide sniffed value with 2.5.
Example: Sniffed WalkSpeed for a specific creature is 5. Divide it by 2.5 to get our DB value.
5/2.5=2

(Default Value Is: 1)

h4. SpeedRun

This Field Controls How Fast An NPC Moves When Running. This speed can be overridden by setting another value in "creature_template.SpeedRun":creature_template#SpeedRun.

This Value Comes From Sniff Packet Data.

Divide sniffed value with 7.
Example: Sniffed RunSpeed for a specific creature is 10. Divide it by 7 to get our DB value.
10/7=1,42857

(Default Value Is: 1.14286)

h4. gender

Gender of the creature

* 0: Male
* 1: Female
* 2: None

h4. modelid&#95;other&#95;gender

Point to "Creature&#95;model&#95;info.modelid":Creature_model_info#modelid. When the entry is gender male (0) or female (1), this value can point to the display id of the other gender.

h3. modelid&#95;alternative

Alternative to the current model.
