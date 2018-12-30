Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_spell\_cooldown\` table
----------------------------------------

Holds the remaining cooldowns from either character spells or item spells for each character.

### Structure

| **Field**                               | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Character_spell_cooldown#guid)   | int(11) unsigned    | NO       | PRI     | 0           |           |
| [spell](Character_spell_cooldown#spell) | int(11) unsigned    | NO       | PRI     | 0           |           |
| [item](Character_spell_cooldown#item)   | int(11) unsigned    | NO       |         | 0           |           |
| [time](Character_spell_cooldown#time)   | bigint(20) unsigned | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### spell

The spell ID. See Spell.dbc column 1

#### item

If the spell was casted from an item, the item ID. See [item\_template.entry](item_template#entry)

#### time

The time when the spell cooldown will finish, measured in [Unix time](http://en.wikipedia.org/wiki/Unix_time)
