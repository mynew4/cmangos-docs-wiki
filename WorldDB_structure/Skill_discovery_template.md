Back to "world database":mangosdb_struct list of tables.

h2. The `skill&#95;discovery&#95;template` table

This table controls the so called &quot;discovery&quot; system of learning spells. This system is solely (?) used by the alchemy profession and controls the chance for a player to &quot;discover&quot; another recipe while creating items with other recipes.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"spellId":Skill_discovery_template#spellid|int(11) unsigned|NO|PRI|0||
|"reqSpell":Skill_discovery_template#reqspell|int(11) unsigned|NO||0||
|"chance":Skill_discovery_template#chance|float|NO||0||


h3. Description of the fields

h4. spellId

The recipe spell ID that has a chance to be automatically discovered. See Spell.dbc

h4. reqSpell

If nonzero, this field controls what spell must be specifically used to trigger the discovery (eg, spell 41458 will only be discovered while using spell 28575). If it is zero, then any recipe use can trigger the discovery. See Spell.dbc

h4. chance

The chance, in percent, that a recipe has of being automatically &quot;discovered&quot;, whether by any recipe use or by the specific recipe use defined in "reqSpell":#reqSpell
