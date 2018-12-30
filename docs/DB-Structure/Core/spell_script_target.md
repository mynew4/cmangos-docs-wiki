Back to [world database](mangosdb_struct) list of tables.

The \`spell\_script\_target\` table
-----------------------------------

Used to control SpellEffect with ImpliciteTargetA-B == 7|8|22|38|40|46|52.

These spell effects require a specific target in either alive or dead state (for creatures).

### Structure

| **Field**                                                  | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry](spell_script_target#entry)                         | int(6) unsigned       | NO       | PRI     |             |           |
| [type](spell_script_target#type)                           | int(8) unsigned       | NO       | PRI     | 0           |           |
| [targetEntry](spell_script_target#targetentry)             | int(11) unsigned      | NO       | PRI     | 0           |           |
| [inverseEffectMask](spell_script_target#inverseeffectmask) | mediumint(8) unsigned | NO       |         | 0           |           |

### Description of the fields

#### entry

The spell ID. [spell\_template\#id](spell_template)

When adding a new entry, be sure to check to see if the spell triggers another spell. If it does, don't forget to check that spell as well to see if it has ImplictTargetA-B = 38 || ImpliciteTargetA-B == 7 and if it does, add an entry in this table for it as well.

NOTE: The only valide targets for ImpliciteTargetA-B == 7 are creatures(dead or alive).

#### type

| ID  | Type                                                  |
|-----|-------------------------------------------------------|
| 0   | Gameobject                                            |
| 1   | Creature by Entry                                     |
| 2   | Creature which must be dead (killed by Player or Npc) |
| 3   | Creature by Guid                                      |

NOTE: A creature corpse and a creature that *looks* dead are two different things. One is actually dead and the other is just using an emote or spell to appear dead.

#### targetEntry

Can be: [creature\_template.entry](creature_template#entry) or [gameobject\_template.entry](gameobject_template#entry) depending on the choosen type.

This specified entry will be automatically targeted if it is near the unit casting the spell.

#### inverseEffectMask

A mask value defining if the target is only applicable for specifiq effect indexes by the spell.
This is an inverseMask, so you need to filter effects for which you don't want the target to be valid.
The mask is 1 << EffectIndex (EffectIndex going from 0 to 2)

Example:
(Spell, 1, NpcA, 2^0), -- NpcA will NOT be chosen for spell-effect 0, so it will be chosen for effects 1 or 2
(Spell, 1, NpcB, 2^1|2^2), -- NpcB will NOT be chosen for spell-effects 1, 2, so it will be chosen for effect 0.

So with this we can define targets for a spell (assuming that the targets for the effects can make use of spell\_script\_target!) in a way that Effect0 will hit NpcB, and Effect1,2 will hit NpcA

| ID  | Description     |
|-----|-----------------|
| 0   | All effects     |
| 1   | effects 1 and 2 |
| 2   | effects 0 and 2 |
| 3   | effect 2        |
| 4   | effects 0 and 1 |
| 5   | effect 1        |
| 6   | effect 0        |
