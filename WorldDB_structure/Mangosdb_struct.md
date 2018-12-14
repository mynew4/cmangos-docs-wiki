### This is the list of tables in the regular 'mangos' database

(Reloadable) - are in-game reloadable with the .reload command.

(Core) - Changes to these tables are to be commited and reviewed in CMaNGOS-Core Repositories NOT CMaNGOS-DB Repositories due to their complexity and relations.

(Classic) (TBC) (WotLK) (Cata) - used since or only in a certain version of CMaNGOS-Core

<table>
<tbody>
<tr class="odd">
<td>Table</td>
<td>Content</td>
</tr>
<tr class="even">
<td>&quot;achievement_criteria_requirement&quot;:achievement_criteria_requirement</td>
<td>contains what need to be done to complete an achievement criteria.</td>
</tr>
<tr class="odd">
<td>&quot;achievement_reward&quot;:achievement_reward</td>
<td>contains the rewards for achievements added with Wrath of the Lichking.</td>
</tr>
<tr class="even">
<td><a href="areatrigger_involvedrelation">areatrigger_involvedrelation</a><br />
(Reloadable)</td>
<td>Enable a trigger to finish one condition of a quest (explore)</td>
</tr>
<tr class="odd">
<td><a href="areatrigger_tavern">areatrigger_tavern</a><br />
(Reloadable)</td>
<td>Enable a trigger when player enters a city or tavern. This causes the player to enter a resting state.</td>
</tr>
<tr class="even">
<td><a href="areatrigger_teleport">areatrigger_teleport</a><br />
(Reloadable)</td>
<td>contains all the teleport triggers definition. This table is used to complete .dbc file information.</td>
</tr>
<tr class="odd">
<td>&quot;battleground_events&quot;:battleground_events</td>
<td>contains the description of battleground events.</td>
</tr>
<tr class="even">
<td>&quot;battleground_template&quot;:battleground_template</td>
<td>contains information about the different battlegrounds.</td>
</tr>
<tr class="odd">
<td>&quot;battlemaster_entry&quot;:battlemaster_entry</td>
<td>holds information on which NPC can start what battleground or arena.</td>
</tr>
<tr class="even">
<td><a href="command">command</a><br />
(Reloadable) (Core)</td>
<td>holds help and security information for commands.</td>
</tr>
<tr class="odd">
<td>&quot;conditions&quot;:conditions</td>
<td>With this table and the new conditions it is possible to create tree like and very complicated combined conditions.</td>
</tr>
<tr class="even">
<td>&quot;creature&quot;:creature</td>
<td>contains individual creature spawn data. Spawn of a creature is an instance of the creature object in the world.</td>
</tr>
<tr class="odd">
<td>&quot;creature_addon&quot;:creature_template_addon</td>
<td>defines different things that are applied on creature with a certain GUID when it is loaded.</td>
</tr>
<tr class="even">
<td><a href="creature_ai_scripts">creature_ai_scripts</a><br />
(Reloadable)</td>
<td>ACID (Artificial Creature Intelligence Database) EventAI</td>
</tr>
<tr class="odd">
<td><a href="creature_ai_summons">creature_ai_summons</a><br />
(Reloadable)</td>
<td>is used to provide NPC support for an event using action 32 = ACTION_T_SUMMON as one of its Actions.</td>
</tr>
<tr class="even">
<td><a href="creature_ai_texts">creature_ai_texts</a><br />
(Reloadable)</td>
<td>holds all the texts used within the EventAI (ACID) scripts.</td>
</tr>
<tr class="odd">
<td>&quot;creature_battleground&quot;:creature_battleground</td>
<td>contains the description of creatures spawned on battlegrounds.</td>
</tr>
<tr class="even">
<td>&quot;creature_equip_template&quot;:creature_equip_template</td>
<td>contains all equipment mobs can wear.</td>
</tr>
<tr class="odd">
<td><a href="creature_involvedrelation">creature_involvedrelation</a><br />
(Reloadable)</td>
<td>holds NPC quest ender relations on which NPCs finishes which quests.</td>
</tr>
<tr class="even">
<td>&quot;creature_linking&quot;:creature_linking</td>
<td>Creature Linking for Aggro/Respawn/Movement/Event by GUID</td>
</tr>
<tr class="odd">
<td>&quot;creature_linking_template&quot;:creature_linking_template</td>
<td>Creature Linking for Aggro/Respawn/Movement/Event by ENTRY</td>
</tr>
<tr class="even">
<td><a href="creature_loot_template">creature_loot_template</a><br />
(Reloadable)</td>
<td>Creature Loot</td>
</tr>
<tr class="odd">
<td>&quot;creature_model_info&quot;:creature_model_info</td>
<td>contains all models of mobs, their gender and other information that are model related.</td>
</tr>
<tr class="even">
<td>&quot;creature_model_race&quot;:creature_model_race</td>
<td>contains data to override displayed models based on the race of the player.</td>
</tr>
<tr class="odd">
<td>&quot;creature_movement&quot;:creature_movement_template</td>
<td>holds all the information on each single GUID creature’s waypoints.</td>
</tr>
<tr class="even">
<td>&quot;creature_movement_template&quot;:creature_movement_template</td>
<td>holds all the information on each single ENTRY creature’s waypoints.</td>
</tr>
<tr class="odd">
<td>&quot;creature_onkill_reputation&quot;:creature_onkill_reputation</td>
<td>controls the reputation given by creatures when killed by other players.</td>
</tr>
<tr class="even">
<td><a href="creature_questrelation">creature_questrelation</a><br />
(Reloadable)</td>
<td>holds NPC quest giver relations on which NPCs start which quests.</td>
</tr>
<tr class="odd">
<td>&quot;creature_template&quot;:creature_template</td>
<td>contains the description of creatures.</td>
</tr>
<tr class="even">
<td>&quot;creature_template_addon&quot;:creature_template_addon</td>
<td>defines different things that are applied on creature with a certain ENTRY when it is loaded.</td>
</tr>
<tr class="odd">
<td>&quot;creature_template_classlevelstats&quot;:creature_template_classlevelstats</td>
<td>Unit Base Stats</td>
</tr>
<tr class="even">
<td>&quot;creature_template_spells&quot;:creature_template_spells</td>
<td>holds creature spell data</td>
</tr>
<tr class="odd">
<td>&quot;costum_texts&quot;:costum_texts</td>
<td>?</td>
</tr>
<tr class="even">
<td>&quot;dbscript_string&quot;:dbscript_string</td>
<td>holds texts for scripts.</td>
</tr>
<tr class="odd">
<td>&quot;db_version&quot;:db_version</td>
<td>contains the version of the DB in use.</td>
</tr>
<tr class="even">
<td>&quot;dbscript_random_templates&quot;:dbscript_random_templates</td>
<td>holds randomize texts and relay scripts</td>
</tr>
<tr class="odd">
<td><a href="DBScripts">dbscripts_on_creature_death</a><br />
(Reloadable)</td>
<td>holds scripts activated when a creature dies.</td>
</tr>
<tr class="even">
<td><a href="DBScripts">dbscripts_on_creature_movement</a><br />
(Reloadable)</td>
<td>holds scripts activated while a npc is moving.</td>
</tr>
<tr class="odd">
<td><a href="DBScripts">dbscripts_on_event</a><br />
(Reloadable)</td>
<td>holds scripts activated whenever an event is activated by spell, gameobject or taxi waypoints.</td>
</tr>
<tr class="even">
<td><a href="DBScripts">dbscripts_on_go_template_use</a><br />
(Reloadable)</td>
<td>holds possible scripts activated by gameobjects.</td>
</tr>
<tr class="odd">
<td><a href="DBScripts">dbscripts_on_go_use</a><br />
(Reloadable)</td>
<td>holds possible scripts activated by GAMEOBJECT_TYPE_DOOR and GAMEOBJECT_TYPE_BUTTON.</td>
</tr>
<tr class="even">
<td><a href="DBScripts">dbscripts_on_gossip</a><br />
(Reloadable)</td>
<td>holds scripts activated on gossip_menu_option or gossip_menu.</td>
</tr>
<tr class="odd">
<td><a href="DBScripts">dbscripts_on_quest_end</a><br />
(Reloadable)</td>
<td>holds scripts activated when a player finishes a quest.</td>
</tr>
<tr class="even">
<td><a href="DBScripts">dbscripts_on_quest_start</a><br />
(Reloadable)</td>
<td>holds scripts activated when a player accepts a quest.</td>
</tr>
<tr class="odd">
<td><a href="DBScripts">dbscripts_on_relay</a><br />
(Reloadable)</td>
<td>holds scripts that are relayed from AI or other dbscripts.</td>
</tr>
<tr class="even">
<td><a href="DBScripts">dbscripts_on_spell</a><br />
(Reloadable)</td>
<td>holds scripts that can be activated by spells</td>
</tr>
<tr class="odd">
<td><a href="disenchant_loot_template">disenchant_loot_template</a><br />
(Reloadable)</td>
<td>Item disenchant loot</td>
</tr>
<tr class="even">
<td>&quot;exploration_basexp&quot;:exploration_basexp</td>
<td>controls the XP gained by characters when they explore new zones.</td>
</tr>
<tr class="odd">
<td><a href="fishing_loot_template">fishing_loot_template</a><br />
(Reloadable)</td>
<td>Fishing loot</td>
</tr>
<tr class="even">
<td>&quot;game_event&quot;:game_event</td>
<td>contains definitions for all game events that are activated or deactivated automatically by the Game Event System in the core.</td>
</tr>
<tr class="odd">
<td>&quot;game_event_creature&quot;:game_event_creature</td>
<td>contains all creature instances that have to be spawned/unspawned during defined game events.</td>
</tr>
<tr class="even">
<td>&quot;game_event_creature_data&quot;:game_event_creature_data</td>
<td>contains all creature instances that need to change display id and/or equipment during defined game events.</td>
</tr>
<tr class="odd">
<td>&quot;game_event_gameobject&quot;:game_event_gameobject</td>
<td>contains all gameobjects instances that participate to any game event.</td>
</tr>
<tr class="even">
<td>&quot;game_event_mail&quot;:game_event_mail</td>
<td>?</td>
</tr>
<tr class="odd">
<td>&quot;game_event_quest&quot;:game_event_quest</td>
<td>holds quests, which are only active during certain events.</td>
</tr>
<tr class="even">
<td><a href="game_graveyard_zone">game_graveyard_zone</a><br />
(Reloadable)</td>
<td>Contains informations about zones connected to world’s graveyards.</td>
</tr>
<tr class="odd">
<td>&quot;game_tele&quot;:game_tele</td>
<td>contains a list of teleport locations that can be used with the .tele command in-game.</td>
</tr>
<tr class="even">
<td>&quot;game_weather&quot;:game_weather</td>
<td>holds the percentages for weather changes in various zones.</td>
</tr>
<tr class="odd">
<td>&quot;gameobject&quot;:gameobject</td>
<td>holds the individual object data on each spawned game object in the world.</td>
</tr>
<tr class="even">
<td><a href="gameobject_addon">gameobject_addon</a> (WotLK)</td>
<td>path rotation</td>
</tr>
<tr class="odd">
<td>&quot;gameobject_battleground&quot;:gameobject_battleground</td>
<td>contains the events of gameobjects which are spawned on battlegrounds.</td>
</tr>
<tr class="even">
<td><a href="gameobject_involvedrelation">gameobject_involvedrelation</a> (Reloadable)</td>
<td>holds game object quest taker relations.</td>
</tr>
<tr class="odd">
<td><a href="gameobject_loot_template">gameobject_loot_template</a> (Reloadable)</td>
<td>Gameobject loot</td>
</tr>
<tr class="even">
<td><a href="gameobject_questrelation">gameobject_questrelation</a> (Reloadable)</td>
<td>holds game object quest giver relations.</td>
</tr>
<tr class="odd">
<td>&quot;gameobject_template&quot;:gameobject_template</td>
<td>contains template off all world’s objects.</td>
</tr>
<tr class="even">
<td><a href="gossip_menu">gossip_menu</a><br />
(Reloadable)</td>
<td>contains displayed gossip when a player talks to an NPC.</td>
</tr>
<tr class="odd">
<td><a href="gossip_menu_option">gossip_menu_option</a><br />
(Reloadable)</td>
<td>holds infos about menu options a gossip NPC can have.</td>
</tr>
<tr class="even">
<td>&quot;gossip_texts&quot;:gossip_texts</td>
<td>holds gossip texts used in ScriptDevAI.</td>
</tr>
<tr class="odd">
<td>&quot;instance_dungeon_encounters&quot;:instance_dungeon_encounters</td>
<td>?</td>
</tr>
<tr class="even">
<td>&quot;instance_encounters&quot;:instance_encounters</td>
<td>?</td>
</tr>
<tr class="odd">
<td>&quot;instance_template&quot;:instance_template</td>
<td>contains all the templates for every instance.</td>
</tr>
<tr class="even">
<td>&quot;item_convert&quot;:item_convert</td>
<td>?</td>
</tr>
<tr class="odd">
<td>&quot;item_enchantment_template&quot;:item_enchantment_template</td>
<td>holds enchantment chance information for items that should have either a random property or a random suffix attached to them.</td>
</tr>
<tr class="even">
<td><a href="item_expire_convert">item_expire_convert</a><br />
(Reloadable) (Core)</td>
<td>contains pairs of times which turn into an other item after a certain amount of time.</td>
</tr>
<tr class="odd">
<td><a href="item_loot_template">item_loot_template</a><br />
(Reloadable)</td>
<td>Item loot</td>
</tr>
<tr class="even">
<td><a href="item_required_target">item_required_target</a><br />
(Reloadable)</td>
<td>These spell effects require a specific target in either alive or dead state (for creatures).</td>
</tr>
<tr class="odd">
<td>&quot;item_template&quot;:item_template</td>
<td>holds information on every item that exists in the game.</td>
</tr>
<tr class="even">
<td>&quot;locales_creature&quot;:locales_creature</td>
<td>is used to provide to localized clients with localized string for creatures.</td>
</tr>
<tr class="odd">
<td>&quot;locales_gameobject&quot;:locales_gameobject</td>
<td>is used to provide to localized clients with localized string for gameobjects.</td>
</tr>
<tr class="even">
<td>&quot;locales_gossip_menu_option&quot;:locales_gossip_menu_option</td>
<td>?</td>
</tr>
<tr class="odd">
<td>&quot;locales_item&quot;:locales_item</td>
<td>is used to provide to localized clients with localized string for items.</td>
</tr>
<tr class="even">
<td>&quot;locales_npc_text&quot;:locales_npc_text</td>
<td>is used to provide localized clients with localized string for npc_texts.</td>
</tr>
<tr class="odd">
<td>&quot;locales_page_text&quot;:locales_page_text</td>
<td>is used to provide localized clients with localized string for page_texts.</td>
</tr>
<tr class="even">
<td>&quot;locales_points_of_interest&quot;:locales_points_of_interest</td>
<td>?</td>
</tr>
<tr class="odd">
<td>&quot;locales_quest&quot;:locales_quest</td>
<td>is used to provide to localized clients with localized string for quest templates.</td>
</tr>
<tr class="even">
<td><a href="mail_level_reward">mail_level_reward</a><br />
(Reloadable)</td>
<td>holds information on sent mails when a character levels up. Can be specified by raceMask.</td>
</tr>
<tr class="odd">
<td><a href="mail_loot_template">mail_loot_template</a><br />
(Reloadable)</td>
<td>?</td>
</tr>
<tr class="even">
<td>&quot;mangos_string&quot;:mangos_string</td>
<td>holds all of the strings used internally by the server.</td>
</tr>
<tr class="odd">
<td>&quot;milling_loot_template&quot;:milling_loot_template</td>
<td>Milling loot</td>
</tr>
<tr class="even">
<td>&quot;npc_gossip&quot;:npc_gossip</td>
<td>THIS TABLE IS OUTDATED. DO NOT USE</td>
</tr>
<tr class="odd">
<td><a href="npc_spellclick_spells">npc_spellclick_spells</a><br />
(Reloadable)</td>
<td>holds information about spells to be casted upon receiving CMSG_SPELLCLICK.</td>
</tr>
<tr class="even">
<td>&quot;npc_text&quot;:npc_text</td>
<td>contains the texts that are used for gossip.</td>
</tr>
<tr class="odd">
<td>&quot;npc_trainer&quot;:npc_trainer_template</td>
<td>holds the spell data for all trainers by ENTRY.</td>
</tr>
<tr class="even">
<td>&quot;npc_trainer_template&quot;:npc_trainer_template</td>
<td>holds the spell data for all trainers by TrainerTemplateId.</td>
</tr>
<tr class="odd">
<td>&quot;npc_vendor&quot;:npc_vendor_template</td>
<td>holds the vendor data for all NPCs that sell items by ENTRY.</td>
</tr>
<tr class="even">
<td>&quot;npc_vendor_template&quot;:npc_vendor_template</td>
<td>holds the vendor data for all NPCs that sell items by VendorTemplateId.</td>
</tr>
<tr class="odd">
<td>&quot;page_text&quot;:page_text</td>
<td>holds the text for letter items.</td>
</tr>
<tr class="even">
<td>&quot;pet_familystats&quot;:pet_familystats</td>
<td>?</td>
</tr>
<tr class="odd">
<td>&quot;pet_levelstats&quot;:pet_levelstats</td>
<td>holds information on individual pet base stats based on level.</td>
</tr>
<tr class="even">
<td>&quot;pet_name_generation&quot;:pet_name_generation</td>
<td>holds pieces of names (first and last half) that are use for pet name generation.</td>
</tr>
<tr class="odd">
<td>&quot;petcreateinfo_spell&quot;:petcreateinfo_spell</td>
<td>controls what spells a tameable beast will have once tamed.</td>
</tr>
<tr class="even">
<td><a href="pickpocketing_loot_template">pickpocketing_loot_template</a><br />
(Reloadable)</td>
<td>Pickpocketing loot</td>
</tr>
<tr class="odd">
<td><a href="player_classlevelstats">player_classlevelstats</a><br />
(Core)</td>
<td>holds information on the base health and mana of characters when they level up. Each class has different level stats.</td>
</tr>
<tr class="even">
<td><a href="player_levelstats">player_levelstats</a><br />
(Core)</td>
<td>holds information on the base health and mana of characters when they level up. Each class has different level stats.</td>
</tr>
<tr class="odd">
<td><a href="player_xp_for_level">player_xp_for_level</a><br />
(Core)</td>
<td>includes information on how much experience needed for next level. Comes from sniffs.</td>
</tr>
<tr class="even">
<td><a href="playercreateinfo">playercreateinfo</a><br />
(Core)</td>
<td>holds the start positions of each class-race combinations for all newly created characters.</td>
</tr>
<tr class="odd">
<td><a href="playercreateinfo_action">playercreateinfo_action</a><br />
(Core)</td>
<td>holds information on what default actions a brand new character should start out with.</td>
</tr>
<tr class="even">
<td><a href="playercreateinfo_item">playercreateinfo_item</a><br />
(Core)</td>
<td>holds information on what items each race-class combination of a new character starts out with.</td>
</tr>
<tr class="odd">
<td><a href="playercreateinfo_spell">playercreateinfo_spell</a><br />
(Core)</td>
<td>holds information on what spells newly created characters should start out with.</td>
</tr>
<tr class="even">
<td><a href="points_of_interest">points_of_interest</a><br />
(Reloadable)</td>
<td>comes from sniffs.</td>
</tr>
<tr class="odd">
<td>&quot;pool_creature&quot;:pool_creature</td>
<td>contains all pooled creatures by GUID that are part of a pool_template.</td>
</tr>
<tr class="even">
<td>&quot;pool_creature_template&quot;:pool_creature_template</td>
<td>contains all pooled creatures by ENTRY that are part of a pool_template.</td>
</tr>
<tr class="odd">
<td>&quot;pool_gameobject&quot;:pool_gameobject</td>
<td>contains all pooled gameobjects by GUID that are part of a pool_template.</td>
</tr>
<tr class="even">
<td>&quot;pool_gameobject_template&quot;:pool_gameobject_template</td>
<td>contains all pooled gameobjects by ENTRY that are part of a pool_template.</td>
</tr>
<tr class="odd">
<td>&quot;pool_pool&quot;:pool_pool</td>
<td>contains pool of pools. You can create a pool with a chance of a range of pools in that pool being activated.</td>
</tr>
<tr class="even">
<td>&quot;pool_template&quot;:pool_template</td>
<td>contains all pool instances that participate to any game event.</td>
</tr>
<tr class="odd">
<td><a href="prospecting_loot_template">prospecting_loot_template</a><br />
(Reloadable)</td>
<td>Prospecting loot</td>
</tr>
<tr class="even">
<td><a href="quest_poi">quest_poi</a><br />
(Reloadable)</td>
<td>comes from sniffs.</td>
</tr>
<tr class="odd">
<td><a href="quest_poi_points">quest_poi_points</a><br />
(Reloadable)</td>
<td>comes from sniffs. Visually speaking, this table is used to identify the X and Y coordinates on the map (not the minimap – the main map) where a quest’s question mark should appear.</td>
</tr>
<tr class="even">
<td><a href="quest_template">quest_template</a><br />
(Reloadable)</td>
<td>contains all basic definitions of quests available.</td>
</tr>
<tr class="odd">
<td><a href="reference_loot_template">reference_loot_template</a><br />
(Reloadable)</td>
<td>reference loot (loot groups)</td>
</tr>
<tr class="even">
<td><a href="reputation_reward_rate">reputation_reward_rate</a><br />
(Reloadable)</td>
<td>holds reputation multipliers for specific factions.</td>
</tr>
<tr class="odd">
<td>&quot;reputation_spillover_template&quot;:reputation_spillover_template</td>
<td>holds information about the <a href="http://wowwiki.wikia.com/wiki/Exalted">Reputation Bleed Over</a> -Effect</td>
</tr>
<tr class="even">
<td><a href="reserved_name">reserved_name</a><br />
(Reloadable)</td>
<td>serves as a simple list of names that players (gmlevel == 0) cannot use when naming their characters.</td>
</tr>
<tr class="odd">
<td>&quot;script_texts&quot;:script_texts</td>
<td>holds all the texts used by core scripted creatures/entities (ScriptDev)</td>
</tr>
<tr class="even">
<td>&quot;script_waypoint&quot;:script_waypoint</td>
<td>?</td>
</tr>
<tr class="odd">
<td><a href="scripted_areatrigger">scripted_areatrigger</a><br />
(Core)</td>
<td>This table links areatriggers to C<em></em> scripts.</td>
</tr>
<tr class="even">
<td><a href="scripted_event_id">scripted_event_id</a><br />
(Core)</td>
<td>This table links event id’s to C<em></em> scripts.</td>
</tr>
<tr class="odd">
<td><a href="skill_discovery_template">skill_discovery_template</a><br />
(Reloadable)</td>
<td>controls the so called &quot;discovery&quot; system of learning spells.</td>
</tr>
<tr class="even">
<td>&quot;skill_extra_item_template&quot;:skill_extra_item_template</td>
<td>holds information about when using certain profession spells, you have the chance of creating more than one copy of the item.</td>
</tr>
<tr class="odd">
<td>&quot;skill_fishing_base_level&quot;:skill_fishing_base_level</td>
<td>controls the minimum skill level required in fishing to fish in a certain area.</td>
</tr>
<tr class="even">
<td>&quot;skinning_loot_template&quot;:skinning_loot_template</td>
<td>Skinning loot</td>
</tr>
<tr class="odd">
<td><a href="spell_affect">spell_affect</a><br />
(Reloadable) (Core)</td>
<td>holds information on what spells are affected by what spell mods.</td>
</tr>
<tr class="even">
<td><a href="spell_area">spell_area</a><br />
(Reloadable)</td>
<td>holds information on what spells are applied to npcs/players in some areas.</td>
</tr>
<tr class="odd">
<td><a href="spell_bonus_data">spell_bonus_data</a><br />
(Reloadable)</td>
<td>is used for storing custom damage/healing bonus coefficients.</td>
</tr>
<tr class="even">
<td><a href="spell_chain">spell_chain</a><br />
(Reloadable)</td>
<td>defines spell chains. A spell chain is a series of spells which all share the same name and all do the same thing.</td>
</tr>
<tr class="odd">
<td>&quot;spell_check&quot;:spell_check</td>
<td>?</td>
</tr>
<tr class="even">
<td>&quot;spell_cone&quot;:spell_cone</td>
<td>holds Degrees for Cone spells</td>
</tr>
<tr class="odd">
<td><a href="spell_elixir">spell_elixir</a><br />
(Reloadable)</td>
<td>holds elixir information to be used to properly stack the elixirs.</td>
</tr>
<tr class="even">
<td>&quot;spell_facing&quot;:spell_facing</td>
<td>?</td>
</tr>
<tr class="odd">
<td><a href="spell_learn_spell">spell_learn_spell</a><br />
(Reloadable)</td>
<td>holds information on spells that should be learned at the same time a player learns another spell.</td>
</tr>
<tr class="even">
<td><a href="spell_loot_template">spell_loot_template</a><br />
(Reloadable)</td>
<td>Spell loot</td>
</tr>
<tr class="odd">
<td>&quot;spell_pet_auras&quot;:spell_pet_auras</td>
<td>?</td>
</tr>
<tr class="even">
<td><a href="spell_proc_event">spell_proc_event</a><br />
(Reloadable)</td>
<td>holds information on how certain spells activate, which proc other spells.</td>
</tr>
<tr class="odd">
<td><a href="spell_proc_item_enchant">spell_proc_item_enchant</a><br />
(Reloadable)</td>
<td>holds information (ppmRate) for item (weapon) enchants</td>
</tr>
<tr class="even">
<td><a href="spell_script_target">spell_script_target</a> (Reloadable)</td>
<td>holds information on spell effects which require a specific target in either alive or dead state (for creatures).</td>
</tr>
<tr class="odd">
<td><a href="spell_target_position">spell_target_position</a><br />
(Reloadable)</td>
<td>holds coordinate information on where the player should be teleported to when a spell with effect SPELL_EFFECT_TELEPORT_UNITS.</td>
</tr>
<tr class="even">
<td><a href="spell_template">spell_template</a> (Core)</td>
<td>contains the description of spells.</td>
</tr>
<tr class="odd">
<td><a href="spell_threat">spell_threat</a><br />
(Reloadable)</td>
<td>holds threat values on all spells that should either give or take away threat.</td>
</tr>
<tr class="even">
<td><a href="taxi_shortcuts">taxi_shortcuts</a><br />
(Reloadable)</td>
<td>holds information about shortcuts for each individual taxi flight.</td>
</tr>
<tr class="odd">
<td>&quot;transports&quot;:transports</td>
<td>contains all type 15 transports (Boats and Zeppelins).</td>
</tr>
<tr class="even">
<td>&quot;vehicle_accessory&quot;:vehicle_accessory</td>
<td>?</td>
</tr>
<tr class="odd">
<td>&quot;world_template&quot;:world_template</td>
<td>holds the ScriptNames of the world maps 0, 1, 530, 571</td>
</tr>
</tbody>
</table>


