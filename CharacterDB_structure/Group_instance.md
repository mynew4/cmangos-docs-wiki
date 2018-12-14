Back to the [characters database](charactersdb_struct) list of tables.

The \`group\_instance\` table
-----------------------------

### Structure

| **Field**                             | **Type**   | **Attributes** | **Key** | **Null** | **Default** | **Extra** | **Comment** |
|---------------------------------------|------------|----------------|---------|----------|-------------|-----------|-------------|
| [guid](Group_instance#guid)           | int(10)    | unsigned       | PRI     | NO       | 0           |           |             |
| [instance](Group_instance#instance)   | int(10)    | unsigned       | PRI     | NO       | 0           |           |             |
| [permanent](Group_instance#permanent) | tinyint(3) | unsigned       |         | NO       | 0           |           |             |

### Description of the fields

#### guid

[Guid](groups#guid) of the group.

#### instance

ID of the Instance session the group has enterd.

#### permanent

Boolean flag if the group is bound to the Instance or not.
