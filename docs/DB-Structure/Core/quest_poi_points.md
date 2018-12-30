Back to [world database](mangosdb_struct) list of tables.

The \`quest\_poi\_points\` table
--------------------------------

Comes from sniffs. Visually speaking, this table is used to identify the X and Y coordinates on the map (not the minimap - the main map) where a quest's question mark should appear. Use the ".gps" command where you are standing to find these coordinates. In order to see changes, ".reload quest\_poi", close Wow.exe, then delete your cache folder.

### Structure

| **Field**                           | **Type** | **Attributes** | **Key** | **Null** | **Default** | **Extra** | **Comment** |
|-------------------------------------|----------|----------------|---------|----------|-------------|-----------|-------------|
| [questid](Quest_poi_points#questid) | int(10)  | unsigned       | PRI     | NO       | 0           |           |             |
| [id](Quest_poi_points#id)           | int(10)  | unsigned       | PRI     | NO       | 0           |           |             |
| [idx](Quest_poi_points#idx)         | int(10)  | unsigned       | PRI     | NO       | 0           |           |             |
| [x](Quest_poi_points#x)             | int(10)  | unsigned       |         | NO       | 0           |           |             |
| [y](Quest_poi_points#y)             | int(10)  | unsigned       |         | NO       | 0           |           |             |

### Description of the fields

#### questid

The Quest Id from [quest\_poi.questid](Quest_poi#questid)

#### id

Used to group multiple entries from [quest\_poi.id](Quest_poi#id). You must manually increment this value by 1 for each new row in quest\_poi\_point with the same questId (0, 1, 2, 3...).

#### idx

#### x

The X position of the question mark on the map.

#### y

The Y position of the question mark on the map.
