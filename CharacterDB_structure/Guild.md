Back to [characters database](charactersdb_struct) list of tables.

The \`guild\` table
-------------------

This table holds the main guild information. All created guilds or all guilds in the process of being created have a record in this table.

### Structure

| **Field**                                | **Type**        | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------|-----------------|----------|---------|-------------|-----------|
| [guildid](Guild#guildid)                 | int(6) unsigned | NO       | PRI     | 0           |           |
| [name](Guild#name)                       | varchar(255)    | NO       |         |             |           |
| [leaderguid](Guild#leaderguid)           | int(6) unsigned | NO       |         | 0           |           |
| [EmblemStyle](Guild#emblemstyle)         | int(5)          | NO       |         | 0           |           |
| [EmblemColor](Guild#emblemcolor)         | int(5)          | NO       |         | 0           |           |
| [BorderStyle](Guild#borderstyle)         | int(5)          | NO       |         | 0           |           |
| [BorderColor](Guild#bordercolor)         | int(5)          | NO       |         | 0           |           |
| [BackgroundColor](Guild#backgroundcolor) | int(5)          | NO       |         | 0           |           |
| [info](Guild#info)                       | text            | NO       |         |             |           |
| [motd](Guild#motd)                       | varchar(255)    | NO       |         |             |           |
| [createdate](Guild#createdate)           | datetime        | YES      |         |             |           |
| [BankMoney](Guild#bankmoney)             | bigint(20)      | NO       |         | 0           |           |

### Description of the fields

#### guildid

The ID of the guild. This number is unique to each guild and is the main method to identify a guild.

#### name

The guild name.

#### leaderguid

The GUID of the character who created the guild. See [character.guid](character#guid)

#### EmblemStyle

The emblem style of the guild tabard.

#### EmblemColor

The emblem color of the guild tabard.

#### BorderStyle

The border style of the guild tabard.

#### BorderColor

The border color of the guild tabard.

#### BackgroundColor

The background color of the guild tabard.

#### info

The text message that appears in the Guild Information box.

#### motd

The text that appears in the Message Of The Day box.

#### createdate

The date when the guild was created.

#### BankMoney

The total money, in copper, that is currently in the guild's guild bank.
