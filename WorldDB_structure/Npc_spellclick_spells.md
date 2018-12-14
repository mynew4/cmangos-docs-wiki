Back to [world database](mangosdb_struct) list of tables.

The \`npc\_spellclick\_spells\` table
-------------------------------------

This table holds information about spells to be casted upon receiving CMSG\_SPELLCLICK. That opcode is sent for quests in which you have to loot creatures, who are already dead at spawning. Examples are [Planning for the Future](http://thottbot.com/q11960) and [Rifle the bodies](http://thottbot.com/q11999).

### Structure

| **Field**                                                        | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [npc\_entry](Npc_spellclick_spells#npc_entry)                    | int(10) unsigned      | NO       |         |             |           |
| [spell\_id](Npc_spellclick_spells#spell_id)                      | int(10) unsigned      | NO       |         |             |           |
| [quest\_start](Npc_spellclick_spells#quest_start)                | mediumint(8) unsigned | NO       |         | 0           |           |
| [quest\_start\_active](Npc_spellclick_spells#quest_start_active) | tinyint(1) unsigned   | NO       |         | 0           |           |
| [quest\_end](Npc_spellclick_spells#quest_end)                    | mediumint(3) unsigned | NO       |         | 0           |           |
| [cast\_flags](Npc_spellclick_spells#cast_flags)                  | tinyint(3) unsigned   | NO       |         |             |           |
| [condition\_id](Npc_spellclick_spells#condition_id)              | mediumint(8) unsigned | NO       |         | 0           |           |

**Note:** The fields quest\_\* are obsolete and will be removed

### Description of the fields

#### npc\_entry

Reference to [Creature\_template\#entry](Creature_template#entry)

#### spell\_id

The spell which should be casted.

Note that for several quests there are more than one spell per click. [Planing for the Future](http://thottbot.com/q11960) for example has [Planning for the Future: Create Snowfall Glade Pup](http://thottbot.com/s46773) which will create the item in the player's inventory and [Planning for the Future: Create Snowfall Glade Pup Cover](http://thottbot.com/s46167) which despawns the creature.

This creates the illusion that the creature has been looted.

#### quest\_start

Same as [Spell\_area\#quest\_start.](Spell_area#quest_start).

#### quest\_start\_active

Same as [Spell\_area\#quest\_start\_active.](Spell_area#quest_start_active).

#### quest\_end

Same as [Spell\_area\#quest\_end.](Spell_area#quest_end).

#### cast\_flags

On every spellclick event a player and a creature "participate". This field defines who casts the spell on who.

Lower bit defines caster: 1=player, 0=creature; higher bit defines target, same mapping as caster bit.

You can use that table for the actual value:

| **cast\_flags value** | **Caster** | **Target** |
|-----------------------|------------|------------|
| 0                     | Creature   | Creature   |
| 1                     | Player     | Creature   |
| 2                     | Creature   | Player     |
| 3                     | Player     | Player     |

#### condition\_id

Value that represents a [condition](Conditions#condition_entry) that must be met in order for the item to drop.
See [Conditions table](Conditions) for detailed description.

Note: If set != 0 it will override any meaning within the quest\_\* fields.
