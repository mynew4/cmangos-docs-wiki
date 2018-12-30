Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_achievement\` table
------------------------------------

This table holds information for each character and its achievement.

### Structure

| **Field**                                        | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Character_achievement#guid)               | int(11) unsigned | NO       | PRIMARY |             |           |
| [achievement](Character_achievement#achievement) | int(11)          | NO       | PRIMARY |             |           |
| [date](Character_achievement#date)               | int(11)          | NO       |         |             |           |

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### achievement

The ID of the achievement. See [achievements.dbc](achievements.dbc)

#### date

Unix timestamp when achievement was completed.
