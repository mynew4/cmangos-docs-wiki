Back to [world database](mangosdb_struct) list of tables.

The \`battlemaster\_entry\` table
---------------------------------

Holds information on which NPC can start what battleground or arena.

### Structure

| **Field**                                      | **Type**              | **Null** | **Key** | **Default** | **Extra**                |
|------------------------------------------------|-----------------------|----------|---------|-------------|--------------------------|
| [entry](Battlemaster_entry#entry)              | mediumint(8) unsigned | NO       | PRI     | 0           | Entry of a creature      |
| [bg\_template](Battlemaster_entry#bg_template) | mediumint(8) unsigned | NO       |         | 0           | Battleground template id |

### Description of the fields

#### entry

The ID of the creature. See [creature\_template.entry](creature_template#entry)

#### bg\_template

The battleground template ID. See [Battleground\_template](Battleground_template)
