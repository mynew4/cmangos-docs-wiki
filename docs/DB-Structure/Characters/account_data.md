Back to the [characters database](charactersdb_struct) list of tables.

The \`account\_data\` table
---------------------------

This table holds addition data for each account.

### Structure

| **Field**                       | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------|---------------------|----------|---------|-------------|-----------|
| [account](Account_data#account) | int(11) unsigned    | NO       | PRIMARY | 0           |           |
| [type](Account_data#type)       | int(11) unsigned    | NO       | PRIMARY | 0           |           |
| [time](Account_data#time)       | bigint(11) unsigned | NO       |         | 0           |           |
| [data](Account_data#data)       | longtext            | NO       |         |             |           |

#### account

The account ID in which this character resides. See [Account.id](Account#id) in the realm database.

#### type

#### time

#### data
