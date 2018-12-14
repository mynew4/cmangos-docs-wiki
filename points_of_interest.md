Back to "world database":mangosdb_struct list of tables.

h2. The `points_of_interest` table

holds points_of_interest information extracted from sniff.

h3. Structure

|*Field*|*Type*|*Attributes*|*Key*|*Null*|*Default*|*Extra*|*Comment*|
|"entry":Points_of_interest#entry|mediumint(8)|unsigned|PRI|NO|0|||
|"x":Points_of_interest#x|float|signed||NO|0|||
|"y":Points_of_interest#y|float|signed||NO|0|||
|"icon":Points_of_interest#icon|mediumint(8)|unsigned||NO|0|||
|"flags":Points_of_interest#flags|mediumint(8)|unsigned||NO|0|||
|"data":Points_of_interest#data|mediumint(8)|unsigned||NO|0|||
|"icon_name":Points_of_interest#icon_name|text|signed||NO|NULL|||

h3. Description of the fields

h4. entry


h4. x


h4. y


h4. icon

|Name|Id|Description|
|ICON_POI_BLANK|0|Blank (not visible)|
|ICON_POI_GREY_AV_MINE|1|Grey mine lorry|
|ICON_POI_RED_AV_MINE|2|Red mine lorry|
|ICON_POI_BLUE_AV_MINE|3|Blue mine lorry|
|ICON_POI_BWTOMB|4|Blue and White Tomb Stone|
|ICON_POI_SMALL_HOUSE|5|Small house|
|ICON_POI_GREYTOWER|6|Grey Tower|
|ICON_POI_REDFLAG|7|Red Flag w/Yellow !|
|ICON_POI_TOMBSTONE|8|Normal tomb stone (brown)|
|ICON_POI_BWTOWER|9|Blue and White Tower|
|ICON_POI_REDTOWER|10|Red Tower|
|ICON_POI_BLUETOWER|11|Blue Tower|
|ICON_POI_RWTOWER|12|Red and White Tower|
|ICON_POI_REDTOMB|13|Red Tomb Stone|
|ICON_POI_RWTOMB|14|Red and White Tomb Stone|
|ICON_POI_BLUETOMB|15|Blue Tomb Stone|
|ICON_POI_16|16|Grey ?|
|ICON_POI_17|17|Blue/White ?|
|ICON_POI_18|18|Blue ?|
|ICON_POI_19|19|Red and White ?|
|ICON_POI_20|20|Red ?|
|ICON_POI_GREYLOGS|21|Grey Wood Logs|
|ICON_POI_BWLOGS|22|Blue and White Wood Logs|
|ICON_POI_BLUELOGS|23|Blue Wood Logs|
|ICON_POI_RWLOGS|24|Red and White Wood Logs|
|ICON_POI_REDLOGS|25|Red Wood Logs|
|ICON_POI_26|26|Grey ?|
|ICON_POI_27|27|Blue and White ?|
|ICON_POI_28|28|Blue ?|
|ICON_POI_29|29|Red and White ?|
|ICON_POI_30|30|Red ?|
|ICON_POI_GREYHOUSE|31|Grey House|
|ICON_POI_BWHOUSE|32|Blue and White House|
|ICON_POI_BLUEHOUSE|33|Blue House|
|ICON_POI_RWHOUSE|34|Red and White House|
|ICON_POI_REDHOUSE|35|Red House|
|ICON_POI_GREYHORSE|36|Grey Horse|
|ICON_POI_BWHORSE|37|Blue and White Horse|
|ICON_POI_BLUEHORSE|38|Blue Horse|
|ICON_POI_RWHORSE|39|Red and White Horse|
|ICON_POI_REDHORSE|40|Red Horse|

h4. flags


h4. data


h4. icon

