Back to [world database](mangosdb_struct) list of tables.

The \`mail\_level\_reward\` table
---------------------------------

This table holds information on sent mails when a character levels up. Can be specified by raceMask.

### Structure

| **Field**                                          | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [level](Mail_level_reward#level)                   | tinyint(3) unsigned   | NO       | PRI     | 0           |           |
| [raceMask](Mail_level_reward#racemask)             | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [mailTemplateId](Mail_level_reward#mailtemplateid) | mediumint(8) unsigned | NO       |         | 0           |           |
| [senderEntry](Mail_level_reward#senderentry)       | mediumint(8) unsigned | NO       |         | 0           |           |
|                                                    |                       |

### Description of the fields

#### level

Send mail when a character reaches this level.

#### raceMask

Only these races are considered.

#### mailTemplateId

Reference to [MailTemplate.dbc.](MailTemplate.dbc). Containing mail text and subject.

#### senderEntry

Sender of mail. Reference to [creature\_template.entry](creature_template#entry).
