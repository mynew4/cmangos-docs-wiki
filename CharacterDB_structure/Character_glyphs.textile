Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;glyphs` table

Contains all the individual glyph data for each character.

h3. Structure


|*Field*|*Type*|*Attributes*|*Key*|*Null*|*Default*|*Extra*|*Comment*|
|"guid":Character_glyphs#guid|int(10)|unsigned|PRI|NO||||
|"slot":Character_glyphs#slot|tinyint(3)|unsigned|PRI|NO|0|||
|"glyph":Character_glyphs#glyph|smallint(5)|unsigned||YES|0|||
||


h3. Description of the fields

h4. guid

The GUID of the character. See "characters.guid":characters#guid

h4. spec

spec = 0 is the first spec, spec = 1 is the second spec.

h4. glyph

The "GlyphProperties":GlyphProperties.dbc#Entry entry of the glyph in that particular spec.
