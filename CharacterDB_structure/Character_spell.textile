Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;spell` table

Holds information for each character's spells.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_spell#guid|int(11) unsigned|NO|PRI|0||
|"spell":Character_spell#spell|int(11) unsigned|NO|PRI|0||
|"slot":Character_spell#slot|int(11) unsigned|NO||0||
|"active":Character_spell#active|tinyint(3) unsigned|NO||1||


h3. Description of the fields

h4. guid

The GUID of the character. See "character.guid":character#guid

h4. spell

The spell ID. See Spell.dbc column 1

h4. slot

The slot in the spell book that the spell is in.

h4. active

Boolean 1 or 0 signifying whether the spell is active (appears in the spell book).
