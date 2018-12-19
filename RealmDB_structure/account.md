Back to [realm database](realmdb_struct) list of tables.

The \`account\` table
---------------------

This table holds information on all available accounts.

### Structure

| **Field**                                | **Type**            | **Null** | **Key** | **Default**         | **Extra**       |
|------------------------------------------|---------------------|----------|---------|---------------------|-----------------|
| [id](Account#id)                         | bigint(20) unsigned | NO       | PRI     |                     | auto\_increment |
| [username](Account#username)             | varchar(32)         | NO       | UNI     |                     |                 |
| [sha\_pass\_hash](Account#sha_pass_hash) | varchar(40)         | NO       |         |                     |                 |
| [gmlevel](Account#gmlevel)               | tinyint(3) unsigned | NO       | MUL     | 0                   |                 |
| [sessionkey](Account#sessionkey)         | longtext            | YES      |         |                     |                 |
| [v](Account#v)                           | longtext            | YES      |         |                     |                 |
| [s](Account#s)                           | longtext            | YES      |         |                     |                 |
| [email](Account#email)                   | varchar(255)        | NO       |         |                     |                 |
| [joindate](Account#joindate)             | timestamp           | NO       |         | CURRENT\_TIMESTAMP  |                 |
| [last\_ip](Account#last_ip)              | varchar(30)         | NO       |         | 127.0.0.1           |                 |
| [failed\_logins](Account#failed_logins)  | int(11) unsigned    | NO       |         | 0                   |                 |
| [locked](Account#locked)                 | tinyint(3) unsigned | NO       |         | 0                   |                 |
| [last\_login](Account#last_login)        | timestamp           | NO       |         | 0000-00-00 00:00:00 |                 |
| [online](Account#online)                 | tinyint(4)          | NO       |         | 0                   |                 |
| [expansion](Account#expansion)           | tinyint(3) unsigned | NO       |         | 0                   |                 |
| [mutetime](Account#mutetime)             | bigint(40) unsigned | NO       |         | 0                   |                 |
| [locale](Account#locale)                 | tinyint(3) unsigned | NO       |         | 0                   |                 |

### Description of the fields

#### id

The unique account ID.

#### username

The account user name.

#### sha\_pass\_hash

This field contains the encrypted password. The encryption is SHA1 and is in the following format: username:password. The SQL to create the password (or to compare with the current hash) is:

    SELECT SHA1(CONCAT(UPPER(`username`), ':', UPPER(<pass>)));

#### gmlevel

The account security level. Different levels have access to different commands. The individual level required for a command is defined in the [command](command) table.

#### sessionkey

#### v

#### s

#### email

The e-mail address associated with this account.

#### joindate

The date when the account was created.

#### last\_ip

The last IP used by the person who logged in the account.

#### failed\_logins

The number of failed logins attempted on the account.

#### locked

Boolean 0 or 1 controlling if the account has been locked or not.

#### last\_login

The date when the account was last logged into.

#### online

Boolean 0 or 1 controlling if the account is currently logged in and online.

#### expansion

| **ID** | **Expansion**              |
|--------|----------------------------|
| 0      | WoW Classic                |
| 1      | WoW Burning Crusade        |
| 2      | WoW Wrath of the Lich King |

The world server will block access to accounts with 0 in this field in the TBC and WotLK areas in-game.

The world server will block access to accounts with 1 in this field in the WotLK areas in-game.

#### mutetime

The time, in Unix time, when the account will be unmuted.

#### locale

The locale used by the client logged into this account. If multiple locale data has been configured and added to the world servers, the world servers will return the proper locale strings to the client. See [localization IDs](localization_lang)

[Category: Realm database tables](Category): Realm database tables
