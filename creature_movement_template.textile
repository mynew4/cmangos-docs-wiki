Back to "world database":mangosdb_struct list of tables.

h2. The `creature&#95;movement&#95;template` table

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Creature_movement_template#entry|mediumint(8) unsigned|NO|PRI|||

|"modelid":Creature_model_info#modelid|mediumint(8) unsigned|NO|PRI|0||
|"bounding_radius":Creature_model_info#bounding_radius|float|NO||0||
|"combat_reach":Creature_model_info#combat_reach|float|NO||0||
|"gender":Creature_model_info#gender|tinyint(3) unsigned|NO||2||
|"modelid_other_gender":Creature_model_info#modelid_other_gender|mediumint(8) unsigned|NO||0||
|"modelid_alternative":Creature_model_info#modelid_alternative|mediumint(8) unsigned|NO||0||
