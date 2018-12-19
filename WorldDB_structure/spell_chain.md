Back to [world database](mangosdb_struct) list of tables.

The \`spell\_chain\` table
--------------------------

This table defines spell chains. A spell chain is a series of spells which all share the same name and all do the same thing; however, each has a different rank and as the rank increases, so does the spell damage/heal/etc values. This table also controls what spells are replaced by their more powerful later ranks; however, that is also decided by other factors as well (if mana costs for both spells are the same, etc). All fields in this table except rank are spell IDs from Spell.dbc.

### Structure

| **Field**                               | **Type**   | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------|------------|----------|---------|-------------|-----------|
| [spell\_id](Spell_chain#spell_id)       | int(5)     | NO       | PRI     | 0           |           |
| [prev\_spell](Spell_chain#prev_spell)   | int(5)     | NO       |         | 0           |           |
| [first\_spell](Spell_chain#first_spell) | int(5)     | NO       |         | 0           |           |
| [rank](Spell_chain#rank)                | tinyint(4) | NO       |         | 0           |           |

### Description of the fields

#### spell\_id

The spell ID of the spell we are looking at that is in a chain.

#### prev\_spell

The spell that came before the spell in [spell\_id](#spell_id). If the spell defined above is the first rank, then this field MUST be 0. If the spell chain is such that new ranks supersede older ranks, then the spell in this field will be unlearned when the spell in [spell\_id](#spell_id) is learned.

#### first\_spell

The very first spell in the chain. The spell put in this field is usually the Rank 1 spell version in the chain. If the ID used in [spell\_id](#spell_id) is equal to the ID in this field (meaning that the spell we are looking at is the first one in the chain), then the rank must be either 0 or 1.

#### rank

This field specifies what rank the spell in [spell\_id](#spell_id) has.
