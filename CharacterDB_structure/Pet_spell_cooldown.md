Back to "characters database":charactersdb_struct list of tables.

h2. The `pet&#95;spell&#95;cooldown` table

This table holds information on pet spell cooldowns.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Pet_spell_cooldown#guid|int(11) unsigned|NO|PRI|0||
|"spell":Pet_spell_cooldown#spell|int(11) unsigned|NO|PRI|0||
|"time":Pet_spell_cooldown#time|bigint(20) unsigned|NO||0||


h3. Description of the fields

h4. guid

The GUID of the pet. See "character&#95;pet.id":character_pet#id

h4. spell

The spell ID to which the cooldown applies.

h4. time

The time when the cooldown expires, in Unix time.
