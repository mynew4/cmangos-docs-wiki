Back to [world database](mangosdb_struct) list of tables.

The \`quest\_poi\` table
------------------------

Comes from sniffs.

### Structure

| **Field**                                  | **Type** | **Attributes** | **Key** | **Null** | **Default** | **Extra** | **Comment** |
|--------------------------------------------|----------|----------------|---------|----------|-------------|-----------|-------------|
| [questid](Quest_poi#questid)               | int(10)  | unsigned       | PRI     | NO       | 0           |           |             |
| [id](Quest_poi#id)                         | int(10)  | unsigned       | PRI     | NO       | 0           |           |             |
| [objIndex](Quest_poi#objindex)             | int(10)  | unsigned       |         | NO       | 0           |           |             |
| [mapid](Quest_poi#mapid)                   | int(10)  | unsigned       |         | NO       | 0           |           |             |
| [WorldMapAreaId](Quest_poi#worldmapareaid) | int(10)  | unsigned       |         | NO       | 0           |           |             |
| [FloorId](Quest_poi#floorid)               | int(10)  | unsigned       |         | NO       | 0           |           |             |
| [unk3](Quest_poi#unk3)                     | int(10)  | unsigned       |         | NO       | 0           |           |             |
| [unk4](Quest_poi#unk4)                     | int(10)  | unsigned       |         | NO       | 0           |           |             |

### Description of the fields

#### questid

The Quest Id from [quest\_template.id](Quest_template#entidry) .

#### id

Used to group multiple entries from [quest\_poi\_points.id](Quest_poi_points#id) it is the id of the POI.

#### objIndex

if -1 than position of npc where you can complete quest

#### mapid

The Map id from [Map.dbc](Map.dbc)

#### WorldMapAreaId

The area ID from [AreaTable.dbc](AreaTable.dbc)

#### FloorId

This is the AreaID of the POI.

#### unk3

#### unk4
