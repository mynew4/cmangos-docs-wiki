Back to [world database](mangosdb_struct) list of tables.

The \`gameobject\_involvedrelation\` table
------------------------------------------

Holds game object quest taker relations. The game objects in this table should all be of type QUESTGIVER (2).

### Structure

| **Field**                                  | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|--------------------------------------------|------------------|----------|---------|-------------|-----------|
| [id](Gameobject_involvedrelation#id)       | int(10) unsigned | NO       | PRI     | 0           |           |
| [quest](Gameobject_involvedrelation#quest) | int(10) unsigned | NO       | PRI     | 0           |           |

### Description of the fields

#### id

The template ID of the game object. See [gameobject\_template.entry](gameobject_template#entry)

#### quest

The quest ID that this game object finishes. See [quest\_template.entry](quest_template#entry)
