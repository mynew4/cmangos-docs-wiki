Back to "dbc files":dbc_files list.

h3. GlyphSlot.dbc

New DBC file from WotLK, handles glyph slot IDs.

*Version is : 3.3.5a*



|*Column*|*Name*|Type|
|1|ID|Integer|
|2|TypeFlags|Integer|
|3|Order|Integer|





<hr />

h3. *Content*


|ID|TypeFlags|Order|
|1|4|0|
|2|2|0|
|3|3|0|
|4|0|0|
|21|0|1|
|22|1|2|
|23|1|3|
|24|0|4|
|25|1|5|
|26|0|6|





h4. ID

The Glyph Slot ID. Slot 21-26 are the normal character glyph slots. 1-4 are left over from development and are unused.

h4. TypeFlags

The type of glyph. 0 is major, 1 is minor. 2, 3, and 4 still seem to have no use and are left over from development.

h4. Order

The order the glyph slots are displayed on the character's glyph tab. 1 is the top middle, then 2-6 are respective glyphs going clockwise.
