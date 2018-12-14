Back to [world database](mangosdb_struct) list of tables.

## The `spell_cone` table

holds `Degrees` for `Cone` spells with Effectparameter: 

`TARGET_X_CONE` and `TARGET_CHAIN_DAMAGE + SPELL_ATTR_EX5_CLEAVE_FRONT_TARGET`, which otherwise would need to be hardcoded.

Original Data is extracted from `Cata-Client`. Values are backwards compatible with earlier versions of the game for most spells.

### Structure

| Field| Type| Null| Key| Default| Extra|
| ---|---| ---|--- |--- |--- |
|[Id](spell_cone#Id)|int(11) unsigned|NO|PRI|0||
|[ConeDegrees](spell_cone#ConeDegrees)|int(11)|NO|PRI|60||

#### Id

[spell_cone.Id](spell_cone#Id) of the spell

#### ConeDegrees

[spell_cone.ConeDegrees](spell_cone#ConeDegrees) of the spell.