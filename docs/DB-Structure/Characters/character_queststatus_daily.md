Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_queststatus\_daily\` table
-------------------------------------------

Holds information on the daily quest status of every player. The quest must have type = 87 or the 4096 flag at SpecialFlags.

### Structure

| **Field**                                  | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Character_queststatus_daily#guid)   | int(11) unsigned    | NO       | PRI     | 0           |           |
| [quest](Character_queststatus_daily#quest) | int(11) unsigned    | NO       | PRI     | 0           |           |
| [time](Character_queststatus_daily#time)   | bigint(20) unsigned | NO       |         | 0           |           |

#### guid

The character GUID. See [characters.guid](characters#guid)

#### quest

The quest ID of the daily quest. See [quest\_template.entry](quest_template#entry)

#### time

The time when the quest was taken, in Unix time.
