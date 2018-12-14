Back to [world database](mangosdb_struct) list of tables.

The \`skill\_fishing\_base\_level\` table
-----------------------------------------

This table controls the minimum skill level required in fishing to fish in a certain area.

### Structure

| **Field**                               | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry](Skill_fishing_base_level#entry) | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [skill](Skill_fishing_base_level#skill) | smallint(6)           | NO       |         | 0           |           |

### Description of the fields

#### entry

The area ID (see AreaTable.dbc).

#### skill

The minimum skill points in fishing required to fish in the area.
