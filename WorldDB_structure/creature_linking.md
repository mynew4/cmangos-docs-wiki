Back to [world database](mangosdb_struct) list of tables.<br>
To link creatures by entry, please refer to [Creature\_linking\_template](Creature_linking_template)

The \`creature\_linking\` table
-------------------------------

### Structure

| **Name**                                     | **Type**              | **Null** | **Key** | **Default** | **Extra** | **Comment**                                   |
|----------------------------------------------|-----------------------|----------|---------|-------------|-----------|-----------------------------------------------|
| [guid](Creature_linking#guid)                | int(10) unsigned      | NO       | PRI     | 0           |           | creature.guid of the slave mob that is linked |
| [master\_guid](Creature_linking#master_guid) | int(10) unsigned      | NO       |         | 0           |           | master to trigger events                      |
| [flag](Creature_linking#flag)                | mediumint(8) unsigned | NO       |         | 0           |           | flag - describing what should happen when     |

### Description of the fields

#### guid

[creature.guid](creature#guid) of the slave mob that is linked

#### master\_guid

[creature.guid](creature#guid) of the master to trigger events

#### flag

flag - describing what should happen when

| Flag | Name                          | Comment                                                                           |
| ---- | ----------------------------- | --------------------------------------------------------------------------------- |
| 1    | FLAG_AGGRO_ON_AGGRO           | the "slave" aggroes when the "master" aggroes                                     |
| 2    | FLAG_TO_AGGRO_ON_AGGRO        | the master aggroes when the slave aggroes                                         |
| 4    | FLAG_RESPAWN_ON_EVADE         | the slave respawns when the master evades                                         |
| 8    | FLAG_TO_RESPAWN_ON_EVADE      | the master respawns when the slave evades                                         |
| 16   | FLAG_DESPAWN_ON_DEATH         | the slave despawns when the master dies                                           |
| 32   | FLAG_SELFKILL_ON_DEATH        | the slave goes suicide when the master dies                                       |
| 64   | FLAG_RESPAWN_ON_DEATH         | the slave respawn when the master dies                                            |
| 128  | FLAG_RESPAWN_ON_RESPAWN       | the slave respawns on master respawn                                              |
| 256  | FLAG_DESPAWN_ON_RESPAWN       | the slave despawns on master respawn (TODO: check for slave != master)            |
| 512  | FLAG_FOLLOW                   | the slave follows the master, very basic, see TODO notes in commit, or post below |
| 1024 | FLAG_CANT_SPAWN_IF_BOSS_DEAD  | the slave cannot respawn while boss is dead                                       |
| 2048 | FLAG_CANT_SPAWN_IF_BOSS_ALIVE | the slave cannot respawn while boss is alive                                      |
| 4096 | FLAG_DESPAWN_ON_EVADE         | the slave despawn after the master evade                                          |
| 8192 | FLAG_DESPAWN_ON_DESPAWN       | the slave despawn after the master despawns                                       |
