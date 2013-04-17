Back to "world database":mangosdb_struct list of tables.

h2. The `petcreateinfo&#95;spell` table

This table controls what spells a tameable beast will have once tamed. It also controls the passive auras that the pet will get.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Petcreateinfo_spell#entry|int(11) unsigned|NO|PRI|0||
|"Spell1":Petcreateinfo_spell#spelln|int(11) unsigned|NO||0||
|"Spell2":Petcreateinfo_spell#spelln|int(11) unsigned|NO||0||
|"Spell3":Petcreateinfo_spell#spelln|int(11) unsigned|NO||0||
|"Spell4":Petcreateinfo_spell#spelln|int(11) unsigned|NO||0||
||


h3. Description of the fields

h4. entry

The template ID of the beast. See "creature&#95;template.entry":creature_template#entry

h4. SpellN

The spell that the pet will have automatically in its pet bar once tamed. Also, the spells in this field need to be &quot;learn&quot; spells because the hunter character will learn the spells so that they can teach other pets those spells. See Spell.dbc
