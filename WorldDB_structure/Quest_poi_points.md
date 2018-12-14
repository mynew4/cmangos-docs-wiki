Back to "world database":mangosdb_struct list of tables.

h2. The `quest&#95;poi&#95;points` table

Comes from sniffs. Visually speaking, this table is used to identify the X and Y coordinates on the map (not the minimap - the main map) where a quest's question mark should appear. Use the &quot;.gps&quot; command where you are standing to find these coordinates. In order to see changes, &quot;.reload quest&#95;poi&quot;, close Wow.exe, then delete your cache folder.

h3. Structure


|*Field*|*Type*|*Attributes*|*Key*|*Null*|*Default*|*Extra*|*Comment*|
|"questid":Quest_poi_points#questid|int(10)|unsigned|PRI|NO|0|||
|"id":Quest_poi_points#id|int(10)|unsigned|PRI|NO|0|||
|"idx":Quest_poi_points#idx|int(10)|unsigned|PRI|NO|0|||
|"x":Quest_poi_points#x|int(10)|unsigned||NO|0|||
|"y":Quest_poi_points#y|int(10)|unsigned||NO|0|||


h3. Description of the fields

h4. questid

The Quest Id from "quest&#95;poi.questid":Quest_poi#questid

h4. id

Used to group multiple entries from "quest&#95;poi.id":Quest_poi#id. You must manually increment this value by 1 for each new row in quest&#95;poi&#95;point with the same questId (0, 1, 2, 3...).

h4. idx


h4. x

The X position of the question mark on the map.

h4. y

The Y position of the question mark on the map.
