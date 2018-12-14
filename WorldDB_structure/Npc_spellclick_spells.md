Back to "world database":mangosdb_struct list of tables.

h2. The `npc&#95;spellclick&#95;spells` table

This table holds information about spells to be casted upon receiving CMSG&#95;SPELLCLICK. That opcode is sent for quests in which you have to loot creatures, who are already dead at spawning. Examples are "Planning for the Future":http://thottbot.com/q11960 and "Rifle the bodies":http://thottbot.com/q11999.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"npc_entry":Npc_spellclick_spells#npc_entry|int(10) unsigned|NO||||
|"spell_id":Npc_spellclick_spells#spell_id|int(10) unsigned|NO||||
|"quest_start":Npc_spellclick_spells#quest_start|mediumint(8) unsigned|NO||0||
|"quest_start_active":Npc_spellclick_spells#quest_start_active|tinyint(1) unsigned|NO||0||
|"quest_end":Npc_spellclick_spells#quest_end|mediumint(3) unsigned|NO||0||
|"cast_flags":Npc_spellclick_spells#cast_flags|tinyint(3) unsigned|NO||||
|"condition_id":Npc_spellclick_spells#condition_id|mediumint(8) unsigned|NO||0||

*Note:* The fields quest_* are obsolete and will be removed

h3. Description of the fields

h4. npc&#95;entry

Reference to "Creature_template#entry":Creature_template#entry

h4. spell&#95;id

The spell which should be casted.

Note that for several quests there are more than one spell per click. "Planing for the Future":http://thottbot.com/q11960 for example has "Planning for the Future: Create Snowfall Glade Pup":http://thottbot.com/s46773 which will create the item in the player's inventory and "Planning for the Future: Create Snowfall Glade Pup Cover":http://thottbot.com/s46167 which despawns the creature.

This creates the illusion that the creature has been looted.

h4. quest&#95;start

Same as "Spell_area#quest_start.":Spell_area#quest_start.

h4. quest&#95;start&#95;active

Same as "Spell_area#quest_start_active.":Spell_area#quest_start_active.

h4. quest&#95;end

Same as "Spell_area#quest_end.":Spell_area#quest_end.

h4. cast&#95;flags

On every spellclick event a player and a creature &quot;participate&quot;. This field defines who casts the spell on who.

Lower bit defines caster: 1=player, 0=creature; higher bit defines target, same mapping as caster bit.

You can use that table for the actual value:

|*cast&#95;flags value*|*Caster*|*Target*|
|0|Creature|Creature|
|1|Player|Creature|
|2|Creature|Player|
|3|Player|Player|

h4. condition&#95;id

Value that represents a "condition":Conditions#condition_entry that must be met in order for the item to drop.
See "Conditions table":Conditions for detailed description.

Note: If set != 0 it will override any meaning within the quest_* fields.
