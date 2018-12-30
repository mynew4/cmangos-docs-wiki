Back to [world database](mangosdb_struct) list of tables.

The \`creature\_respawn\` table
-------------------------------

This table holds the respawn time when creatures should be respawned in the world. In case of a server crash, this table holds the respawn data so that the creatures don't respawn immediately on server restart. How often the respawn time is saved for creatures can be controlled in mangosd.conf at SaveRespawnTimeImmediately.

### Structure

| **Field**                                   | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [guid](Creature_respawn#guid)               | int(10) unsigned      | NO       | PRI     | 0           |           |
| [respawntime](Creature_respawn#respawntime) | bigint(20)            | NO       |         | 0           |           |
| [instance](Creature_respawn#instance)       | mediumint(8) unsigned | NO       | PRI     | 0           |           |

### Description of the fields

#### guid

The GUID of the creature. See [creature.guid](creature#guid)

#### respawntime

The time when the creature should be respawned in Unix time.

#### instance

If the creature was killed in an instance, this field holds the instance ID where this creature should be respawned. Each instance is different depending on the group so this field is vital in keeping track of which creatures should be respawned for which players at what time.
