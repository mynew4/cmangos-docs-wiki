Back to "world database":mangosdb_struct list of tables.

h2. The `spell&#95;threat` table

This table holds threat values on all spells that should either give or take away threat.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Spell_threat#entry|int(10) unsigned|NO|PRI|||
|"Threat":Spell_threat#threat|int(11)|NO||||
|"multiplier":Spell_threat#multiplier|float|NO||||
|"ap_bonus":Spell_threat#ap_bonus|float|NO||||


h3. Description of the fields

h4. entry

The spell ID. See Spell.dbc

h4. Threat

The threat value that this spells should add to the caster (or take away if it is negative).

h4. multiplier

The threat multiplier for damage/healing

h4. ap_bonus

Additional threat bonus from attack power
