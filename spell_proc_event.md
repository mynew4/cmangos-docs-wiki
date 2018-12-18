Back to [world database](mangosdb_struct) list of tables.

The \`spell\_proc\_event\` table
--------------------------------

holds information on how certain spells activate, which proc other spells.

All spells in this table must have **Aura Id 42 (SPELL\_AURA\_PROC\_TRIGGER\_SPELL)** as one of its **Effects**.

Any entries in this table will overwrite the existing proc settings for this [spell\_template\#id](spell_template).

### Structure

| **Field**                                           | **Type**             | **Null** | **Key** | **Default** | **Extra**                          |
|-----------------------------------------------------|----------------------|----------|---------|-------------|------------------------------------|
| [entry](spell_proc_event#entry)                     | smallint(6) unsigned | NO       | PRI     | 0           |                                    |
| [SchoolMask](spell_proc_event#schoolmask)           | tinyint(4)           | NO       |         | 0           |                                    |
| [SpellFamilyName](spell_proc_event#spellfamilyname) | smallint(6) unsigned | NO       |         | 0           |                                    |
| [SpellFamilyMask](spell_proc_event#spellfamilymask) | bigint(40) unsigned  | NO       |         | 0           | Different Setup through Expansions |
| [procFlags](spell_proc_event#procflags)             | int(11) unsigned     | NO       |         | 0           |                                    |
| [procEx](spell_proc_event#procex)                   | int(11) unsigned     | NO       |         | 0           |                                    |
| [ppmRate](spell_proc_event#ppmrate)                 | float                | NO       |         | 0           |                                    |
| [CustomChance](spell_proc_event#customchance)       | float                | NO       |         | 0           |                                    |
| [Cooldown](spell_proc_event#cooldown)               | float                | NO       |         | 0           |                                    |

### Description of the fields

#### entry

The spell ID that is capable to proc on an event.

#### SchoolMask

This field contains a bitmask that controls on what types of spell damages the proc can be triggered. For example if an aura procs only when the unit it is casted upon is hit by shadow spells (spell 34914). To combine spell schools, just add the bit values.

| Bit | Hex  | School Name           | Comment         |
|-----|------|-----------------------|-----------------|
| 1   | 0x01 | SPELL\_SCHOOL\_NORMAL | Physical Damage |
| 2   | 0x02 | SPELL\_SCHOOL\_HOLY   | Holy Damage     |
| 4   | 0x04 | SPELL\_SCHOOL\_FIRE   | Fire Damage     |
| 8   | 0x08 | SPELL\_SCHOOL\_NATURE | Nature Damage   |
| 16  | 0x10 | SPELL\_SCHOOL\_FROST  | Frost Damage    |
| 32  | 0x20 | SPELL\_SCHOOL\_SHADOW | Shadow Damage   |
| 64  | 0x40 | SPELL\_SCHOOL\_ARCANE | Arcane Damage   |

#### SpellFamilyName

This field controls what family name spells can proc the triggered spell.

| ID  | Family Name | ID  | Family Name  |
|-----|-------------|-----|--------------|
| 0   | Generic     | 9   | Hunter       |
| 3   | Mage        | 10  | Paladin      |
| 4   | Warrior     | 11  | Shaman       |
| 5   | Warlock     | 13  | Potion       |
| 6   | Priest      | 15  | Death Knight |
| 7   | Druid       | 53  | Monk         |
| 8   | Rogue       | 107 | Demon Hunter |

#### SpellFamilyMask

These fields control what spells' family flags can proc the triggered spell.

#### procFlags

A bitmask controlling what events trigger the spell. To combine possible events, add the proc bits together.

| Bit     | Hex        | ProcFlag Name                             | Comment                                                                                                      |
| ------- | ---------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| 0       | 0x00000000 | PROC_FLAG_NONE                            | always?                                                                                                      |
| 1       | 0x00000001 | PROC_FLAG_KILLED                          | Killed by aggressor                                                                                          |
| 2       | 0x00000002 | PROC_FLAG_KILL                            | Kill target (in most cases need XP/Honor reward, see Unit::IsTriggeredAtSpellProcEvent for additinoal check) |
| 4       | 0x00000004 | PROC_FLAG_SUCCESSFUL_MELEE_HIT            | Successful melee auto attack                                                                                 |
| 8       | 0x00000008 | PROC_FLAG_TAKEN_MELEE_HIT                 | Taken damage from melee auto attack hit                                                                      |
| 16      | 0x00000010 | PROC_FLAG_SUCCESSFUL_MELEE_SPELL_HIT      | Successful attack by Spell that use melee weapon                                                             |
| 32      | 0x00000020 | PROC_FLAG_TAKEN_MELEE_SPELL_HIT           | Taken damage by Spell that use melee weapon                                                                  |
| 64      | 0x00000040 | PROC_FLAG_SUCCESSFUL_RANGED_HIT           | Successful Ranged auto attack                                                                                |
| 128     | 0x00000080 | PROC_FLAG_TAKEN_RANGED_HIT                | Taken damage from ranged auto attack                                                                         |
| 256     | 0x00000100 | PROC_FLAG_SUCCESSFUL_RANGED_SPELL_HIT     | Successful Ranged attack by Spell that use ranged weapon                                                     |
| 512     | 0x00000200 | PROC_FLAG_TAKEN_RANGED_SPELL_HIT          | Taken damage by Spell that use ranged weapon                                                                 |
| 1024    | 0x00000400 | PROC_FLAG_DONE_SPELL_NONE_DMG_CLASS_POS   | Done positive spell that has dmg class none                                                                  |
| 2048    | 0x00000800 | PROC_FLAG_TAKEN_SPELL_NONE_DMG_CLASS_POS  | Taken positive spell that has dmg class none                                                                 |
| 4096    | 0x00001000 | PROC_FLAG_DONE_SPELL_NONE_DMG_CLASS_NEG   | Done negative spell that has dmg class none                                                                  |
| 8192    | 0x00002000 | PROC_FLAG_TAKEN_SPELL_NONE_DMG_CLASS_NEG  | Taken negative spell that has dmg class none                                                                 |
| 16384   | 0x00004000 | PROC_FLAG_DONE_SPELL_MAGIC_DMG_CLASS_POS  | Successful cast positive spell (by default only on healing)                                                  |
| 32768   | 0x00008000 | PROC_FLAG_TAKEN_SPELL_MAGIC_DMG_CLASS_POS | Taken positive spell hit (by default only on healing)                                                        |
| 65536   | 0x00010000 | PROC_FLAG_DONE_SPELL_MAGIC_DMG_CLASS_NEG  | Successful negative spell cast (by default only on damage)                                                   |
| 131072  | 0x00020000 | PROC_FLAG_TAKEN_SPELL_MAGIC_DMG_CLASS_NEG | Taken negative spell (by default only on damage)                                                             |
| 262144  | 0x00040000 | PROC_FLAG_ON_DO_PERIODIC                  | Successful do periodic (damage / healing, determined by PROC_EX_PERIODIC_POSITIVE or negative if no procEx)  |
| 524288  | 0x00080000 | PROC_FLAG_ON_TAKE_PERIODIC                | Taken spell periodic (damage / healing, determined by PROC_EX_PERIODIC_POSITIVE or negative if no procEx)    |
| 1048576 | 0x00100000 | PROC_FLAG_TAKEN_ANY_DAMAGE                | Taken any damage                                                                                             |
| 2097152 | 0x00200000 | PROC_FLAG_ON_TRAP_ACTIVATION              | On trap activation                                                                                           |
| 4194304 | 0x00400000 | PROC_FLAG_TAKEN_OFFHAND_HIT               | Taken off-hand melee attacks(not used)                                                                       |
| 8388608 | 0x00800000 | PROC_FLAG_SUCCESSFUL_OFFHAND_HIT          | Successful off-hand melee attacks                                                                            |

#### procEx

| Bit    | Hex       | ProcEx Name                 | Comment                                                                                |
| ------ | --------- | --------------------------- | -------------------------------------------------------------------------------------- |
| 0      | 0x0000000 | PROC_EX_NONE                | If none can trigger on Hit/Crit only (passive spells MUST defined by SpellFamily flag) |
| 1      | 0x0000001 | PROC_EX_NORMAL_HIT          | If set only from normal hit (only damage spells)                                       |
| 2      | 0x0000002 | PROC_EX_CRITICAL_HIT        | only on crit                                                                           |
| 4      | 0x0000004 | PROC_EX_MISS                | only on miss                                                                           |
| 8      | 0x0000008 | PROC_EX_RESIST              | only on resist                                                                         |
| 16     | 0x0000010 | PROC_EX_DODGE               | only on dodge                                                                          |
| 32     | 0x0000020 | PROC_EX_PARRY               | only on parry                                                                          |
| 64     | 0x0000040 | PROC_EX_BLOCK               | only on block                                                                          |
| 128    | 0x0000080 | PROC_EX_EVADE               | only on evade                                                                          |
| 256    | 0x0000100 | PROC_EX_IMMUNE              | only on immune                                                                         |
| 512    | 0x0000200 | PROC_EX_DEFLECT             | only on deflect                                                                        |
| 1024   | 0x0000400 | PROC_EX_ABSORB              | only on absorb                                                                         |
| 2048   | 0x0000800 | PROC_EX_REFLECT             | only on reflect                                                                        |
| 4096   | 0x0001000 | PROC_EX_INTERRUPT           | Melee hit result can be Interrupt (not used)                                           |
| 8192   | 0x0002000 | PROC_EX_RESERVED1           | UNUSED                                                                                 |
| 16384  | 0x0004000 | PROC_EX_RESERVED2           | UNUSED                                                                                 |
| 32768  | 0x0008000 | PROC_EX_RESERVED3           | UNUSED                                                                                 |
| 65536  | 0x0010000 | PROC_EX_EX_TRIGGER_ALWAYS   | If set trigger always ( no matter another flags) used for drop charges                 |
| 131072 | 0x0020000 | PROC_EX_EX_ONE_TIME_TRIGGER | If set trigger always but only one time (not used)                                     |
| 262144 | 0x0040000 | PROC_EX_PERIODIC_POSITIVE   | For periodic heal                                                                      |
| 524288 | 0x0080000 | PROC_EX_MAGNET              | For grounding totem hit                                                                |

#### ppmRate

This field controls the times per minute that the spell should proc. If zero, then the value is taken from the DBC entry.

#### CustomChance

Changed Proc Chance from spell\_template information

#### Cooldown

Internal Cooldown
