Back to "world database":mangosdb_struct list of tables.

h2. The `game&#95;weather` table

This table holds the percentages for weather changes in various zones. Not all zones can have their weather changed. For any given zone the percentage of all weather types for each season should total, and not exceed 100%.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"zone":Game_weather#zone|int(10) unsigned|NO|PRI|0||
|"spring_rain_chance":Game_weather#spring_rain_chance|tinyint(3) unsigned|NO||25||
|"spring_snow_chance":Game_weather#spring_snow_chance|tinyint(3) unsigned|NO||25||
|"spring_storm_chance":Game_weather#spring_storm_chance|tinyint(3) unsigned|NO||25||
|"summer_rain_chance":Game_weather#summer_rain_chance|tinyint(3) unsigned|NO||25||
|"summer_snow_chance":Game_weather#summer_snow_chance|tinyint(3) unsigned|NO||25||
|"summer_storm_chance":Game_weather#summer_storm_chance|tinyint(3) unsigned|NO||25||
|"fall_rain_chance":Game_weather#fall_rain_chance|tinyint(3) unsigned|NO||25||
|"fall_snow_chance":Game_weather#fall_snow_chance|tinyint(3) unsigned|NO||25||
|"fall_storm_chance":Game_weather#fall_storm_chance|tinyint(3) unsigned|NO||25||
|"winter_rain_chance":Game_weather#winter_rain_chance|tinyint(3) unsigned|NO||25||
|"winter_snow_chance":Game_weather#winter_snow_chance|tinyint(3) unsigned|NO||25||
|"winter_storm_chance":Game_weather#winter_storm_chance|tinyint(3) unsigned|NO||25||


h3. Description of the fields

h4. zone

This field contains the zone id from "AreaTable.dbc":AreaTable.dbc that you wish to change the weather for.

h4. spring&#95;rain&#95;chance

Percentage chance for rain in the Spring

h4. spring&#95;snow&#95;chance

Percentage chance for snow in the Spring

h4. spring&#95;storm&#95;chance

Percentage chance for a sand storm in the Spring

h4. summer&#95;rain&#95;chance

Percentage chance for rain in the Summer

h4. summer&#95;snow&#95;chance

Percentage chance for snow in the Summer

h4. summer&#95;storm&#95;chance

Percentage chance for a sand storm in the Summer

h4. fall&#95;rain&#95;chance

Percentage chance for rain in the Fall

h4. fall&#95;snow&#95;chance

Percentage chance for snow in the Fall

h4. fall&#95;storm&#95;chance

Percentage chance for a sand storm in the Fall

h4. winter&#95;rain&#95;chance

Percentage chance for rain in the Winter

h4. winter&#95;snow&#95;chance

Percentage chance for snow in the Winter

h4. winter&#95;storm&#95;chance

Percentage chance for a sand storm in the Winter
