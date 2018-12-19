Back to [world database](mangosdb_struct) list of tables.

The \`item\_required\_target\` table
------------------------------------

These spell effects require a specific target in either alive or dead state (for creatures).

### Structure

| **Field**                                       | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Item_required_target#entry)             | int(6) unsigned  | NO       | PRI     |             |           |
| [type](Item_required_target#type)               | int(8) unsigned  | NO       | PRI     | 0           |           |
| [targetEntry](Item_required_target#targetentry) | int(11) unsigned | NO       | PRI     | 0           |           |

### Description of the fields

#### entry

The item ID. See Items.dbc

#### type

One of these type are available

-   0 = Gameobject
-   1 = Creature
-   2 = Creature who must be dead (killed by Player or Npc)

NOTE: A creature corpse and a creature that *looks* dead are two different things. One is actually dead and the other is just using an emote to appear dead.

#### targetEntry

Can be: [creature\_template.entry](creature_template#entry) or [gameobject\_template.entry](gameobject_template#entry) depending on the choosen type.

This specified entry will be automatically targeted if it is near the player using the item.
