Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_ticket\` table
-------------------------------

Holds ticket information from tickets written through the client help request -function.

### Structure

| **Field**                                                | **Type**         | **Null** | **Key** | **Default**        | **Extra**       |
|----------------------------------------------------------|------------------|----------|---------|--------------------|-----------------|
| [ticket\_id](Character_ticket#ticket_id)                 | int(11)          | NO       | PRI     | None               | auto\_increment |
| [guid](Character_ticket#guid)                            | int(11) unsigned | NO       |         | 0                  |                 |
| [ticket\_text](Character_ticket#ticket_text)             | text             | YES      |         | None               |                 |
| [ticket\_category](Character_ticket#ticket_category)     | int(1)           | NO       |         | 0                  |                 |
| [ticket\_lastchange](Character_ticket#ticket_lastchange) | timestamp        | NO       |         | CURRENT\_TIMESTAMP |                 |

### Description of the fields

#### ticket\_id

A unique ticket ID.

#### guid

The GUID of the character sending the ticket. See [characters.guid](characters#guid)

#### ticket\_text

The ticket description text; the text written by the player in describing the problem.

#### ticket\_category

The ticket category:

| ID  | Category            |
| --- | ------------------- |
| 0   | Item                |
| 1   | Behavior/Harassment |
| 2   | Guild               |
| 3   | Character           |
| 4   | Non-quest/Creep     |
| 5   | Stuck               |
| 6   | Environmental       |
| 7   | Quest/Quest NPC     |
| 8   | Account/Billing     |

#### ticket\_lastchange

Stores the time when this ticket was last changed.
