Back to [world database](mangosdb_struct) list of tables.

The \`reputation\_reward\_rate\` table
--------------------------------------

Holds reputation multipliers for specific factions.

### Structure

| **Field**                                              | **Type**     | **Attributes** | **Key** | **Null** | **Default** | **Extra** | **Comment** |
|--------------------------------------------------------|--------------|----------------|---------|----------|-------------|-----------|-------------|
| [faction](Reputation_reward_rate#faction)              | mediumint(8) | unsigned       | PRI     | NO       | 0           |           |             |
| [quest\_rate](Reputation_reward_rate#quest_rate)       | float        | signed         |         | NO       | 1           |           |             |
| [creature\_rate](Reputation_reward_rate#creature_rate) | float        | signed         |         | NO       | 1           |           |             |
| [spell\_rate](Reputation_reward_rate#spell_rate)       | float        | signed         |         | NO       | 1           |           |             |

### Description of the fields

#### faction

The ID of the faction these rates apply to.

#### quest\_rate

The rate for reputation gain from quests.

#### creature\_rate

The rate for reputation gain from creatures.

#### spell\_rate

The rate for reputation gain from spells.
