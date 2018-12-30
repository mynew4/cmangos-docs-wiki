Back to [world database](mangosdb_struct) list of tables.

## The `world_template` table

holds the ScriptNames of the world maps 0, 1, 530, 571.

### Structure

| Field| Type| Null| Key| Default| Extra|
| ---|---| ---|--- |--- |--- |
|[map](world_template#map)|smallint(5) unsigned|NO|PRI|||
|[ScriptName](world_template#ScriptName)|varchar|NO|PRI|||

#### map

id from [Map.dbc](Map.dbc) the ScriptName is applied to.

#### ScriptName

ScriptName used in Core
