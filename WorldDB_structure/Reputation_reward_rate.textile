Back to "world database":mangosdb_struct list of tables.

h2. The `reputation&#95;reward&#95;rate` table

Holds reputation multipliers for specific factions.

h3. Structure


|*Field*|*Type*|*Attributes*|*Key*|*Null*|*Default*|*Extra*|*Comment*|
|"faction":Reputation_reward_rate#faction|mediumint(8)|unsigned|PRI|NO|0|||
|"quest_rate":Reputation_reward_rate#quest_rate|float|signed||NO|1|||
|"creature_rate":Reputation_reward_rate#creature_rate|float|signed||NO|1|||
|"spell_rate":Reputation_reward_rate#spell_rate|float|signed||NO|1|||


h3. Description of the fields

h4. faction

The ID of the faction these rates apply to.

h4. quest&#95;rate

The rate for reputation gain from quests.

h4. creature&#95;rate

The rate for reputation gain from creatures.

h4. spell&#95;rate

The rate for reputation gain from spells.
