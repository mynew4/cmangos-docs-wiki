Back to [realm database](realmdb_struct) list of tables.

The \`ip\_banned\` table
------------------------

This table contains all of the banned IPs and the date when (or if) the ban will expire.

### Structure

| **Field**                        | **Type**    | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------|-------------|----------|---------|-------------|-----------|
| [ip](Ip_banned#ip)               | varchar(32) | NO       | PRI     | 127.0.0.1   |           |
| [bandate](Ip_banned#bandate)     | int(11)     | NO       |         |             |           |
| [unbandate](Ip_banned#unbandate) | int(11)     | NO       |         |             |           |
| [bannedby](Ip_banned#bannedby)   | varchar(50) | NO       |         | \[Console\] |           |
| [banreason](Ip_banned#banreason) | varchar(50) | NO       |         | no reason   |           |

### Description of the fields

#### ip

The IP address that is banned.

#### bandate

The date when the IP was first banned, in Unix time.

#### unbandate

The date when the IP will be unbanned in Unix time. Any date that is set lower than the current date basically classifies as a permanent ban as it will never auto expire.

#### bannedby

The name of the character that banned the IP. The character should belong to an account with the rights to the .ban command in-game.

#### banreason

The reason given for the IP ban.

Back to [realm database](realmdb_struct) list of tables.
