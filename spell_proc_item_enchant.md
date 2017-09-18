Back to [world database](https://github.com/cmangos/issues/wiki/mangosdb_struct) list of tables.

## The `spell_proc_item_enchant` table

holds spell effects that need ppm rates.

### Structure

| Field| Type| Null| Key| Default| Extra|
| ---|---| ---|--- |--- |--- |
|[entry](https://github.com/cmangos/issues/wiki/spell_proc_item_enchant#entry)|int(8) unsigned|NO|PRI|||
|[ppmRate](https://github.com/cmangos/issues/wiki/spell_proc_item_enchant#ppmRate)|float signed|NO|PRI|0||

#### entry

[spell_template.id](https://github.com/cmangos/issues/wiki/spell_template#id) of the spell

#### ppmRate

http://wowwiki.wikia.com/wiki/Procs_per_minute