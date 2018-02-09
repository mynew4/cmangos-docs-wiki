Back to [world database](https://github.com/cmangos/issues/wiki/mangosdb_struct) list of tables.

## The `world_template` table

This table holds the ScriptNames of the world maps 0, 1, 530, 571.

### Structure

| Field| Type| Null| Key| Default| Extra|
| ---|---| ---|--- |--- |--- |
|[map](https://github.com/cmangos/issues/wiki/Map.dbc)|smallint(5) unsigned|NO|PRI|||
|ScriptName|varchar|NO|PRI|||

#### map

id from https://github.com/cmangos/issues/wiki/Map.dbc the ScriptName is applied to.

#### ScriptName

ScriptName used in Core