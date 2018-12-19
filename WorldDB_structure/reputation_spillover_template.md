Back to [world database](mangosdb_struct) list of tables.

The \`reputation\_spillover\_template\` table
---------------------------------------------

This table holds data about the [Reputation Bleed Over](http://wowwiki.wikia.com/wiki/Exalted) -Effect

### Structure

| **Field**                                              | **Type**    | **Attributes** | **Key** | **Null** | **Default** |
|--------------------------------------------------------|-------------|----------------|---------|----------|-------------|
| [faction](Reputation_spillover_template#faction)       | smallint(6) | unsigned       | PRI     | NO       | 0           |
| [faction1](Reputation_spillover_template#faction1/2/3) | smallint(6) | unsigned       |         | NO       | 0           |
| [rate\_1](Reputation_spillover_template#rate)          | float(0)    | signed         |         | NO       | 0           |
| [rank\_1](Reputation_spillover_template#rank)          | tinyint(3)  | unsigned       |         | NO       | 0           |
| [faction2](Reputation_spillover_template#faction1/2/3) | smallint(6) | unsigned       |         | NO       | 0           |
| [rate\_2](Reputation_spillover_template#rate)          | float(0)    | signed         |         | NO       | 0           |
| [rank\_2](Reputation_spillover_template#rank)          | tinyint(3)  | unsigned       |         | NO       | 0           |
| [faction3](Reputation_spillover_template#faction1/2/3) | smallint(6) | unsigned       |         | NO       | 0           |
| [rate\_3](Reputation_spillover_template#rate)          | float(0)    | signed         |         | NO       | 0           |
| [rank\_3](Reputation_spillover_template#rank)          | tinyint(3)  | unsigned       |         | NO       | 0           |

### Description of the fields

#### faction

#### faction1/2/3

#### rate

#### rank

| Value | Rank       |
|-------|------------|
| 0     | Hated      |
| 1     | Hostil     |
| 2     | Unfriendly |
| 3     | Neutral    |
| 4     | Friendly   |
| 5     | Honored    |
| 6     | Revered    |
| 7     | Exalted    |


