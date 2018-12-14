Back to [world database](mangosdb_struct) list of tables.

The \`game\_weather\` table
---------------------------

This table holds the percentages for weather changes in various zones. Not all zones can have their weather changed. For any given zone the percentage of all weather types for each season should total, and not exceed 100%.

### Structure

| **Field**                                                 | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [zone](Game_weather#zone)                                 | int(10) unsigned    | NO       | PRI     | 0           |           |
| [spring\_rain\_chance](Game_weather#spring_rain_chance)   | tinyint(3) unsigned | NO       |         | 25          |           |
| [spring\_snow\_chance](Game_weather#spring_snow_chance)   | tinyint(3) unsigned | NO       |         | 25          |           |
| [spring\_storm\_chance](Game_weather#spring_storm_chance) | tinyint(3) unsigned | NO       |         | 25          |           |
| [summer\_rain\_chance](Game_weather#summer_rain_chance)   | tinyint(3) unsigned | NO       |         | 25          |           |
| [summer\_snow\_chance](Game_weather#summer_snow_chance)   | tinyint(3) unsigned | NO       |         | 25          |           |
| [summer\_storm\_chance](Game_weather#summer_storm_chance) | tinyint(3) unsigned | NO       |         | 25          |           |
| [fall\_rain\_chance](Game_weather#fall_rain_chance)       | tinyint(3) unsigned | NO       |         | 25          |           |
| [fall\_snow\_chance](Game_weather#fall_snow_chance)       | tinyint(3) unsigned | NO       |         | 25          |           |
| [fall\_storm\_chance](Game_weather#fall_storm_chance)     | tinyint(3) unsigned | NO       |         | 25          |           |
| [winter\_rain\_chance](Game_weather#winter_rain_chance)   | tinyint(3) unsigned | NO       |         | 25          |           |
| [winter\_snow\_chance](Game_weather#winter_snow_chance)   | tinyint(3) unsigned | NO       |         | 25          |           |
| [winter\_storm\_chance](Game_weather#winter_storm_chance) | tinyint(3) unsigned | NO       |         | 25          |           |

### Description of the fields

#### zone

This field contains the zone id from [AreaTable.dbc](AreaTable.dbc) that you wish to change the weather for.

#### spring\_rain\_chance

Percentage chance for rain in the Spring

#### spring\_snow\_chance

Percentage chance for snow in the Spring

#### spring\_storm\_chance

Percentage chance for a sand storm in the Spring

#### summer\_rain\_chance

Percentage chance for rain in the Summer

#### summer\_snow\_chance

Percentage chance for snow in the Summer

#### summer\_storm\_chance

Percentage chance for a sand storm in the Summer

#### fall\_rain\_chance

Percentage chance for rain in the Fall

#### fall\_snow\_chance

Percentage chance for snow in the Fall

#### fall\_storm\_chance

Percentage chance for a sand storm in the Fall

#### winter\_rain\_chance

Percentage chance for rain in the Winter

#### winter\_snow\_chance

Percentage chance for snow in the Winter

#### winter\_storm\_chance

Percentage chance for a sand storm in the Winter
