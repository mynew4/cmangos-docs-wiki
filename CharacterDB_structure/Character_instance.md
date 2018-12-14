Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_instance\` table
---------------------------------

Contains the instance data for characters.

### Structure

| **Field**                                 | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Character_instance#guid)           | int(11) unsigned    | NO       | PRI     | 0           |           |
| [instance](Character_instance#instance)   | bigint(40)          | NO       | MUL     | 0           |           |
| [permanent](Character_instance#permanent) | tinyint(1) unsigned | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### instance

The instance ID. See [instance.id](instance#id)

#### permanent

Boolean 0 or 1 controlling if the player has been bound to the instance. A player is bound to the instance only when he (or his party/raid) kills a creature with the CREATURE\_FLAG\_EXTRA\_INSTANCE\_BIND flag set in the [flags\_extra](creature_template#flags_extra) field.
