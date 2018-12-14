Back to [world database](mangosdb_struct) list of tables.

The \`spell\_pet\_auras\` table
-------------------------------

| **Field**                            | **Type**     | **Attributes** | **Key** | **Null** | **Default** | **Extra** | **Comment**     |
|--------------------------------------|--------------|----------------|---------|----------|-------------|-----------|-----------------|
| [spell](Spell_pet_auras#spell)       | mediumint(8) | unsigned       | PRI     | NO       | NULL        |           | dummy spell id  |
| [effectId](Spell_pet_auras#effectid) | tinyint(3)   | unsigned       | PRI     | NO       | 0           |           |                 |
| [pet](Spell_pet_auras#pet)           | mediumint(8) | unsigned       | PRI     | NO       | 0           |           | pet id; 0 = all |
| [aura](Spell_pet_auras#aura)         | mediumint(8) | unsigned       |         | NO       | NULL        |           | pet aura id     |

### Description of the fields

#### spell

#### effectId

#### pet

#### aura
