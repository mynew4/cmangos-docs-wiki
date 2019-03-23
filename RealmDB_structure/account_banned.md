Back to [realm database](realmdb_struct) list of tables.

The \`account\_banned\` table
-----------------------------

This table lists all of the accounts that have been banned along with the date when (or if) the ban will expire.

### Structure

| **Field**                             | **Type**     | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------|--------------|----------|---------|-------------|-----------|
| [id](Account_banned#id)               | int(11)      | NO       | PRI     | 0           |           |
| [bandate](Account_banned#bandate)     | bigint(40)   | NO       | PRI     | 0           |           |
| [unbandate](Account_banned#unbandate) | bigint(40)   | NO       |         | 0           |           |
| [bannedby](Account_banned#bannedby)   | varchar(50)  | NO       |         |             |           |
| [banreason](Account_banned#banreason) | varchar(255) | NO       |         |             |           |
| [active](Account_banned#active)       | tinyint(4)   | NO       |         | 1           |           |

### Description of the fields

#### id

The account ID. See [account.id](account#id)

#### bandate

The date when the account was banned, in Unix time.

#### unbandate

The date when the account will be automatically unbanned, in Unix time. A value less than the current date means, in effect, a permanent ban.

#### bannedby

The character with the rights to the .ban command that banned the account.

#### banreason

The reason for the ban.

#### active

Boolean 0 or 1 controlling if the ban is currently active or not.

Back to [realm database](realmdb_struct) list of tables.
