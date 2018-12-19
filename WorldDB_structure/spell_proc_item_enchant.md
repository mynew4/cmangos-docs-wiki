Back to [world database](mangosdb_struct) list of tables.

## The `spell_proc_item_enchant` table

holds spell effects that need ppm rates.

### Structure

| Field| Type| Null| Key| Default| Extra|
| ---|---| ---|--- |--- |--- |
|[entry](spell_proc_item_enchant#entry)|int(8) unsigned|NO|PRI|||
|[ppmRate](spell_proc_item_enchant#ppmRate)|float signed|NO|PRI|0||

#### entry

[spell_template.id](spell_template#id) of the spell

#### ppmRate

This field controls the times per minute that the spell should proc. If zero, then the value is taken from the DBC entry.

http://wowwiki.wikia.com/wiki/Procs_per_minute