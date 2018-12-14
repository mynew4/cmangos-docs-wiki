Back to [world database](mangosdb_struct) list of tables.

The \`scripted\_areatrigger\` table
-----------------------------------

This table links areatriggers to C\*\* scripts.

### Structure

| Field                                         | Type          | NULL | Key | Default | Comments          |
|-----------------------------------------------|---------------|------|-----|---------|-------------------|
| [entry](Scripted_areatrigger#entry)           | mediumint (8) | NO   | PRI |         | Identifier        |
| [ScriptName](Scripted_areatrigger#scriptname) | CHAR (64)     | NO   |     |         | Script Identifier |

### Description of the fields

#### entry

This is the trigger identifier from AreaTrigger.dbc

#### ScriptName

The name of the script that this areatrigger uses, if any. This ties a script from a scripting engine to this trigger.
