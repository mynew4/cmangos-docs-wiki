Key:
----

| IDENTIFIER              | DESCRIPTION                                                                                                                                     |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **BOTNAME**             | name of bot character                                                                                                                           |
| **FRIEND**              | name bot or player character                                                                                                                    |
| **TARGET**              | select target player, corpse or npc (non-player character)                                                                                      |
| **&#124;**              | logical **OR**                                                                                                                                  |
| **&**                   | logical **AND**                                                                                                                                 |
| **..**                  | multiple instances                                                                                                                              |
| **/command**            | MACRO commands                                                                                                                                  |
| **/s**                  | chat: SAY                                                                                                                                       |
| **/p**                  | chat: PARTY                                                                                                                                     |
| **/t** ***BOTNAME***    | chat: TELL ***BOTNAME***                                                                                                                        |
| **/w** ***BOTNAME***    | chat: TELL ***BOTNAME***                                                                                                                        |
| **[** *name* **LINK\]** | *name* = &lt;Spell &#124; Item &#124; Quest &#124; Training &#124; Profession &#124; Gameobject &#124; Auction &#124; Recipe &#124; Mailbox&gt; |
| **(shortcut)**          | assign **shortcut** to command or sub-command                                                                                                   |

### Available Bot Commands: Playerbot support for MaNGOS, Cmangos & mangosR2

**SAY** commands:

| SYNTAX                        | DESCRIPTION                 |
| ----------------------------- | --------------------------- |
| **.bot add** ***BOTNAME***    | add character to world      |
| **.bot remove** ***BOTNAME*** | remove character from world |

#### Currrently only used with the follow playerbot code: portalzero & portalclassic

(All other code uses the new revised 'orders combat' command, to set bot roles)

| SYNTAX                                                                                                                                 | DESCRIPTION     |
| -------------------------------------------------------------------------------------------------------------------------------------- | --------------- |
| **.bot &lt; co &#124; combatorder &gt;** ***BOTNAME*** &lt;TANK &#124; HEAL &#124; ASSIST ***FRIEND*** &#124; PROTECT ***FRIEND***&gt; | assign bot role |

**MACRO** commands:

| SYNTAX                      | DESCRIPTION                         |
| --------------------------- | ----------------------------------- |
| **/invite** ***BOTNAME***   | bot will auto accept party invite   |
| **/uninvite** ***BOTNAME*** | bot will auto accept party uninvite |

**TELL/PARTY** commands:<br>
(Please refer to playerbot online help. Some commands may not be available for certain cores)

| SYNTAX                                                 | DESCRIPTION                                                                                                                     |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| **assist  *TARGET***                                   | bots(s) assist the character(s) listed, attacking as they attack.                                                               |
| **attack  *TARGET***                                   | Order bot(s) to attack selected target, similar to the way a pet can attack                                                     |
| **auction**                                            | Order bot(s) to seek out auctioneer closeby and display bot's active **<sup>1</sup>\[ Auction LINK \]..**                       |
| **auction (a)dd <sup>1</sup>\[ Item LINK \]..**        | Order bot to seek out auctioneer closeby and add **<sup>1</sup>\[ Item LINK \]..**                                              |
| **auction (r)emove <sup>1</sup>\[ Auction LINK \]..**  | Order bot to seek out auctioneer closeby and remove **<sup>1</sup>\[ Auction LINK \]..**                                        |
| **bank**                                               | Order bot(s) to seek out banker closeby and list bot's bank balance                                                             |
| **bank (d)eposit <sup>1</sup>\[ Item LINK \]..**       | Order bot to seek out banker closeby and deposit **<sup>1</sup>\[ Item LINK \]..** in bank                                      |
| **bank (w)ithdraw <sup>1</sup>\[ Item LINK \]..**      | Order bot to seek out banker closeby and withdraw **<sup>1</sup>\[ Item LINK \]..** from bank                                   |
| **(b)uy <sup>1</sup>\[ Item LINK \]..**                | Order bot to seek out vendor closeby and buy **<sup>1</sup>\[ Item LINK \]..**                                                  |
| **(c)ast SPELL**                                       | **SPELL = &lt;SPELLID &#124; SPELLNAME &#124; <sup>1</sup>\[ Spell LINK \] &gt;**                                               |
| **collect**                                            | Shows collect **OBJECT** options and current collect status                                                                     |
| **collect OBJECT**                                     | Sets collect status, **OBJECT = \[ all &#124; none &#124; combat &#124; loot &#124; objects &#124; profession &#124; quest \]** |
| **craft  <sup>1</sup>\[ Recipe LINK \]..**             | Creates all listed recipes, if known by bot                                                                                     |
| **craft  <sup>1</sup>\[ Recipe LINK \] all**           | Creates multiple instances of a recipe, if known by bot                                                                         |
| **craft (a)lchemy**                                    | Shows all alchemy recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                                                   |
| **craft (b)lacksmithing**                              | Shows all blacksmithing recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                                             |
| **craft (c)ooking**                                    | Shows all cooking recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                                                   |
| **craft (e)ngineering**                                | Shows all engineering recipes **<sup>1</sup>\[ Recipe LINK \]**, if learn by bot                                                |
| **craft (f)irstaid**                                   | Shows all first-aid recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                                                 |
| **craft (i)nscription**                                | Shows all inscription recipes **<sup>1</sup>\[ Recipe LINK \]**, if learn by bot                                                |
| **craft (j)ewelcrafting**                              | Shows all jewelcrafting recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                                             |
| **craft (l)eatherworking**                             | Shows all leatherworking recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                                            |
| **craft (m)agic**                                      | Shows all craftable enchantment (e.g wands etc..) recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                   |
| **craft (s)melting**                                   | Shows all ore smelting recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                                              |
| **craft (t)ailoring**                                  | Shows all tailoring recipes **<sup>1</sup>\[ Recipe LINK \]**, if learnt by bot                                                 |
| **drop <sup>1</sup>\[ Item LINK \]..**                 | Order bot to drop and destroy specified items **<sup>1</sup>\[ Item LINK \]..**                                                 |
| **drop all**                                           | When bot(s) inventory becomes full, drop all low level **\[GREY\]** items.                                                      |
| **enchant **                                           | Lists all enchantments **<sup>1</sup>\[ Spell LINK \]**, learnt by the bot                                                      |
| **enchant  <sup>1</sup>\[ Spell LINK \]..**            | Enchants selected tradable **<sup>1</sup>\[ Item LINK \]** either equipped or in bag                                            |
| **(e)quip <sup>1</sup>\[ Item LINK \]..**              | Equip bot with containers, weapons, armour and trinkets from it's inventory                                                     |
| **(e)quip auto on**                                    | Turns auto equip ON, also does an immediate check                                                                               |
| **(e)quip auto off**                                   | Turns auto equip OFF.                                                                                                           |
| **(e)quip auto once**                                  | Runs auto equip once, then turns it off.                                                                                        |
| **(e)quip info**                                       | Shows equip auto toggle status (ON/OFF).                                                                                        |
| **(f)ind <sup>1</sup>\[ Gameobject LINK \]**           | Order bot(s) to locate **<sup>1</sup>\[ Gameobject LINK \]** and then wait. Useful in quest objectives                          |
| **follow**                                             | Order bot(s) to follow player; will also revive bot if dead or teleport bot if far away                                         |
| **follow auto**                                        | Toggles Automatic Follow Distance (ON/OFF)                                                                                      |
| **follow info**                                        | Shows bot(s) current Automatic Follow Distance, toggle status (ON/OFF)                                                          |
| **follow far**                                         | bot(s) follow, farther from master.                                                                                             |
| **follow near**                                        | bot(s) follow, closer to master                                                                                                 |
| **follow reset**                                       | bot(s) follow distance reset to original default                                                                                |
| **(g)et <sup>1</sup>\[ Gameobject LINK \]..**          | Fetch the selected **<sup>1</sup>\[ Gameobject LINK \]..** and then return to the player                                        |
| **orders**                                             | Shows bot's combat orders                                                                                                       |
| **orders delay &lt;0-10&gt; **                         | Activates a delay before bot(s) start fighting.                                                                                 |
| **orders combat ASSIST *FRIEND***                      | Assist the linked friendly target, focusing our killing power.                                                                  |
| **orders combat HEAL **                                | Order bot to heal. Best used on shamans, priests, druids or paladins.                                                           |
| **orders combat PROTECT *FRIEND***                     | Protect the listed friendly target, attempting to keep aggro away from the target.                                              |
| **orders combat TANK **                                | Order bot to tank. Best used on paladins, warriors, druids or death knights.                                                    |
| **orders combat RESET **                               | Resets bot combat orders, as if they'd never been given at all.                                                                 |
| **orders resume**                                      | Resume combat orders to what they were before logout.                                                                           |
| **mail inbox <sup>1</sup>\[ Mailbox LINK \]**          | Lists all bot mail from selected **<sup>1</sup>\[ Mailbox LINK\]**. Mail is indexed by **<sup>1</sup>\[ Mail ID \]..**          |
| **mail getcash <sup>1</sup>\[ Mail ID \]..**           | Gets money from all selected **<sup>1</sup>\[ Mail ID \]..**                                                                    |
| **mail getitem <sup>1</sup>\[ Mail ID \]..**           | Gets items from all selected **<sup>1</sup>\[ Mail ID \]..**                                                                    |
| **mail delete <sup>1</sup>\[ Mail ID \]..**            | Deletes all selected **<sup>1</sup>\[ Mail ID \]..**                                                                            |
| **pet abandon**                                        | Abandons active hunter pet.                                                                                                     |
| **pet tame  *TARGET***                                 | Tame selected creature, if bot has 'tame beast' spell in spellbook                                                              |
| **pet spells**                                         | Shows spells known to bot's pet. Autocast spells will be shown in green                                                         |
| **pet cast SPELL**                                     | **SPELL = &lt;SPELLID &#124; SPELLNAME &#124; <sup>1</sup>\[ Spell LINK \]&gt;**                                                |
| **pet toggle SPELL**                                   | **SPELL = &lt;SPELLID &#124; SPELLNAME &#124; <sup>1</sup>\[ Spell LINK \]&gt;** toggles autocast for a given spell             |
| **pet state**                                          | Shows current react **MODE** of bot's pet                                                                                       |
| **pet react MODE**                                     | **MODE = &lt;(a)ggresive &#124; (d)efensive &#124; (p)assive&gt;**                                                              |
| **process (d)isenchant <sup>1</sup>\[ Item LINK \]..** | Disenchants a green coloured **<sup>1</sup>\[ Item LINK \]** or better                                                          |
| **process (m)ill <sup>1</sup>\[ Item LINK \]..**       | Grinds 5 herbs **<sup>1</sup>\[ Item LINK \]** to produce pigments                                                              |
| **process (p)rospect <sup>1</sup>\[ Item LINK \]..**   | Searches 5 metal ore **<sup>1</sup>\[ Item LINK \]** for precious gems                                                          |
| **pull  *TARGET***                                     | Pulls the target in a coordinated party/raid manner.                                                                            |
| **pull test**                                          | bot(s) tell you if they can pull at all (can be used anywhere).                                                                 |
| **pull ready**                                         | bot(s) tell you if they're ready to pull **right now** (to be used on location with valid target).                              |
| **quest**                                              | List bot's current quests                                                                                                       |
| **quest (a)dd <sup>1</sup>\[ Quest LINK \]..**         | Order bot(s) to seek out questgiver closeby and add **<sup>1</sup>\[ Quest LINK \]..**                                          |
| **quest (d)rop <sup>1</sup>\[ Quest LINK \]**          | Order bot(s) to abandon **<sup>1</sup>\[ Quest LINK \]**                                                                        |
| **quest (e)nd**                                        | Order bot(s) to seek out questgiver closeby and turn in all relevant completed quests                                           |
| **quest (r)eport**                                     | Reports all items, creatures or gameobjects the bot(s)need to finish quests                                                     |
| **quest (l)ist**                                       | Orders bot(s) to seek out questgiver and show new available **<sup>1</sup>\[ Quest LINK \]..**                                  |
| **quest (c)omplete <sup>1</sup>\[ Quest LINK \]**      | Autocompletes (GM Approved) quests, available in database                                                                       |
| **repair <sup>1</sup>\[ Item LINK \]..**               | Order bot to seek out armourer closeby and repair selected **<sup>1</sup>\[ Item LINK \]..**                                    |
| **repair all**                                         | Order bot(s) to seek out armourer closeby and repair all damaged items equipped, or in bags                                     |
| **reset**                                              | Reset states, orders and loot list                                                                                              |
| **(s)ell <sup>1</sup>\[ Item LINK \]..**               | Order bot to seek out vendor closeby and sell **<sup>1</sup>\[ Item LINK \]..**                                                 |
| **(s)ell all**                                         | One off sale (command does not persist) of all low level white items.                                                           |
| **skill**                                              | lists bot(s) **<sup>1</sup>\[ Profession LINK \]..** primary professions and weapon skills                                      |
| **skill (l)earn**                                      | Order bot(s) to seek out trainer closeby and list available **<sup>1</sup>\[ Training LINK \]..**                               |
| **skill (l)earn <sup>1</sup>\[ Training LINK \]..**    | Order bot to seek out trainer closeby and learn **<sup>1</sup>\[ Training LINK \]..**                                           |
| **skill (u)nlearn <sup>1</sup>\[ Profession LINK \]**  | Order bot to seek out trainer closeby & unlearn **<sup>1</sup>\[ Profession LINK \]** & associated spells                       |
| **spells**                                             | Shows all spells known to bot(s)                                                                                                |
| **stats**                                              | Shows bot(s) available money, free inventory space and estimated item repair costs                                              |
| **stay**                                               | Order bot(s) to stand and not follow the player                                                                                 |
| **summon**                                             | Teleport bot(s) near the player                                                                                                 |
| **survey**                                             | Shows all available **<sup>1</sup>\[ Gameobject LINK \]..**, within a local perimeter around the bot                            |
| **use <sup>1</sup>\[ Item LINK \]..**                  | Use item (e.g food, drink, etc)                                                                                                 |
| **use <sup>1</sup>\[ Item LINK \]** ***TARGET***       | Use item on ***TARGET*** (e.g quest item)                                                                                       |


### Additional Bot Commands: Playerbot for MaNGOS

| SYNTAX                                         | DESCRIPTION                                                                                                                          |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **talent**                                     | Lists bot(s) **<sup>1</sup>[ Talent LINK ]..** & **<sup>1</sup>[ Glyph LINK ]..**, unspent talent points & cost to reset all talents |
| **talent learn <sup>1</sup>[ Talent LINK ]..** | Learn selected talent for bot **[Inspect-&gt;Talent]** tab or **<sup>1</sup>[ Talent LINK ]..**                                      |
| **talent reset**                               | Order bot to seek out class trainer closeby and reset all talents **<sup>2</sup>**                                                   |
| **talent spec**                                | Lists all talent specs bot(s) can use (Indexed numerically #).                                                                       |
| **talent spec #**                              | bot(s) will follow this talent spec.                                                                                                 |

**<sup>1</sup>** To select **\[** *name* **LINK \], &lt;Hold Shift Key&gt;&lt;Left Mouse Click On Link&gt;**.  
**<sup>2</sup>** Tax increases per bot, each time talents are reset.
