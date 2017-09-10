Back to [world database](https://github.com/cmangos/issues/wiki/mangosdb_struct) list of tables.

# `access_requirement`

This table contains requirements to enter a certain map.

## structure

|*Field*|*Description*||
|"id":access_requirement#id|Former Map ID|
|"level_min":access_requirement#level_min|Minimum character level to enter this map|
|"level_max":access_requirement#level_max|Maximum character level to enter this map|
|"item":access_requirement#item|"Item":item_template#entry needed to enter this map|
|"item2":access_requirement#item2|"Item":item_template#entryneeded to enter this map|
|"heroic_key":access_requirement#heroic_key|Key "Item":item_template#entry needed to enter this map|
|"heroic_key2":access_requirement#heroic_key2|Key "Item":item_template#entry needed to enter this map|
|"quest_done":access_requirement#quest_done|"Quest":quest_template#entry needed to enter this map|
|"quest_failed_text":access_requirement#quest_failed_text|Displayed failed text when trying to enter without passing requirements|
|"heroic_quest_done":access_requirement#heroic_quest_done|"Quest":quest_template#entry needed to enter this map on heroic mode|
|"heroic_quest_failed_text":access_requirement#heroic_quest_failed_text|Displayed failed text when trying to enter without passing requirements|
|"aura_id":access_requirement#aura_id||
|"missing_aura_text":access_requirement#missing_aura_text||
|"comment":access_requirement#comment|Map Name and Map ID|