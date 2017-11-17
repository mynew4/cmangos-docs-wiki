Back to [world database](https://github.com/cmangos/issues/wiki/Mangosdb_struct) list of tables.

## The `creature_template_spells` table

holds creature spell data, which was previously hold in [creature_template](https://github.com/cmangos/issues/wiki/creature_template) table.

### General Use

TotemAI uses creature_template_spells for spell reference.

Creatures of with creature_template_spells data, which are subject to Mind Control - Spells will hold these Spells as Actions in the Mind Controlers Action Bar.

creature_template_spells data can also give information missing CreatureAI. However, this has to be evaltuated carfully, as creatures might hold spell data, which is either incorrect or has spells inserted which they only have available when possessed.

NOTICE: The data for this table is largely incomplete and is mostly just a regurgitation of what the client receives from the server. This article is a WIP as to what all the possible values are.

### Structure

| Field | Type | Null | Key | Default |
| --- | --- | --- | --- | --- |
|[entry](creature_template_spells#entry)||NO|PRI|0|
|[spell1](creature_template_spells#spell1)||NO||0|
|[spell2](creature_template_spells#spell2)||NO||0|
|[spell3](creature_template_spells#spell3)||NO||0|
|[spell4](creature_template_spells#spell4)||NO||0|

### Description of the fields

#### entry

[`creature_template`.`entry`](Creature_template#entry) of the creature possessing these spells.

#### spell1

[`spell_template`.`id`](spell_template#id) of the spell