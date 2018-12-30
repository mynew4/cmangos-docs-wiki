Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_pet\` table
----------------------------

This table holds the pet data for each pet summoned by anyone in the game.

### Structure

| **Field**                                             | **Type**            | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------------------|---------------------|----------|---------|-------------|-----------|
| [id](Character_pet#id)                                | int(11) unsigned    | NO       | PRI     | 0           |           |
| [entry](Character_pet#entry)                          | int(11) unsigned    | NO       |         | 0           |           |
| [owner](Character_pet#owner)                          | int(11) unsigned    | NO       | MUL     | 0           |           |
| [modelid](Character_pet#modelid)                      | int(11) unsigned    | YES      |         | 0           |           |
| [CreatedBySpell](Character_pet#createdbyspell)        | int(11) unsigned    | NO       |         | 0           |           |
| [PetType](Character_pet#pettype)                      | tinyint(3) unsigned | NO       |         | 0           |           |
| [level](Character_pet#level)                          | int(11) unsigned    | NO       |         | 1           |           |
| [exp](Character_pet#exp)                              | int(11) unsigned    | NO       |         | 0           |           |
| [Reactstate](Character_pet#reactstate)                | tinyint(1) unsigned | NO       |         | 0           |           |
| [talentpoints](Character_pet#talentpoints)            | int(11) unsigned    | NO       |         | 0           |           |
| [name](Character_pet#name)                            | varchar(100)        | YES      |         | Pet         |           |
| [renamed](Character_pet#renamed)                      | tinyint(1) unsigned | NO       |         | 0           |           |
| [slot](Character_pet#slot)                            | int(11) unsigned    | NO       |         | 0           |           |
| [curhealth](Character_pet#curhealth)                  | int(11) unsigned    | NO       |         | 1           |           |
| [curmana](Character_pet#curmana)                      | int(11) unsigned    | NO       |         | 0           |           |
| [curhappiness](Character_pet#curhappiness)            | int(11) unsigned    | NO       |         | 0           |           |
| [savetime](Character_pet#savetime)                    | bigint(20) unsigned | NO       |         | 0           |           |
| [resettalents\_cost](Character_pet#resettalents_cost) | int(11) unsigned    | NO       |         | 0           |           |
| [resettalents\_time](Character_pet#resettalents_time) | bigint(20) unsigned | NO       |         | 0           |           |
| [abdata](Character_pet#abdata)                        | longtext            | YES      |         | None        |           |
| [teachspelldata](Character_pet#teachspelldata)        | longtext            | YES      |         | None        |           |

### Description of the fields

#### id

The special pet ID. This is a unique identifier among all pets.

#### entry

The creature entry of this pet. See [creature\_template.entry](creature_template#entry)

#### owner

The GUID of the pet's owner. See [characters.guid](characters#guid)

#### modelid

The model ID to use to display the pet.

#### CreatedBySpell

The ID of the spell that has created this pet. For hunters, this is usually the Tame Beast spell. For warlocks or other classes (mages), it is the spell ID that summoned the creature. See Spell.dbc column 1

#### PetType

The type of pet that this is. 0 = summoned pet, 1 = tamed pet

#### level

The current level of the pet.

#### exp

The current experience that this pet has. For summoned pets, this field is always 0.

#### Reactstate

The current reaction state of the pet (passive, aggressive, etc).

#### talentpoints

#### name

The pet's name.

#### renamed

Boolean 1 or 0. 1 = Pet has been renamed, 0 = Pet has never been renamed and still uses the same name as the creature that was tamed.

#### slot

The pet slot that the pet is in. The slot is a number between 0 and 3 inclusive.

#### curhealth

The current pet health at the time it was saved to DB.

#### curmana

The current pet mana at the time it was saved to DB.

#### curhappiness

The current pet happiness.

#### savetime

The time when the pet was last saved, in Unix time.

#### resettalents\_cost

#### resettalents\_time

#### abdata

data about pet action bar and action type ten pairs of action bar entry (from 1 to 10) and action or spell IDs

#### teachspelldata

This field holds IDs of spells that have been taught to this pet, abilities that this pet has.
