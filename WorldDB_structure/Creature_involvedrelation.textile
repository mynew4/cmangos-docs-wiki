Back to "world database":mangosdb_struct list of tables.

h2. The `creature&#95;involvedrelation` table

Holds NPC quest ender relations on which NPCs finishes which quests.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Creature_involvedrelation#id|mediumint(8) unsigned|NO|PRI|0||
|"quest":Creature_involvedrelation#quest|mediumint(8) unsigned|NO|PRI|0||


h3. Description of the fields

h4. id

The ID of the creature. See "creature&#95;template.entry":creature_template#entry

h4. quest

The quest ID that the creature finishes. See "quest&#95;template.entry":quest_template#entry
