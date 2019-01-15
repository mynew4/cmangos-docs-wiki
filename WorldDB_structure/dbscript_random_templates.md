Back to [world database](mangosdb_struct) list of tables.

The \`dbscript\_random\_templates\` table
-----------------------------------------

Use this table to set up an infinite amount of texts or relay scripts to be randomized in the same action. Used in SCRIPT\_COMMAND\_TALK, SCRIPT\_COMMAND\_START\_RELAY\_SCRIPT, ACTION\_T\_TEXT\_NEW and ACTION\_T\_START\_RELAY\_SCRIPT

### Structure

| **Field**                                         | **Type**         | **Null** | **Key** | **Default** | **Extra**                        |
|---------------------------------------------------|------------------|----------|---------|-------------|----------------------------------|
| [id](dbscript_random_templates#id)                | int(11) unsigned | NO       | PRI     | No default  | Id of template                   |
| [type](dbscript_random_templates#type)            | int(11) unsigned | NO       | PRI     | No default  | Type of template                 |
| [target\_id](dbscript_random_templates#target_id) | int(11)          | NO       | PRI     | 0           | Id of chanced element            |
| [chance](dbscript_random_templates#chance)        | int(11)          | NO       |         | 0           | Chance for element to occur in % |
| [comments](dbscript_random_templates#comments)    | varchar(500)     | Yes      |         | ''          |                                  |

### Description of the fields

#### id

The ID of the random template.<br>
Similar to dbscripts\_on\_relay the ID is assigned depending on which expansion it is used in:

* Vanilla - 1-9999
* TBC - 10000-19999
* WotLK - 20000+

#### type

0 = DBScript\_string or creature\_ai\_texts string<br>
1 = DBScripts\_on\_relay

#### target\_id

If type = 0: The string entry from [dbscript\_string.entry](Dbscript_string#entry) or [creature\_ai\_texts.entry](Creature_ai_texts#entry)<br>
If type = 1: The dbscripts\_on\_relay ID you want to randomize

#### chance

The chance in % for the string or relay script to occur

#### comment

Provide a useful comment to help out yourself and other developers who may come across your work
