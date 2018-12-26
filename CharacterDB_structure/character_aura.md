Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_aura\` table
-----------------------------

Contains aura information that is loaded when a character is loaded, so the auras that were on the character when it logged out are still kept when it logs back in. A spell can have up to three auras, one in each of its effects.

### Structure

| **Field**                                     | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [guid](Character_aura#guid)                   | int(11) unsigned    | NO       | PRI     | 0           |           |
| [caster\_guid](Character_aura#caster_guid)    | bigint(20) unsigned | NO       |         | 0           |           |
| [spell](Character_aura#spell)                 | int(11) unsigned    | NO       | PRI     | 0           |           |
| [effect\_index](Character_aura#effect_index)  | int(11) unsigned    | NO       | PRI     | 0           |           |
| [amount](Character_aura#amount)               | int(11)             | NO       |         | 0           |           |
| [maxduration](Character_aura#maxduration)     | int(11)             | NO       |         | 0           |           |
| [remaintime](Character_aura#remaintime)       | int(11)             | NO       |         | 0           |           |
| [remaincharges](Character_aura#remaincharges) | int(11)             | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the target affected by the aura. See [characters.guid](characters#guid)

#### caster\_guid

The GUID of the player who casted the aura. See [characters.guid](characters#guid)

#### spell

The spell from which the aura was applied. See Spell.dbc column 1

#### effect\_index

The effect index of the spell from which the aura came from. A spell has up to three effects, with the index being 0, 1, or 2.

#### amount

The modifier value associated with the aura.

#### maxduration

The maximum duration of the aura.

#### remaintime

The time remaining in seconds on the aura. -1 means that the aura is indefinite.

#### remaincharges

The number of charges remaining on the aura.
