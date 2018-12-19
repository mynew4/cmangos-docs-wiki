Back to the [characters database](charactersdb_struct) list of tables.

The \`guild\_bank\_right\` table
--------------------------------

### Structure

| **Field**                                 | **Type**            | **Null** | **Key** | **Default** | **Extra**       |
|-------------------------------------------|---------------------|----------|---------|-------------|-----------------|
| [guildid](Guild_bank_right#guildid)       | int(11)             | NO       | PRI     | None        | auto\_increment |
| [TabId](Guild_bank_right#tabid)           | tinyint(1) unsigned | NO       | PRI     | 0           |                 |
| [rid](Guild_bank_right#rid)               | int(11) unsigned    | NO       | PRI     | None        |                 |
| [gbright](Guild_bank_right#gbright)       | tinyint(3)          | NO       |         | 0           |                 |
| [SlotPerDay](Guild_bank_right#slotperday) | int(11) unsigned    | NO       |         | 0           |                 |

### Description of the fields

#### guildid

Reference to guildid in table guild.

#### TabId

#### guildid

#### rid

#### gbright

#### SlotPerDay
