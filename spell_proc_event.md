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

<table>
<colgroup>
<col width="5%" />
<col width="6%" />
<col width="27%" />
<col width="60%" />
</colgroup>
<thead>
<tr class="header">
<th>Bit</th>
<th>Hex</th>
<th>ProcFlag Name</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>0x00000000</td>
<td>PROC_FLAG_NONE</td>
<td>always?</td>
</tr>
<tr class="even">
<td>1</td>
<td>0x00000001</td>
<td>PROC_FLAG_KILLED</td>
<td>Killed by aggressor</td>
</tr>
<tr class="odd">
<td>2</td>
<td>0x00000002</td>
<td>PROC_FLAG_KILL</td>
<td>Kill target (in most cases need XP/Honor reward, see Unit::IsTriggeredAtSpellProcEvent for additinoal check)</td>
</tr>
<tr class="even">
<td>4</td>
<td>0x00000004</td>
<td>PROC_FLAG_SUCCESSFUL_MELEE_HIT</td>
<td>Successful melee auto attack</td>
</tr>
<tr class="odd">
<td>8</td>
<td>0x00000008</td>
<td>PROC_FLAG_TAKEN_MELEE_HIT</td>
<td>Taken damage from melee auto attack hit</td>
</tr>
<tr class="even">
<td>16</td>
<td>0x00000010</td>
<td>PROC_FLAG_SUCCESSFUL_MELEE_SPELL_HIT</td>
<td>Successful attack by Spell that use melee weapon</td>
</tr>
<tr class="odd">
<td>32</td>
<td>0x00000020</td>
<td>PROC_FLAG_TAKEN_MELEE_SPELL_HIT</td>
<td>Taken damage by Spell that use melee weapon</td>
</tr>
<tr class="even">
<td>64</td>
<td>0x00000040</td>
<td>PROC_FLAG_SUCCESSFUL_RANGED_HIT</td>
<td>Successful Ranged auto attack</td>
</tr>
<tr class="odd">
<td>128</td>
<td>0x00000080</td>
<td>PROC_FLAG_TAKEN_RANGED_HIT</td>
<td>Taken damage from ranged auto attack</td>
</tr>
<tr class="even">
<td>256</td>
<td>0x00000100</td>
<td>PROC_FLAG_SUCCESSFUL_RANGED_SPELL_HIT</td>
<td>Successful Ranged attack by Spell that use ranged weapon</td>
</tr>
<tr class="odd">
<td>512</td>
<td>0x00000200</td>
<td>PROC_FLAG_TAKEN_RANGED_SPELL_HIT</td>
<td>Taken damage by Spell that use ranged weapon</td>
</tr>
<tr class="even">
<td>1024</td>
<td>0x00000400</td>
<td>PROC_FLAG_DONE_SPELL_NONE_DMG_CLASS_POS</td>
<td>Done positive spell that has dmg class none</td>
</tr>
<tr class="odd">
<td>2048</td>
<td>0x00000800</td>
<td>PROC_FLAG_TAKEN_SPELL_NONE_DMG_CLASS_POS</td>
<td>Taken positive spell that has dmg class none</td>
</tr>
<tr class="even">
<td>4096</td>
<td>0x00001000</td>
<td>PROC_FLAG_DONE_SPELL_NONE_DMG_CLASS_NEG</td>
<td>Done negative spell that has dmg class none</td>
</tr>
<tr class="odd">
<td>8192</td>
<td>0x00002000</td>
<td>PROC_FLAG_TAKEN_SPELL_NONE_DMG_CLASS_NEG</td>
<td>Taken negative spell that has dmg class none</td>
</tr>
<tr class="even">
<td>16384</td>
<td>0x00004000</td>
<td>PROC_FLAG_DONE_SPELL_MAGIC_DMG_CLASS_POS</td>
<td>Successful cast positive spell (by default only on healing)</td>
</tr>
<tr class="odd">
<td>32768</td>
<td>0x00008000</td>
<td>PROC_FLAG_TAKEN_SPELL_MAGIC_DMG_CLASS_POS</td>
<td>Taken positive spell hit (by default only on healing)</td>
</tr>
<tr class="even">
<td>65536</td>
<td>0x00010000</td>
<td>PROC_FLAG_DONE_SPELL_MAGIC_DMG_CLASS_NEG</td>
<td>Successful negative spell cast (by default only on damage)</td>
</tr>
<tr class="odd">
<td>131072</td>
<td>0x00020000</td>
<td>PROC_FLAG_TAKEN_SPELL_MAGIC_DMG_CLASS_NEG</td>
<td>Taken negative spell (by default only on damage)</td>
</tr>
<tr class="even">
<td>262144</td>
<td>0x00040000</td>
<td>PROC_FLAG_ON_DO_PERIODIC</td>
<td>Successful do periodic (damage / healing, determined by PROC_EX_PERIODIC_POSITIVE or negative if no procEx)</td>
</tr>
<tr class="odd">
<td>524288</td>
<td>0x00080000</td>
<td>PROC_FLAG_ON_TAKE_PERIODIC</td>
<td>Taken spell periodic (damage / healing, determined by PROC_EX_PERIODIC_POSITIVE or negative if no procEx)</td>
</tr>
<tr class="even">
<td>1048576</td>
<td>0x00100000</td>
<td>PROC_FLAG_TAKEN_ANY_DAMAGE</td>
<td>Taken any damage</td>
</tr>
<tr class="odd">
<td>2097152</td>
<td>0x00200000</td>
<td>PROC_FLAG_ON_TRAP_ACTIVATION</td>
<td>On trap activation</td>
</tr>
<tr class="even">
<td>4194304</td>
<td>0x00400000</td>
<td>PROC_FLAG_TAKEN_OFFHAND_HIT</td>
<td>Taken off-hand melee attacks(not used)</td>
</tr>
<tr class="odd">
<td>8388608</td>
<td>0x00800000</td>
<td>PROC_FLAG_SUCCESSFUL_OFFHAND_HIT</td>
<td>Successful off-hand melee attacks</td>
</tr>
</tbody>
</table>

#### procEx

<table>
<colgroup>
<col width="6%" />
<col width="8%" />
<col width="24%" />
<col width="61%" />
</colgroup>
<thead>
<tr class="header">
<th>Bit</th>
<th>Hex</th>
<th>ProcEx Name</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>0x0000000</td>
<td>PROC_EX_NONE</td>
<td>If none can trigger on Hit/Crit only (passive spells MUST defined by SpellFamily flag)</td>
</tr>
<tr class="even">
<td>1</td>
<td>0x0000001</td>
<td>PROC_EX_NORMAL_HIT</td>
<td>If set only from normal hit (only damage spells)</td>
</tr>
<tr class="odd">
<td>2</td>
<td>0x0000002</td>
<td>PROC_EX_CRITICAL_HIT</td>
<td>only on crit</td>
</tr>
<tr class="even">
<td>4</td>
<td>0x0000004</td>
<td>PROC_EX_MISS</td>
<td>only on miss</td>
</tr>
<tr class="odd">
<td>8</td>
<td>0x0000008</td>
<td>PROC_EX_RESIST</td>
<td>only on resist</td>
</tr>
<tr class="even">
<td>16</td>
<td>0x0000010</td>
<td>PROC_EX_DODGE</td>
<td>only on dodge</td>
</tr>
<tr class="odd">
<td>32</td>
<td>0x0000020</td>
<td>PROC_EX_PARRY</td>
<td>only on parry</td>
</tr>
<tr class="even">
<td>64</td>
<td>0x0000040</td>
<td>PROC_EX_BLOCK</td>
<td>only on block</td>
</tr>
<tr class="odd">
<td>128</td>
<td>0x0000080</td>
<td>PROC_EX_EVADE</td>
<td>only on evade</td>
</tr>
<tr class="even">
<td>256</td>
<td>0x0000100</td>
<td>PROC_EX_IMMUNE</td>
<td>only on immune</td>
</tr>
<tr class="odd">
<td>512</td>
<td>0x0000200</td>
<td>PROC_EX_DEFLECT</td>
<td>only on deflect</td>
</tr>
<tr class="even">
<td>1024</td>
<td>0x0000400</td>
<td>PROC_EX_ABSORB</td>
<td>only on absorb</td>
</tr>
<tr class="odd">
<td>2048</td>
<td>0x0000800</td>
<td>PROC_EX_REFLECT</td>
<td>only on reflect</td>
</tr>
<tr class="even">
<td>4096</td>
<td>0x0001000</td>
<td>PROC_EX_INTERRUPT</td>
<td>Melee hit result can be Interrupt (not used)</td>
</tr>
<tr class="odd">
<td>8192</td>
<td>0x0002000</td>
<td>PROC_EX_RESERVED1</td>
<td>UNUSED</td>
</tr>
<tr class="even">
<td>16384</td>
<td>0x0004000</td>
<td>PROC_EX_RESERVED2</td>
<td>UNUSED</td>
</tr>
<tr class="odd">
<td>32768</td>
<td>0x0008000</td>
<td>PROC_EX_RESERVED3</td>
<td>UNUSED</td>
</tr>
<tr class="even">
<td>65536</td>
<td>0x0010000</td>
<td>PROC_EX_EX_TRIGGER_ALWAYS</td>
<td>If set trigger always ( no matter another flags) used for drop charges</td>
</tr>
<tr class="odd">
<td>131072</td>
<td>0x0020000</td>
<td>PROC_EX_EX_ONE_TIME_TRIGGER</td>
<td>If set trigger always but only one time (not used)</td>
</tr>
<tr class="even">
<td>262144</td>
<td>0x0040000</td>
<td>PROC_EX_PERIODIC_POSITIVE</td>
<td>For periodic heal</td>
</tr>
<tr class="odd">
<td>524288</td>
<td>0x0080000</td>
<td>PROC_EX_MAGNET</td>
<td>For grounding totem hit</td>
</tr>
</tbody>
</table>

#### ppmRate

This field controls the times per minute that the spell should proc. If zero, then the value is taken from the DBC entry.

#### CustomChance

Changed Proc Chance from spell\_template information

#### Cooldown

Internal Cooldown
