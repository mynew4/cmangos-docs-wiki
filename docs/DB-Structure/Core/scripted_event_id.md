Back to [world database](mangosdb_struct) list of tables.

The \`scriped\_event\_id\` table
--------------------------------

This table links event id's to C\*\* scripts.

### Structure

| Field                                      | Type          | NULL | Key | Default | Comments          |
|--------------------------------------------|---------------|------|-----|---------|-------------------|
| [entry](Scripted_event_id#entry)           | mediumint (8) | NO   | PRI |         | Identifier        |
| [ScriptName](Scripted_event_id#scriptname) | CHAR (64)     | NO   |     |         | Script Identifier |

### Description of the fields

#### entry

This is the event id identifier

#### ScriptName

The name of the script that this event uses, if any. This ties a script from a scripting engine to this trigger.
