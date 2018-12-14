Back to [characters database](charactersdb_struct) list of tables.

The \`pet\_spell\_cooldown\` table
----------------------------------

This table holds information on pet spell cooldowns.

### Structure

| **Field**                         | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Pet_spell_cooldown#guid)   | int(11) unsigned    | NO       | PRI     | 0           |           |
| [spell](Pet_spell_cooldown#spell) | int(11) unsigned    | NO       | PRI     | 0           |           |
| [time](Pet_spell_cooldown#time)   | bigint(20) unsigned | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the pet. See [character\_pet.id](character_pet#id)

#### spell

The spell ID to which the cooldown applies.

#### time

The time when the cooldown expires, in Unix time.
