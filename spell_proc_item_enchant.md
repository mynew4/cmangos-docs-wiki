Back to [world database](https://github.com/cmangos/issues/wiki/mangosdb_struct) list of tables.

## The `spell_proc_item_enchant` table

holds spell effects that need ppm rates.

### Structure

| Field| Type| Null| Key| Default| Extra|
| ---|---| ---|--- |--- |--- |
|"entry":spell_proc_item_enchant#entry|int(8) unsigned|NO|PRI|||
|"ppmRate":spell_proc_item_enchant#ppmRate|float signed|NO|PRI|0||

#### entry

"spell&#95;template.entry":spell_template#entry of the spell

This specified entry will be automatically targeted if it is near the unit casting the spell.

#### ppmRate

http://wowwiki.wikia.com/wiki/Procs_per_minute