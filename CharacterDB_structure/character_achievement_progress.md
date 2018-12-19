Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_achievement\_progress\` table
----------------------------------------------

This table holds information for each character and its achievement progress.

### Structure

| **Field**                                           | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Character_achievement_progress#guid)         | int(11) unsigned | NO       | PRIMARY |             |           |
| [criteria](Character_achievement_progress#criteria) | int(11)          | NO       | PRIMARY |             |           |
| [counter](Character_achievement_progress#counter)   | int(11)          | NO       |         |             |           |
| [date](Character_achievement_progress#date)         | int(11)          | NO       |         |             |           |

#### guid

The GUID of the character. See [character.guid](character#guid)

#### criteria

#### counter

#### date
