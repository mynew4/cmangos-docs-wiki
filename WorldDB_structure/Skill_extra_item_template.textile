Back to "world database":mangosdb_struct list of tables.

h2. The `skill&#95;extra&#95;item&#95;template` table

This table holds information about when using certain profession spells, you have the chance of creating more than one copy of the item.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"spellId":Skill_extra_item_template#spellid|int(11) unsigned|NO|PRI|0||
|"requiredSpecialization":Skill_extra_item_template#requiredspecialization|int(11) unsigned|NO||0||
|"additionalCreateChance":Skill_extra_item_template#additionalcreatechance|float|NO||0||
|"additionalMaxNum":Skill_extra_item_template#additionalmaxnum|int(11) unsigned|NO||0||


h3. Description of the fields

h4. spellId

The spell ID that creates the item. See Spell.dbc

h4. requiredSpecialization

The required specialization spell ID. The character must have the spell ID specified here learned to have a chance at making another item instantly.

h4. additionalCreateChance

The chance that the player will make another item instantly.

h4. additionalMaxNum

The number of extra copies that can be made.
