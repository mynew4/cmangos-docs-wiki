Back to "world database":mangosdb_struct list of tables.

h2. The `areatrigger&#95;involvedrelation` table

Enable a trigger to finish one condition of a quest (explore)

If there is a record in the table for this a quest, then the quest will not be completed until the player activates this areatriger. The quest is not necessarily finished after that, but that one condition of the quest is satisfied. If the only condition of the quest is to explore an area, then the quest will be complete.

h3. Structure


|Field|Type|Attributes|Can be null|Default|Comments|
|"id":Areatrigger_involvedrelation#id|int(11)|unsigned|NO|0|Identifier|
|"quest":Areatrigger_involvedrelation#quest|int(11)|unsigned|NO|0|Quest Identifier|


h3. Description of the fields

h4. id

This is the trigger identifier from "AreaTrigger.dbc":AreaTrigger.dbc

h4. quest

Quest's identifier (see "quest&#95;template.entry":quest_template#entry)
