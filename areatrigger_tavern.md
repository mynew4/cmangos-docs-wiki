Back to "world database":mangosdb_struct list of tables.

h2. The `areatrigger_tavern` table

Enable a trigger when player enters a city or tavern. This causes the player to enter a resting state.

h3. Structure


|Field|Type|NULL|Key|Default|Comments|
|"id":areatrigger_tavern#id|int(11) unsigned|NO|PRIMARY|0|Identifier, auto&#95;increment|
|"name":areatrigger_tavern#name|text|YES||||


h3. Description of the fields

h4. id

This is the trigger identifier, see "AreaTrigger.dbc":https://github.com/cmangos/issues/wiki/AreaTrigger.dbc

h4. name

Name of the city or tavern. This is purely for descriptive purposes.
