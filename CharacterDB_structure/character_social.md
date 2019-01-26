Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_social\` table
-------------------------------

Contains data about characters' friends/ignored list.

### Structure

| **Field**                         | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Character_social#guid)     | int(11) unsigned | NO       | PRI     | 0           |           |
| [name](Character_social#name)     | varchar(21)      | NO       |         |             |           |
| [friend](Character_social#friend) | int(11) unsigned | NO       | PRI     | 0           |           |
| [flags](Character_social#flags)   | varchar(21)      | NO       | PRI     |             |           |

### Description of the fields

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### name

The name of the friend/ignored. See [characters.name](characters#name)

#### friend

The GUID of the friend/ignored. See [characters.guid](characters#guid)

#### flags

0 = Friend<br>
1 = Ignored
