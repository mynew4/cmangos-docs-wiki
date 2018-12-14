Back to "world database":mangosdb_struct list of tables.

h2. The `creature&#95;model&#95;race` table

This table contains data to override displayed models based on the race of the player. Use creature_entry or modelid_racial to specify the new models, but not both.


h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"modelid":Creature_model_race#modelid|mediumint(8) unsigned|NO|PRI|0||
|"racemask":Creature_model_race#racemask|mediumint(8) unsigned|NO|PRI|0||
|"creature_entry":Creature_model_race#creature_entry|mediumint(8) unsigned|NO||0||
|"modelid_racial":Creature_model_race#modelid_racial|mediumint(8) unsigned|NO||0||


h3. Description of the fields

h4. modelid

The model id to override with a different model.

h4. racemask

The racemask you want to trigger the model override for.

h4. creature&#95;entry

A creature_template entry id - this will override the model using the model(s) from the specified creature_template entry.

h4. modelid&#95;racial

The id of a specific model to use when overriding.