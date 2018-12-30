Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_gifts\` table
------------------------------

This table holds data about wrapped/gift items.

### Structure

| **Field**                               | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Character_gifts#guid)            | int(20) unsigned | NO       | MUL     | 0           |           |
| [item\_guid](Character_gifts#item_guid) | int(11) unsigned | NO       | PRI     | 0           |           |
| [entry](Character_gifts#entry)          | int(20) unsigned | NO       |         | 0           |           |
| [flags](Character_gifts#flags)          | int(20) unsigned | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### item\_guid

The GUID of the item. See [item\_instance.guid](item_instance#guid)

#### entry

The entry of the item. See [item\_template.entry](item_template#entry)

#### flags
