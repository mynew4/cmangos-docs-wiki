Back to "world database":mangosdb_struct list of tables.

h2. The `item&#95;required&#95;target` table

These spell effects require a specific target in either alive or dead state (for creatures).

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"entry":Item_required_target#entry|int(6) unsigned|NO|PRI|||
|"type":Item_required_target#type|int(8) unsigned|NO|PRI|0||
|"targetEntry":Item_required_target#targetentry|int(11) unsigned|NO|PRI|0||


h3. Description of the fields

h4. entry

The item ID. See Items.dbc

h4. type

One of these type are available

* 0 = Gameobject
* 1 = Creature
* 2 = Creature who must be dead (killed by Player or Npc)

NOTE: A creature corpse and a creature that _looks_ dead are two different things. One is actually dead and the other is just using an emote to appear dead.

h4. targetEntry

Can be: "creature&#95;template.entry":creature_template#entry or "gameobject&#95;template.entry":gameobject_template#entry depending on the choosen type.

This specified entry will be automatically targeted if it is near the player using the item.
