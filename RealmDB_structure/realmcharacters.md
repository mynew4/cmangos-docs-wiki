Back to [realm database](realmdb_struct) list of tables.

The \`realmcharacters\` table
-----------------------------

This table holds information on the number of characters each account has for each realm.

### Structure

| **Field**                            | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------|---------------------|----------|---------|-------------|-----------|
| [realmid](Realmcharacters#realmid)   | int(11) unsigned    | NO       | PRI     | 0           |           |
| [acctid](Realmcharacters#acctid)     | bigint(20) unsigned | NO       | PRI     |             |           |
| [numchars](Realmcharacters#numchars) | tinyint(3) unsigned | NO       |         | 0           |           |

### Description of the fields

#### realmid

The ID of the realm. See [realmlist.id](realmlist#id)

#### acctid

The account ID. See [account.id](account#id)

#### numchars

The number of characters the account has on the realm.

Back to [realm database](realmdb_struct) list of tables.
