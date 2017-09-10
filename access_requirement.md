Back to [world database](https://github.com/cmangos/issues/wiki/mangosdb_struct) list of tables.

# `access_requirement`

This table contains requirements to enter a certain map.

## structure

| Field | Description |
| :---:| :---:|
|id| Former Map ID |
|level_min|Minimum character level to enter this map|
|level_max|Maximum character level to enter this map|
|item|[Item](https://github.com/cmangos/issues/wiki/Item_template#entry) needed to enter this map|
|item2|[Item](https://github.com/cmangos/issues/wiki/Item_template#entry) needed to enter this map|
|heroic_key|Key [Item](https://github.com/cmangos/issues/wiki/Item_template#entry) needed to enter this map|
|heroic_key2|Key [Item](https://github.com/cmangos/issues/wiki/Item_template#entry) needed to enter this map|
|quest_done|[Quest](https://github.com/cmangos/issues/wiki/Quest_template#entry) needed to enter this map|
|quest_failed_text|Displayed failed text when trying to enter without passing requirements|
|heroic_quest_done|[Quest](https://github.com/cmangos/issues/wiki/Quest_template#entry) needed to enter this map on heroic mode|
|heroic_quest_failed_text|Displayed failed text when trying to enter without passing requirements|
|aura_id|[Aura](https://github.com/cmangos/issues/wiki/spell_template#id) needed to enter this map on heroic mode| 
|missing_aura_text|Displayed failed text when trying to enter without passing requirements|
|comment|Map Name and Map ID|