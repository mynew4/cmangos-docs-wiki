Back to "world database":mangosdb_struct list of tables.

h2. The `spell&#95;area` table

This table holds information on what spells are applied to npcs/players in some areas.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"spell":Spell_area#spell|mediumint(8) unsigned|NO|PRI|0||
|"area":Spell_area#area|mediumint(8) unsigned|NO|PRI|0||
|"quest_start":Spell_area#quest_start|mediumint(8) unsigned|NO|PRI|0||
|"quest_start_active":Spell_area#quest_start_active|tinyint(1) unsigned|NO|PRI|0||
|"quest_end":Spell_area#quest_end|mediumint(8) unsigned|NO||0||
|"condition_id":Spell_area#condition_id|mediumint(8)|NO|PRI|0||
|"aura_spell":Spell_area#aura_spell|mediumint(8)|NO|PRI|0||
|"racemask":Spell_area#racemask|mediumint(8) unsigned|NO|PRI|0||
|"gender":Spell_area#gender|tinyint(1) unsigned|NO|PRI|2||
|"autocast":Spell_area#autocast|tinyint(1) unsigned|NO||0||


h3. Description of the fields

h4. spell

The spell ID that will be castet. Reference to "Spell.dbc.":Spell.dbc.

h4. area

Reference to "AreaTable.dbc.":AreaTable.dbc. Player must be in this area.

h4. quest&#95;start

Reference to "quest_template.":quest_template. This quest must be available or active and must not be completed. Exact behaviour depends on "quest&#95;start&#95;active":spell_area#quest_start_active.

h4. quest&#95;start&#95;active

Boolean value. If set to 0 the quest "quest&#95;start":spell_area#quest_start must be available and not activ. If set to 1 the quest "quest&#95;start":spell_area#quest_start must be available or active in players' log.

h4. quest&#95;end

Reference to "quest_template.":quest_template. This quest must not be completed.

h4. condition_id

Reference to "conditions.":conditions.

h4. aura&#95;spell

Reference to "Spell.dbc.":Spell.dbc. Player must have this aura to activate the spell. Negativ values stand for &quot;not has aura&quot; requirement.

h4. racemask

Only these races are target of the spell.

*Race*

These values are 2^ID taken from "CharRaces.dbc":CharRaces.dbc 

<big>Examples</big>

0,1791 = All Races

(2 + 16 + 32 + 128 + 512) = 690 = only Horde

(1 + 4 + 8 + 64 + 1024) = 1101 = only Alliance

h4. gender

Only this gender is target of the spell.

* 0: Male
* 1: Female
* 2: Both

h4. autocast

Boolean value.
