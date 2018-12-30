Back to [world database](mangosdb_struct) list of tables.

The \`spell\_threat\` table
---------------------------

This table holds threat values on all spells that should either give or take away threat.

### Structure

| **Field**                             | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Spell_threat#entry)           | int(10) unsigned | NO       | PRI     |             |           |
| [Threat](Spell_threat#threat)         | int(11)          | NO       |         |             |           |
| [multiplier](Spell_threat#multiplier) | float            | NO       |         |             |           |
| [ap\_bonus](Spell_threat#ap_bonus)    | float            | NO       |         |             |           |

### Description of the fields

#### entry

The spell ID. See Spell.dbc

#### Threat

The threat value that this spells should add to the caster (or take away if it is negative).

#### multiplier

The threat multiplier for damage/healing

#### ap\_bonus

Additional threat bonus from attack power
