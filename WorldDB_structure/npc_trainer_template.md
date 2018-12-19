Back to [world database](mangosdb_struct) list of tables.

The \`npc\_trainer(\_template)\` table
--------------------------------------

This table holds all the information on training NPCs. All spells listed in the table are learning spells. This means that the main effect of the spells listed here is to teach spells to the target (which is the player in this case). Any other spell that is not a learning spell will be ignored and an error message will be shown in the console window. Learning spells usually have the same name as their actual spell counterparts and are listed as Uncategorized in Wowhead.

### Structure

| **Field**                                           | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](npc_trainer_template#entry)                 | int(11)          | NO       | PRI     | 0           |           |
| [spell](npc_trainer_template#spell)                 | int(11)          | NO       | PRI     | 0           |           |
| [spellcost](npc_trainer_template#spellcost)         | int(11)          | YES      |         | 0           |           |
| [reqskill](npc_trainer_template#reqskill)           | int(10) unsigned | YES      |         | 0           |           |
| [reqskillvalue](npc_trainer_template#reqskillvalue) | int(10) unsigned | YES      |         | 0           |           |
| [reqlevel](npc_trainer_template#reqlevel)           | int(10) unsigned | YES      |         | 0           |           |

### Description of the fields

#### entry

[creature\_template.entry](creature_template#entry) for npc\_trainer (unique trainers which share no npc\_trainer\_template with other entries)

[creature\_template.trainertemplateid](creature_template#trainertemplateid) for npc\_trainer\_template

#### spell

The learning spell ID.

#### spellcost

The cost that the player needs to pay in order to learn the spell.

#### reqskill

The required skill the player needs to have in order to be able to learn the spell. See ID in SkillLine.dbc

#### reqskillvalue

The proficiency in the skill from [reqskill](#reqskill) that the player needs to meet in order to learn the spell.

#### reqlevel

The level the player needs to be in order to learn the spell.
