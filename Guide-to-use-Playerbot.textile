h2. Key: 

|_.<font color=grey>IDENTIFIER</font>|_.<font color=grey>DESCRIPTION</font>|
|<font color=red>*_BOTNAME_*</font>|name of bot character|
|<font color=blue>*_FRIEND_*</font>|name bot or player character|
|<font color=brown>*_TARGET_*</font>|select target player, corpse or npc (non-player character)|
|&#124; |logical OR|
|*&*|logical AND|
|*..*|multiple instances|
|*/command*|MACRO commands|
|*/s*|chat: SAY|
|*/p*|chat: PARTY|
|*/t* <font color=red>*_BOTNAME_*</font>|chat: TELL <font color=red>*_BOTNAME_*</font>|
|*/w* <font color=red>*_BOTNAME_*</font>|chat: TELL <font color=red>*_BOTNAME_*</font>|
|*<font color=green>[</font>* _name_ *LINK <font color=green>]</font>*|_name_ = <Spell &#124; Item &#124; Quest &#124; Training &#124; Profession &#124; Gameobject &#124; Auction &#124; Recipe &#124; Mailbox>|
|*(<font color=orangered>shortcut</font>)*|assign *<font color=orangered>shortcut</font>* to command or sub-command|

h3. Available Bot Commands: Playerbot support for MaNGOS, Cmangos & mangosR2

*SAY* commands:

|_.<font color=grey>SYNTAX</font>|_.<font color=grey>DESCRIPTION</font>|
|*.bot add* <font color=red>*_BOTNAME_*</font>|add character to world|
|*.bot remove* <font color=red>*_BOTNAME_*</font>|remove character from world|

h4. Currrently only used with the follow playerbot code: portalzero & portalclassic
(All other code uses the new revised 'orders combat' command, to set bot roles)

|_.<font color=grey>SYNTAX</font>|_.<font color=grey>DESCRIPTION</font>|
|*.bot < co &#124; combatorder >* <font color=red>*_BOTNAME_*</font> <TANK &#124; HEAL &#124; ASSIST <font color=blue>*_FRIEND_*</font> &#124; PROTECT <font color=blue>*_FRIEND_*</font>>|assign bot role|

*MACRO* commands:

|_.<font color=grey>SYNTAX</font>|_.<font color=grey>DESCRIPTION</font>|
|*/invite* <font color=red>*_BOTNAME_*</font>|bot will auto accept party invite|
|*/uninvite* <font color=red>*_BOTNAME_*</font>|bot will auto accept party uninvite|

*TELL/PARTY* commands:
(Please refer to playerbot online help. Some commands may not be available for certain cores)

|_.<font color=grey>SYNTAX</font>|_.<font color=grey>DESCRIPTION</font>|
|*<font color=green>assist <font color=brown> _TARGET_</font></font>*|bots(s) assist the character(s) listed, attacking as they attack.|
|*<font color=green>attack <font color=brown> _TARGET_</font></font>*|Order bot(s) to attack selected target, similar to the way a pet can attack|
|*<font color=green>auction</font>*|Order bot(s) to seek out auctioneer closeby and display bot's active *^<font color=red>1</font>^<font color=green>[</font> Auction LINK <font color=green>]</font>..*|
|*<font color=green>auction</font> (<font color=blue>a</font>)<font color=blue>dd</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Order bot to seek out auctioneer closeby and add *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|
|*<font color=green>auction</font> (<font color=blue>r</font>)<font color=blue>emove</font> ^<font color=red>1</font>^<font color=green>[</font> Auction LINK <font color=green>]</font>..*|Order bot to seek out auctioneer closeby and remove *^<font color=red>1</font>^<font color=green>[</font> Auction LINK <font color=green>]</font>..*|
|*<font color=green>bank</font>*|Order bot(s) to seek out banker closeby and list bot's bank balance|
|*<font color=green>bank</font> (<font color=blue>d</font>)<font color=blue>eposit</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Order bot to seek out banker closeby and deposit *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..* in bank|
|*<font color=green>bank</font> (<font color=blue>w</font>)<font color=blue>ithdraw</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Order bot to seek out banker closeby and withdraw *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..* from bank|
|*(<font color=orangered>b</font>)<font color=green>uy</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Order bot to seek out vendor closeby and buy *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|
|*(<font color=orangered>c</font>)<font color=green>ast</font> <font color=orange>SPELL</font>*|*<font color=orange>SPELL</font> = <SPELLID &#124; SPELLNAME &#124; ^<font color=red>1</font>^<font color=green>[</font> Spell LINK <font color=green>]</font> >*|
|*<font color=green>collect</font>*| Shows collect *<font color=orange>OBJECT</font>* options and current collect status|
|*<font color=green>collect</font> <font color=orange>OBJECT</font>*|Sets collect status, *<font color=orange>OBJECT</font> = [ <font color=gold>all none combat loot objects profession quest</font> ]*|
|*<font color=green>craft </font> ^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>..*|Creates all listed recipes, if known by bot|
|*<font color=green>craft </font> ^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font><font color=brown> all</font>*|Creates multiple instances of a recipe, if known by bot|
|*<font color=green>craft </font>(<font color=blue>a</font>)<font color=blue>lchemy</font>*|Shows all alchemy recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>craft </font>(<font color=blue>b</font>)<font color=blue>lacksmithing</font>*|Shows all blacksmithing recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>craft </font>(<font color=blue>c</font>)<font color=blue>ooking</font>*|Shows all cooking recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>craft </font>(<font color=blue>e</font>)<font color=blue>ngineering</font>*|Shows all engineering recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learn by bot|
|*<font color=green>craft </font>(<font color=blue>f</font>)<font color=blue>irstaid</font>*|Shows all first-aid recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>craft </font>(<font color=blue>i</font>)<font color=blue>nscription</font>*|Shows all inscription recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learn by bot|
|*<font color=green>craft </font>(<font color=blue>j</font>)<font color=blue>ewelcrafting</font>*|Shows all jewelcrafting recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>craft </font>(<font color=blue>l</font>)<font color=blue>eatherworking</font>*|Shows all leatherworking recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>craft </font>(<font color=blue>m</font>)<font color=blue>agic</font>*|Shows all craftable enchantment (e.g wands etc..) recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>craft </font>(<font color=blue>s</font>)<font color=blue>melting</font>*|Shows all ore smelting recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>craft </font>(<font color=blue>t</font>)<font color=blue>ailoring</font>*|Shows all tailoring recipes *^<font color=red>1</font>^<font color=green>[</font> Recipe LINK <font color=green>]</font>*, if learnt by bot|
|*<font color=green>drop</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Order bot to drop and destroy specified items *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|
|*<font color=green>drop </font><font color=blue>all</font>*|When bot(s) inventory becomes full, drop all low level <font color=grey>*[GREY]*</fonts> items.|
|*<font color=green>enchant </font>*|Lists all enchantments *^<font color=red>1</font>^<font color=green>[</font> Spell LINK <font color=green>]</font>*, learnt by the bot|
|*<font color=green>enchant </font> ^<font color=red>1</font>^<font color=green>[</font> Spell LINK <font color=green>]</font>..*|Enchants selected tradable *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>* either equipped or in bag|
|*(<font color=orangered>e</font>)<font color=green>quip</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Equip bot with containers, weapons, armour and trinkets from it's inventory|
|*(<font color=orangered>e</font>)<font color=green>quip</font><font color=blue> auto </font><font color=brown>on</font>*|Turns auto equip ON, also does an immediate check|
|*(<font color=orangered>e</font>)<font color=green>quip</font><font color=blue> auto </font><font color=brown>off</font>*|Turns auto equip OFF.|
|*(<font color=orangered>e</font>)<font color=green>quip</font><font color=blue> auto </font><font color=brown>once</font>*|Runs auto equip once, then turns it off.|
|*(<font color=orangered>e</font>)<font color=green>quip</font><font color=blue> info</font>*|Shows equip auto toggle status (ON/OFF).|
|*(<font color=orangered>f</font>)<font color=green>ind</font> ^<font color=red>1</font>^<font color=green>[</font> Gameobject LINK <font color=green>]</font>*|Order bot(s) to locate *^<font color=red>1</font>^<font color=green>[</font> Gameobject LINK <font color=green>]</font>* and then wait. Useful in quest objectives|
|*<font color=green>follow</font>*|Order bot(s) to follow player; will also revive bot if dead or teleport bot if far away|
|*<font color=green>follow </font><font color=blue>auto</font>*|Toggles Automatic Follow Distance (ON/OFF)|
|*<font color=green>follow </font><font color=blue>info</font>*|Shows bot(s) current Automatic Follow Distance, toggle status (ON/OFF)|
|*<font color=green>follow </font><font color=blue>far</font>*|bot(s) follow, farther from master.|
|*<font color=green>follow </font><font color=blue>near</font>*|bot(s) follow, closer to master|
|*<font color=green>follow </font><font color=blue>reset</font>*|bot(s) follow distance reset to original default|
|*(<font color=orangered>g</font>)<font color=green>et</font> ^<font color=red>1</font>^<font color=green>[</font> Gameobject LINK <font color=green>]</font>..*|Fetch the selected *^<font color=red>1</font>^<font color=green>[</font> Gameobject LINK <font color=green>]</font>..* and then return to the player|
|*<font color=green>orders</font>*|Shows bot's combat orders|
|*<font color=green>orders </font><font color=blue>delay <0-10> </font>*|Activates a delay before bot(s) start fighting.|
|*<font color=green>orders </font><font color=blue>combat </font><font color=brown>ASSIST </font><font color=blue>_FRIEND_</font>*|Assist the linked friendly target, focusing our killing power.|
|*<font color=green>orders </font><font color=blue>combat </font><font color=brown>HEAL </font>*|Order bot to heal. Best used on shamans, priests, druids or paladins.|
|*<font color=green>orders </font><font color=blue>combat </font><font color=brown>PROTECT </font><font color=blue>_FRIEND_</font>*|Protect the listed friendly target, attempting to keep aggro away from the target.|
|*<font color=green>orders </font><font color=blue>combat </font><font color=brown>TANK </font>*|Order bot to tank. Best used on paladins, warriors, druids or death knights.|
|*<font color=green>orders </font><font color=blue>combat </font><font color=brown>RESET </font>*|Resets bot combat orders, as if they'd never been given at all.|
|*<font color=green>orders </font><font color=blue>resume</font>*|Resume combat orders to what they were before logout.|
|*<font color=green>mail </font><font color=blue>inbox</font> ^<font color=red>1</font>^<font color=green>[</font> Mailbox LINK <font color=green>]</font>*|Lists all bot mail from selected *^<font color=red>1</font>^<font color=green>[</font> Mailbox LINK<font color=green>]</font>*. Mail is indexed by *^<font color=red>1</font>^<font color=green>[</font> Mail ID <font color=green>]</font>..*|
|*<font color=green>mail </font><font color=blue>getcash</font> ^<font color=red>1</font>^<font color=green>[</font> Mail ID <font color=green>]</font>..*|Gets money from all selected *^<font color=red>1</font>^<font color=green>[</font> Mail ID <font color=green>]</font>..*|
|*<font color=green>mail </font><font color=blue>getitem</font> ^<font color=red>1</font>^<font color=green>[</font> Mail ID <font color=green>]</font>..*|Gets items from all selected *^<font color=red>1</font>^<font color=green>[</font> Mail ID <font color=green>]</font>..*|
|*<font color=green>mail </font><font color=blue>delete</font> ^<font color=red>1</font>^<font color=green>[</font> Mail ID <font color=green>]</font>..*|Deletes all selected *^<font color=red>1</font>^<font color=green>[</font> Mail ID <font color=green>]</font>..*|
|*<font color=green>pet</font> <font color=blue>abandon</font>*|Abandons active hunter pet.|
|*<font color=green>pet</font><font color=blue> tame </font><font color=brown> _TARGET_</font>*|Tame selected creature, if bot has 'tame beast' spell in spellbook|
|*<font color=green>pet</font> <font color=blue>spells</font>*|Shows spells known to bot's pet. Autocast spells will be shown in green|
|*<font color=green>pet</font> <font color=blue>cast</font> <font color=orange>SPELL</font>*|*<font color=orange>SPELL</font> = <SPELLID &#124; SPELLNAME &#124; ^<font color=red>1</font>^<font color=green>[</font> Spell LINK <font color=green>]</font>>*|
|*<font color=green>pet</font> <font color=blue>toggle</font> <font color=orange>SPELL</font>*|*<font color=orange>SPELL</font> = <SPELLID &#124; SPELLNAME &#124; ^<font color=red>1</font>^<font color=green>[</font> Spell LINK <font color=green>]</font>>* toggles autocast for a given spell|
|*<font color=green>pet</font> <font color=blue>state</font>*|Shows current react *<font color=orange>MODE</font>* of bot's pet|
|*<font color=green>pet</font> <font color=blue>react</font> <font color=orange>MODE</font>*|*<font color=orange>MODE</font> = <(<font color=gold>a</font>)<font color=gold>ggresive</font> &#124; (<font color=gold>d</font>)<font color=gold>efensive</font> &#124; (<font color=gold>p</font>)<font color=gold>assive</font>>*|
|*<font color=green>process </font>(<font color=blue>d</font>)<font color=blue>isenchant</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Disenchants a green coloured *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>* or better|
|*<font color=green>process </font>(<font color=blue>m</font>)<font color=blue>ill</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Grinds 5 herbs *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>* to produce pigments|
|*<font color=green>process </font>(<font color=blue>p</font>)<font color=blue>rospect</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Searches 5 metal ore *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>* for precious gems|
|*<font color=green>pull </font><font color=brown> _TARGET_</font>*|Pulls the target in a coordinated party/raid manner.|
|*<font color=green>pull </font><font color=blue>test</font>*|bot(s) tell you if they can pull at all (can be used anywhere).|
|*<font color=green>pull </font><font color=blue>ready</font>*|bot(s) tell you if they're ready to pull *right now* (to be used on location with valid target).|
|*<font color=green>quest</font>*|List bot's current quests|
|*<font color=green>quest</font> (<font color=blue>a</font>)<font color=blue>dd</font> ^<font color=red>1</font>^<font color=green>[</font> Quest LINK <font color=green>]</font>..*|Order bot(s) to seek out questgiver closeby and add *^<font color=red>1</font>^<font color=green>[</font> Quest LINK <font color=green>]</font>..*|
|*<font color=green>quest</font> (<font color=blue>d</font>)<font color=blue>rop</font> ^<font color=red>1</font>^<font color=green>[</font> Quest LINK <font color=green>]</font>*|Order bot(s) to abandon *^<font color=red>1</font>^<font color=green>[</font> Quest LINK <font color=green>]</font>*|
|*<font color=green>quest</font> (<font color=blue>e</font>)<font color=blue>nd</font>*|Order bot(s) to seek out questgiver closeby and turn in all relevant completed quests|
|*<font color=green>quest</font> (<font color=blue>r</font>)<font color=blue>eport</font>*|Reports all items, creatures or gameobjects the bot(s)need to finish quests|
|*<font color=green>quest</font> (<font color=blue>l</font>)<font color=blue>ist</font>*|Orders bot(s) to seek out questgiver and show new available *^<font color=red>1</font>^<font color=green>[</font> Quest LINK <font color=green>]</font>..*|
|*<font color=green>quest</font> (<font color=blue>c</font>)<font color=blue>omplete</font> ^<font color=red>1</font>^<font color=green>[</font> Quest LINK <font color=green>]</font>*|Autocompletes (GM Approved) quests, available in database|
|*<font color=green>repair</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Order bot to seek out armourer closeby and repair selected *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|
|*<font color=green>repair </font><font color=blue>all</font>*|Order bot(s) to seek out armourer closeby and repair all damaged items equipped, or in bags|
|*<font color=green>reset</font>*|Reset states, orders and loot list|
|*(<font color=orangered>s</font>)<font color=green>ell</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Order bot to seek out vendor closeby and sell *^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|
|*(<font color=orangered>s</font>)<font color=green>ell </font></font><font color=blue>all</font>*|One off sale (command does not persist) of all low level white items.|
|*<font color=green>skill</font>*|lists bot(s) *^<font color=red>1</font>^<font color=green>[</font> Profession LINK <font color=green>]</font>..* primary professions and weapon skills|
|*<font color=green>skill</font> (<font color=blue>l</font>)<font color=blue>earn</font>*|Order bot(s) to seek out trainer closeby and list available *^<font color=red>1</font>^<font color=green>[</font> Training LINK <font color=green>]</font>..*|
|*<font color=green>skill</font> <font color=blue>(<font color=blue>l</font>)earn</font> ^<font color=red>1</font>^<font color=green>[</font> Training LINK <font color=green>]</font>..*|Order bot to seek out trainer closeby and learn *^<font color=red>1</font>^<font color=green>[</font> Training LINK <font color=green>]</font>..*|
|*<font color=green>skill</font> <font color=blue>(<font color=blue>u</font>)nlearn</font> ^<font color=red>1</font>^<font color=green>[</font> Profession LINK <font color=green>]</font>*|Order bot to seek out trainer closeby & unlearn *^<font color=red>1</font>^<font color=green>[</font> Profession LINK <font color=green>]</font>* & associated spells|
|*<font color=green>spells</font>*|Shows all spells known to bot(s)|
|*<font color=green>stats</font>*|Shows bot(s) available money, free inventory space and estimated item repair costs|
|*<font color=green>stay</font>*|Order bot(s) to stand and not follow the player|
|*<font color=green>summon</font>*|Teleport bot(s) near the player|
|*<font color=green>survey</font>*|Shows all available *^<font color=red>1</font>^<font color=green>[</font> Gameobject LINK <font color=green>]</font>..*, within a local perimeter around the bot|
|*<font color=green>use</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>..*|Use item (e.g food, drink, etc)|
|*<font color=green>use</font> ^<font color=red>1</font>^<font color=green>[</font> Item LINK <font color=green>]</font>* <font color=brown>*_TARGET_*</font>|Use item on <font color=brown>*_TARGET_*</font> (e.g quest item)|
</p>

h3. Additional Bot Commands: Playerbot for MaNGOS

|_.<font color=grey>SYNTAX</font>|_.<font color=grey>DESCRIPTION</font>|
|*<font color=green>talent</font>*|Lists bot(s) *^<font color=red>1</font>^<font color=green>[</font> Talent LINK <font color=green>]</font>..* & *^<font color=red>1</font>^<font color=green>[</font> Glyph LINK <font color=green>]</font>..*, unspent talent points & cost to reset all talents|
|*<font color=green>talent</font> <font color=blue>learn</font> ^<font color=red>1</font>^<font color=green>[</font> Talent LINK <font color=green>]</font>..*|Learn selected talent for bot *[Inspect->Talent]* tab or *^<font color=red>1</font>^<font color=green>[</font> Talent LINK <font color=green>]</font>..*|
|*<font color=green>talent</font> <font color=blue>reset</font>*|Order bot to seek out class trainer closeby and reset all talents *^<font color=red>2</font>^*|
|*<font color=green>talent</font> <font color=blue>spec</font>*|Lists all talent specs bot(s) can use (Indexed numerically #).|
|*<font color=green>talent</font> <font color=blue>spec #</font>*|bot(s) will follow this talent spec.|

*^<font color=red>1</font>^* To select *<font color=green>[</font>* _name_ *LINK <font color=green>]</font>, &#60;Hold Shift Key&#62;&#60;Left Mouse Click On Link&#62;*.
*^<font color=red>2</font>^* Tax increases per bot, each time talents are reset.
