Back to "world database":mangosdb_struct list of tables.

h2. The `quest&#95;poi` table

Comes from sniffs.

h3. Structure


|*Field*|*Type*|*Attributes*|*Key*|*Null*|*Default*|*Extra*|*Comment*|
|"questid":Quest_poi#questid|int(10)|unsigned|PRI|NO|0|||
|"id":Quest_poi#id|int(10)|unsigned|PRI|NO|0|||
|"objIndex":Quest_poi#objindex|int(10)|unsigned||NO|0|||
|"mapid":Quest_poi#mapid|int(10)|unsigned||NO|0|||
|"WorldMapAreaId":Quest_poi#worldmapareaid|int(10)|unsigned||NO|0|||
|"FloorId":Quest_poi#floorid|int(10)|unsigned||NO|0|||
|"unk3":Quest_poi#unk3|int(10)|unsigned||NO|0|||
|"unk4":Quest_poi#unk4|int(10)|unsigned||NO|0|||


h3. Description of the fields

h4. questid

The Quest Id from "quest&#95;template.id":Quest_template#entidry .

h4. id

Used to group multiple entries from "quest&#95;poi&#95;points.id":Quest_poi_points#id it is the id of the POI.

h4. objIndex

if -1 than position of npc where you can complete quest

h4. mapid

The Map id from "Map.dbc":Map.dbc

h4. WorldMapAreaId

The area ID from "AreaTable.dbc":AreaTable.dbc

h4. FloorId

This is the AreaID of the POI.

h4. unk3


h4. unk4

