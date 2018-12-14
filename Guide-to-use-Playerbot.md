Key:
----

| <font color=grey>IDENTIFIER</font>                                                                                  | <font color=grey>DESCRIPTION</font>                                                                                                       |
|---------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| <font color=red>***BOTNAME***</font>                                                                                | name of bot character                                                                                                                     |
| <font color=blue>***FRIEND***</font>                                                                                | name bot or player character                                                                                                              |
| <font color=brown>***TARGET***</font>                                                                               | select target player, corpse or npc (non-player character)                                                                                |
|                                                                                                                     |                                                                                                                                           |
| **&**                                                                                                               | logical AND                                                                                                                               |
| **..**                                                                                                              | multiple instances                                                                                                                        |
| **/command**                                                                                                        | MACRO commands                                                                                                                            |
| **/s**                                                                                                              | chat: SAY                                                                                                                                 |
| **/p**                                                                                                              | chat: PARTY                                                                                                                               |
| **/t** <font color=red>***BOTNAME***</font>                                                                         | chat: TELL <font color=red>***BOTNAME***</font>                                                                                           |
| **/w** <font color=red>***BOTNAME***</font>                                                                         | chat: TELL <font color=red>***BOTNAME***</font>                                                                                           |
| **<span style="text-align:left;">font color=green&gt;\[</font></span>** *name* **LINK <font color=green>\]</font>** | *name* = <Spell &#124; Item &#124; Quest &#124; Training &#124; Profession &#124; Gameobject &#124; Auction &#124; Recipe &#124; Mailbox> |
| **<span class="color=orangered>shortcut</font> <font"></span>**                                                     | assign **<span style="text-align:left;">font color=orangered&gt;shortcut</font></span>** to command or sub-command                        |

### Available Bot Commands: Playerbot support for MaNGOS, Cmangos & mangosR2

**SAY** commands:

| <font color=grey>SYNTAX</font>                       | <font color=grey>DESCRIPTION</font> |
|------------------------------------------------------|-------------------------------------|
| **.bot add** <font color=red>***BOTNAME***</font>    | add character to world              |
| **.bot remove** <font color=red>***BOTNAME***</font> | remove character from world         |

#### Currrently only used with the follow playerbot code: portalzero & portalclassic

(All other code uses the new revised 'orders combat' command, to set bot roles)

| <font color=grey>SYNTAX</font> | <font color=grey>DESCRIPTION</font>                                                                                            |
|--------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| \*\*.bot &lt; co               | combatorder &gt;\*\* <font color=red>***BOTNAME***</font> <TANK &#124; HEAL &#124; ASSIST <font color=blue>***FRIEND***</font> |

**MACRO** commands:

| <font color=grey>SYNTAX</font>                     | <font color=grey>DESCRIPTION</font> |
|----------------------------------------------------|-------------------------------------|
| **/invite** <font color=red>***BOTNAME***</font>   | bot will auto accept party invite   |
| **/uninvite** <font color=red>***BOTNAME***</font> | bot will auto accept party uninvite |

**TELL/PARTY** commands:
(Please refer to playerbot online help. Some commands may not be available for certain cores)

|*.<font color=grey>SYNTAX</font>|*.<font color=grey>DESCRIPTION</font>|
|**<span style="text-align:left;">font color=green&gt;assist <font color=brown> *TARGET*</font></font></span>**|bots(s) assist the character(s) listed, attacking as they attack.|
|**<span style="text-align:left;">font color=green&gt;attack <font color=brown> *TARGET*</font></font></span>**|Order bot(s) to attack selected target, similar to the way a pet can attack|
|**<span style="text-align:left;">font color=green&gt;auction</font></span>**|Order bot(s) to seek out auctioneer closeby and display bot's active **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Auction LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;auction</font> (<font color=blue>a</font>)<font color=blue>dd</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Order bot to seek out auctioneer closeby and add **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;auction</font> (<font color=blue>r</font>)<font color=blue>emove</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Auction LINK <font color=green>\]</font>..</span>**|Order bot to seek out auctioneer closeby and remove **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Auction LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;bank</font></span>**|Order bot(s) to seek out banker closeby and list bot's bank balance|
|**<span style="text-align:left;">font color=green&gt;bank</font> (<font color=blue>d</font>)<font color=blue>eposit</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Order bot to seek out banker closeby and deposit **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..** in bank|
|**<span style="text-align:left;">font color=green&gt;bank</font> (<font color=blue>w</font>)<font color=blue>ithdraw</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Order bot to seek out banker closeby and withdraw **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..** from bank|
|**<span class="color=orangered>b</font> <font"><font color=green>uy</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Order bot to seek out vendor closeby and buy **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..**|
|**<span class="color=orangered>c</font> <font"><font color=green>ast</font> <font color=orange>SPELL</font></span>**|**<span style="text-align:left;">font color=orange&gt;SPELL</font> = <SPELLID &#124; SPELLNAME &#124; ^<font color=red>1</font>^<font color=green>\[</font> Spell LINK <font color=green>\]</font> &gt;</span>**|
|**<span style="text-align:left;">font color=green&gt;collect</font></span>**| Shows collect **<span style="text-align:left;">font color=orange&gt;OBJECT</font></span>** options and current collect status|
|**<span style="text-align:left;">font color=green&gt;collect</font> <font color=orange>OBJECT</font></span>**|Sets collect status, **<span style="text-align:left;">font color=orange&gt;OBJECT</font> = \[ <font color=gold>all none combat loot objects profession quest</font> \]</span>**|
|**<span style="text-align:left;">font color=green&gt;craft </font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>..</span>**|Creates all listed recipes, if known by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font><font color=brown> all</font></span>**|Creates multiple instances of a recipe, if known by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>a</font>)<font color=blue>lchemy</font></span>**|Shows all alchemy recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>b</font>)<font color=blue>lacksmithing</font></span>**|Shows all blacksmithing recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>c</font>)<font color=blue>ooking</font></span>**|Shows all cooking recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>e</font>)<font color=blue>ngineering</font></span>**|Shows all engineering recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learn by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>f</font>)<font color=blue>irstaid</font></span>**|Shows all first-aid recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>i</font>)<font color=blue>nscription</font></span>**|Shows all inscription recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learn by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>j</font>)<font color=blue>ewelcrafting</font></span>**|Shows all jewelcrafting recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>l</font>)<font color=blue>eatherworking</font></span>**|Shows all leatherworking recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>m</font>)<font color=blue>agic</font></span>**|Shows all craftable enchantment (e.g wands etc..) recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>s</font>)<font color=blue>melting</font></span>**|Shows all ore smelting recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;craft </font>(<font color=blue>t</font>)<font color=blue>ailoring</font></span>**|Shows all tailoring recipes **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Recipe LINK <font color=green>\]</font>**, if learnt by bot|
|**<span style="text-align:left;">font color=green&gt;drop</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Order bot to drop and destroy specified items **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;drop </font><font color=blue>all</font></span>**|When bot(s) inventory becomes full, drop all low level <font color=grey>**<span lang="GREY"></span>**</fonts> items.|
|**<span style="text-align:left;">font color=green&gt;enchant </font></span>**|Lists all enchantments **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Spell LINK <font color=green>\]</font>**, learnt by the bot|
|**<span style="text-align:left;">font color=green&gt;enchant </font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Spell LINK <font color=green>\]</font>..</span>**|Enchants selected tradable **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>** either equipped or in bag|
|**<span class="color=orangered>e</font> <font"><font color=green>quip</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Equip bot with containers, weapons, armour and trinkets from it's inventory|
|**<span class="color=orangered>e</font> <font"><font color=green>quip</font><font color=blue> auto </font><font color=brown>on</font></span>**|Turns auto equip ON, also does an immediate check|
|**<span class="color=orangered>e</font> <font"><font color=green>quip</font><font color=blue> auto </font><font color=brown>off</font></span>**|Turns auto equip OFF.|
|**<span class="color=orangered>e</font> <font"><font color=green>quip</font><font color=blue> auto </font><font color=brown>once</font></span>**|Runs auto equip once, then turns it off.|
|**<span class="color=orangered>e</font> <font"><font color=green>quip</font><font color=blue> info</font></span>**|Shows equip auto toggle status (ON/OFF).|
|**<span class="color=orangered>f</font> <font"><font color=green>ind</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Gameobject LINK <font color=green>\]</font></span>**|Order bot(s) to locate **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Gameobject LINK <font color=green>\]</font>** and then wait. Useful in quest objectives|
|**<span style="text-align:left;">font color=green&gt;follow</font></span>**|Order bot(s) to follow player; will also revive bot if dead or teleport bot if far away|
|**<span style="text-align:left;">font color=green&gt;follow </font><font color=blue>auto</font></span>**|Toggles Automatic Follow Distance (ON/OFF)|
|**<span style="text-align:left;">font color=green&gt;follow </font><font color=blue>info</font></span>**|Shows bot(s) current Automatic Follow Distance, toggle status (ON/OFF)|
|**<span style="text-align:left;">font color=green&gt;follow </font><font color=blue>far</font></span>**|bot(s) follow, farther from master.|
|**<span style="text-align:left;">font color=green&gt;follow </font><font color=blue>near</font></span>**|bot(s) follow, closer to master|
|**<span style="text-align:left;">font color=green&gt;follow </font><font color=blue>reset</font></span>**|bot(s) follow distance reset to original default|
|**<span class="color=orangered>g</font> <font"><font color=green>et</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Gameobject LINK <font color=green>\]</font>..</span>**|Fetch the selected **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Gameobject LINK <font color=green>\]</font>..** and then return to the player|
|**<span style="text-align:left;">font color=green&gt;orders</font></span>**|Shows bot's combat orders|
|**<span style="text-align:left;">font color=green&gt;orders </font><font color=blue>delay &lt;0-10&gt; </font></span>**|Activates a delay before bot(s) start fighting.|
|**<span style="text-align:left;">font color=green&gt;orders </font><font color=blue>combat </font><font color=brown>ASSIST </font><font color=blue>*FRIEND*</font></span>**|Assist the linked friendly target, focusing our killing power.|
|**<span style="text-align:left;">font color=green&gt;orders </font><font color=blue>combat </font><font color=brown>HEAL </font></span>**|Order bot to heal. Best used on shamans, priests, druids or paladins.|
|**<span style="text-align:left;">font color=green&gt;orders </font><font color=blue>combat </font><font color=brown>PROTECT </font><font color=blue>*FRIEND*</font></span>**|Protect the listed friendly target, attempting to keep aggro away from the target.|
|**<span style="text-align:left;">font color=green&gt;orders </font><font color=blue>combat </font><font color=brown>TANK </font></span>**|Order bot to tank. Best used on paladins, warriors, druids or death knights.|
|**<span style="text-align:left;">font color=green&gt;orders </font><font color=blue>combat </font><font color=brown>RESET </font></span>**|Resets bot combat orders, as if they'd never been given at all.|
|**<span style="text-align:left;">font color=green&gt;orders </font><font color=blue>resume</font></span>**|Resume combat orders to what they were before logout.|
|**<span style="text-align:left;">font color=green&gt;mail </font><font color=blue>inbox</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mailbox LINK <font color=green>\]</font></span>**|Lists all bot mail from selected **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mailbox LINK<font color=green>\]</font>**. Mail is indexed by **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mail ID <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;mail </font><font color=blue>getcash</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mail ID <font color=green>\]</font>..</span>**|Gets money from all selected **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mail ID <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;mail </font><font color=blue>getitem</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mail ID <font color=green>\]</font>..</span>**|Gets items from all selected **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mail ID <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;mail </font><font color=blue>delete</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mail ID <font color=green>\]</font>..</span>**|Deletes all selected **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Mail ID <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;pet</font> <font color=blue>abandon</font></span>**|Abandons active hunter pet.|
|**<span style="text-align:left;">font color=green&gt;pet</font><font color=blue> tame </font><font color=brown> *TARGET*</font></span>**|Tame selected creature, if bot has 'tame beast' spell in spellbook|
|**<span style="text-align:left;">font color=green&gt;pet</font> <font color=blue>spells</font></span>**|Shows spells known to bot's pet. Autocast spells will be shown in green|
|**<span style="text-align:left;">font color=green&gt;pet</font> <font color=blue>cast</font> <font color=orange>SPELL</font></span>**|**<span style="text-align:left;">font color=orange&gt;SPELL</font> = <SPELLID &#124; SPELLNAME &#124; ^<font color=red>1</font>^<font color=green>\[</font> Spell LINK <font color=green>\]</font>&gt;</span>**|
|**<span style="text-align:left;">font color=green&gt;pet</font> <font color=blue>toggle</font> <font color=orange>SPELL</font></span>**|**<span style="text-align:left;">font color=orange&gt;SPELL</font> = <SPELLID &#124; SPELLNAME &#124; ^<font color=red>1</font>^<font color=green>\[</font> Spell LINK <font color=green>\]</font>&gt;</span>** toggles autocast for a given spell|
|**<span style="text-align:left;">font color=green&gt;pet</font> <font color=blue>state</font></span>**|Shows current react **<span style="text-align:left;">font color=orange&gt;MODE</font></span>** of bot's pet|
|**<span style="text-align:left;">font color=green&gt;pet</font> <font color=blue>react</font> <font color=orange>MODE</font></span>**|**<span style="text-align:left;">font color=orange&gt;MODE</font> = &lt;(<font color=gold>a</font>)<font color=gold>ggresive</font> | (<font color=gold>d</font>)<font color=gold>efensive</font> | (<font color=gold>p</font>)<font color=gold>assive</font>&gt;</span>**|
|**<span style="text-align:left;">font color=green&gt;process </font>(<font color=blue>d</font>)<font color=blue>isenchant</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Disenchants a green coloured **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>** or better|
|**<span style="text-align:left;">font color=green&gt;process </font>(<font color=blue>m</font>)<font color=blue>ill</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Grinds 5 herbs **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>** to produce pigments|
|**<span style="text-align:left;">font color=green&gt;process </font>(<font color=blue>p</font>)<font color=blue>rospect</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Searches 5 metal ore **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>** for precious gems|
|**<span style="text-align:left;">font color=green&gt;pull </font><font color=brown> *TARGET*</font></span>**|Pulls the target in a coordinated party/raid manner.|
|**<span style="text-align:left;">font color=green&gt;pull </font><font color=blue>test</font></span>**|bot(s) tell you if they can pull at all (can be used anywhere).|
|**<span style="text-align:left;">font color=green&gt;pull </font><font color=blue>ready</font></span>**|bot(s) tell you if they're ready to pull **right now** (to be used on location with valid target).|
|**<span style="text-align:left;">font color=green&gt;quest</font></span>**|List bot's current quests|
|**<span style="text-align:left;">font color=green&gt;quest</font> (<font color=blue>a</font>)<font color=blue>dd</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Quest LINK <font color=green>\]</font>..</span>**|Order bot(s) to seek out questgiver closeby and add **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Quest LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;quest</font> (<font color=blue>d</font>)<font color=blue>rop</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Quest LINK <font color=green>\]</font></span>**|Order bot(s) to abandon **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Quest LINK <font color=green>\]</font>**|
|**<span style="text-align:left;">font color=green&gt;quest</font> (<font color=blue>e</font>)<font color=blue>nd</font></span>**|Order bot(s) to seek out questgiver closeby and turn in all relevant completed quests|
|**<span style="text-align:left;">font color=green&gt;quest</font> (<font color=blue>r</font>)<font color=blue>eport</font></span>**|Reports all items, creatures or gameobjects the bot(s)need to finish quests|
|**<span style="text-align:left;">font color=green&gt;quest</font> (<font color=blue>l</font>)<font color=blue>ist</font></span>**|Orders bot(s) to seek out questgiver and show new available **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Quest LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;quest</font> (<font color=blue>c</font>)<font color=blue>omplete</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Quest LINK <font color=green>\]</font></span>**|Autocompletes (GM Approved) quests, available in database|
|**<span style="text-align:left;">font color=green&gt;repair</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Order bot to seek out armourer closeby and repair selected **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;repair </font><font color=blue>all</font></span>**|Order bot(s) to seek out armourer closeby and repair all damaged items equipped, or in bags|
|**<span style="text-align:left;">font color=green&gt;reset</font></span>**|Reset states, orders and loot list|
|**<span class="color=orangered>s</font> <font"><font color=green>ell</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Order bot to seek out vendor closeby and sell **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..**|
|**<span class="color=orangered>s</font> <font"><font color=green>ell </font></font><font color=blue>all</font></span>**|One off sale (command does not persist) of all low level white items.|
|**<span style="text-align:left;">font color=green&gt;skill</font></span>**|lists bot(s) **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Profession LINK <font color=green>\]</font>..** primary professions and weapon skills|
|**<span style="text-align:left;">font color=green&gt;skill</font> (<font color=blue>l</font>)<font color=blue>earn</font></span>**|Order bot(s) to seek out trainer closeby and list available **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Training LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;skill</font> <font color=blue>(<font color=blue>l</font>)earn</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Training LINK <font color=green>\]</font>..</span>**|Order bot to seek out trainer closeby and learn **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Training LINK <font color=green>\]</font>..**|
|**<span style="text-align:left;">font color=green&gt;skill</font> <font color=blue>(<font color=blue>u</font>)nlearn</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Profession LINK <font color=green>\]</font></span>**|Order bot to seek out trainer closeby & unlearn **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Profession LINK <font color=green>\]</font>** & associated spells|
|**<span style="text-align:left;">font color=green&gt;spells</font></span>**|Shows all spells known to bot(s)|
|**<span style="text-align:left;">font color=green&gt;stats</font></span>**|Shows bot(s) available money, free inventory space and estimated item repair costs|
|**<span style="text-align:left;">font color=green&gt;stay</font></span>**|Order bot(s) to stand and not follow the player|
|**<span style="text-align:left;">font color=green&gt;summon</font></span>**|Teleport bot(s) near the player|
|**<span style="text-align:left;">font color=green&gt;survey</font></span>**|Shows all available **<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Gameobject LINK <font color=green>\]</font>..**, within a local perimeter around the bot|
|**<span style="text-align:left;">font color=green&gt;use</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font>..</span>**|Use item (e.g food, drink, etc)|
|**<span style="text-align:left;">font color=green&gt;use</font> <sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup><font color=green>\[</font> Item LINK <font color=green>\]</font></span>** <font color=brown>***TARGET***</font>|Use item on <font color=brown>***TARGET***</font> (e.g quest item)|

</p>
### Additional Bot Commands: Playerbot for MaNGOS

<table>
<colgroup>
<col width="40%" />
<col width="59%" />
</colgroup>
<thead>
<tr class="header">
<th><font color=grey>SYNTAX</font></th>
<th><font color=grey>DESCRIPTION</font></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><span style="text-align:left;">font color=green&gt;talent</font></span></strong></td>
<td>Lists bot(s) <strong><sup><span style="text-align:left;">font\ color=red&gt;1</font></span></sup><font color=green>[</font> Talent LINK <font color=green>]</font>..</strong> &amp; <strong><sup><span style="text-align:left;">font\ color=red&gt;1</font></span></sup><font color=green>[</font> Glyph LINK <font color=green>]</font>..</strong>, unspent talent points &amp; cost to reset all talents</td>
</tr>
<tr class="even">
<td><strong><span style="text-align:left;">font color=green&gt;talent</font> <font color=blue>learn</font> <sup><span style="text-align:left;">font\ color=red&gt;1</font></span></sup><font color=green>[</font> Talent LINK <font color=green>]</font>..</span></strong></td>
<td>Learn selected talent for bot <strong>[Inspect-&gt;Talent]</strong> tab or <strong><sup><span style="text-align:left;">font\ color=red&gt;1</font></span></sup><font color=green>[</font> Talent LINK <font color=green>]</font>..</strong></td>
</tr>
<tr class="odd">
<td><strong><span style="text-align:left;">font color=green&gt;talent</font> <font color=blue>reset</font></span></strong></td>
<td>Order bot to seek out class trainer closeby and reset all talents <strong><sup><span style="text-align:left;">font\ color=red&gt;2</font></span></sup></strong></td>
</tr>
<tr class="even">
<td><strong><span style="text-align:left;">font color=green&gt;talent</font> <font color=blue>spec</font></span></strong></td>
<td>Lists all talent specs bot(s) can use (Indexed numerically #).</td>
</tr>
<tr class="odd">
<td><strong><span style="text-align:left;">font color=green&gt;talent</font> <font color=blue>spec #</font></span></strong></td>
<td>bot(s) will follow this talent spec.</td>
</tr>
</tbody>
</table>

**<sup><span style="text-align:left;">font\\ color=red&gt;1</font></span></sup>** To select **<span style="text-align:left;">font color=green&gt;\[</font></span>** *name* **LINK <font color=green>\]</font>, &lt;Hold Shift Key&gt;&lt;Left Mouse Click On Link&gt;**.
**<sup><span style="text-align:left;">font\\ color=red&gt;2</font></span></sup>** Tax increases per bot, each time talents are reset.
