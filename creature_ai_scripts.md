Back to [world database](mangosdb_struct) list of tables.

### EventAI Tables

[creature\_ai\_scripts](creature_ai_scripts) for EventAI (ACID) scripted NPCs
[creature\_ai\_summons](creature_ai_summons) for [Summon IDs](creature_ai_summons#id) used in ACTION\_T\_SUMMON\_ID (32)
[creature\_ai\_texts](creature_ai_texts) for Texts used by ACTION\_T\_TEXT (1) and ACTION\_T\_TEXT\_NEW (54)

EventAI Documentation
---------------------

The Manual-like and most-recent documentation for EventAI can be found in [doc/EventAI.txt](https://github.com/cmangos/mangos-wotlk/blob/master/doc/EventAI.txt)

EventAI Guide
-------------

ScriptDev2 was integrated into cmangos on 04 sept 2015 and enables us to handle DB-based scripting that allows the use of a database (MySQL only right now) to specify the actions that a creature script will do.

The script is called EventAI and will be referenced like this for the rest of this guide. A basic EventAI script works with and requires only two pieces of information: <u>When it happens</u> and <u>What happens when</u>.

The first piece of information (the <u>When it happens</u>) will be referred to as the <u>event</u>.

The second piece of information (the <u>What happens when</u>) will be referred to as the <u>action</u>.
Currently, a single EventAI script entry can have up to three actions.

Anyone that wants to create entries for the EventAI script needs to answer the two questions above.

Some events will only occur once while others can be timed so that they occur at a specified interval.

### Structure

<table style="width:100%;">
<colgroup>
<col width="25%" />
<col width="3%" />
<col width="3%" />
<col width="3%" />
<col width="4%" />
<col width="59%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Field</strong></th>
<th><strong>Type</strong></th>
<th><strong>Null</strong></th>
<th><strong>Key</strong></th>
<th><strong>Default</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="creature_ai_scripts#id">id</a></td>
<td></td>
<td>NO</td>
<td>PRI</td>
<td>None</td>
<td>Primary Key</td>
</tr>
<tr class="even">
<td><a href="creature_ai_scripts#id">creature_id</a></td>
<td></td>
<td>NO</td>
<td></td>
<td></td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
</tr>
<tr class="odd">
<td><a href="creature_ai_scripts#event_type">event_type</a></td>
<td></td>
<td>NO</td>
<td></td>
<td></td>
<td>Event</td>
</tr>
<tr class="even">
<td><a href="creature_ai_scripts#event_inverse_phase_mask">event_inverse_phase_mask</a></td>
<td></td>
<td>NO</td>
<td></td>
<td></td>
<td>PhaseMask</td>
</tr>
<tr class="odd">
<td><a href="creature_ai_scripts#event_chance">event_chance</a></td>
<td></td>
<td>NO</td>
<td></td>
<td></td>
<td>Chance. Using a value of 0 in this field will make the event never occur. Values are from 0 to 100.</td>
</tr>
<tr class="even">
<td><a href="creature_ai_scripts#eventflags">event_flags</a></td>
<td></td>
<td>NO</td>
<td></td>
<td></td>
<td>Every event also has a `chance` field that controls the chance of that event actually occurring. Using a value of 0 in this field will make the event never occur. Values are from 0 to 100.</td>
</tr>
<tr class="odd">
<td><a href="creature_ai_scripts#event_param">event_param</a></td>
<td></td>
<td>NO</td>
<td></td>
<td></td>
<td>event_param1-3 for Event</td>
</tr>
<tr class="even">
<td><a href="creature_ai_scripts#action_type">action_type</a></td>
<td></td>
<td>NO</td>
<td></td>
<td></td>
<td>action_type1-3 for Event</td>
</tr>
<tr class="odd">
<td><a href="creature_ai_scripts#action_param">action_param</a></td>
<td></td>
<td>NO</td>
<td></td>
<td></td>
<td>action_param1-3 for action_type1-3</td>
</tr>
<tr class="even">
<td><a href="creature_ai_scripts#comment">comment</a></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>comment describing the actions performed on event</td>
</tr>
</tbody>
</table>

Example:

let's say that a certain creature using EventAI will have a max of four phases. We are then dealing with a 4 bit number in this field. Let's further say that that certain creature has an event that will only trigger in its phase 2 (a timed spell cast for instance). Then the field should contain all of the phases the event SHOULDN'T be triggered in...then out of the four bits, we leave the **third** bit alone (off) and turn on all of the other bits so we get 1011 which is equal to 11, so we put in 11 as the inverse phase mask for the event entry. As another example, let's say that the same creature previously mentioned has another event that is only triggered in the phase 0 and phase 3. This would mean that we need to ignore phase 1 and 2, so our bitmask would be 0110 which is equal to 6 so we put in 6 for this event's inverse phase mask field. Please note that both examples were tailored for a creature with four and only four phases. If you decide to add more phases later on, you will have to redefine all of the nonzero bitmasks for all of the mob's events.

EventAI can also support phases. A <u>phase</u> is just a way to group certain events + actions together so that the creature will perform certain actions based on what event it is currently on. The way the phase system works in EventAI is that for every event added, it needs to be specified under which phases the event <u>SHOULD NOT</u> occur. This is a bit confusing at first, so let's look at it more closely. A creature can have more than one phase, up to a max of 32 different phases (with the first one being phase 0, and last one being phase 31). How the phase selection field works is that it contains a 32bit number. Each bit in the number represents a possible phase, with the bit in the least significant position signifying phase 0 and the most significant bit signifying phase 31. The default value of zero in this field has no bits set and since the field controls when the event should NOT trigger, it would then mean that the event will always be triggered independent of the current phase the creature is in. Therefore, if you want to specify what phases the event should occur in, you need to add up all of the corresponding bits for all the other phases where the event shouldn't trigger in (confusing...yes).

All of the [events](creature_ai_scripts#event_type), [EventFlags](creature_ai_scripts#EventFlags), [actions](creature_ai_scripts#action_type) and possible [targets](creature_ai_scripts#Target) are summarized and described below.

-   NU = Not Used\*
-   IC = In Combat Only\*
-   OOC = Out Of Combat Only\*
-   US = Unsupported

#### event\_type

<table>
<colgroup>
<col width="1%" />
<col width="9%" />
<col width="12%" />
<col width="12%" />
<col width="3%" />
<col width="3%" />
<col width="57%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Name</th>
<th>Param1</th>
<th>Param2</th>
<th>Param3</th>
<th>Param4</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>EVENT_T_TIMER_IN_COMBAT</td>
<td>InitialMin</td>
<td>InitialMax</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>IC - Expires first between (Param1) and (Param2). Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>1</td>
<td>EVENT_T_TIMER_OOC</td>
<td>InitialMin</td>
<td>InitialMax</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>OOC - Expires first between (Param1) and (Param2). Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="odd">
<td>2</td>
<td>EVENT_T_HP</td>
<td>HPMax%</td>
<td>HPMin%</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>IC - Expires when HP% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>3</td>
<td>EVENT_T_MANA</td>
<td>ManaMax%</td>
<td>ManaMin%</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>IC - Expires when Mana% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="odd">
<td>4</td>
<td>EVENT_T_AGGRO</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Expires on Aggro</td>
</tr>
<tr class="even">
<td>5</td>
<td>EVENT_T_KILL</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>NU</td>
<td>NU</td>
<td>Expires on Player Kill. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="odd">
<td>6</td>
<td>EVENT_T_DEATH</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Expires on Death</td>
</tr>
<tr class="even">
<td>7</td>
<td>EVENT_T_EVADE</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Expires on Evade</td>
</tr>
<tr class="odd">
<td>8</td>
<td>EVENT_T_SPELLHIT</td>
<td><a href="spell_template#Id">spellId</a></td>
<td><a href="creature_ai_scripts#schoolMask">schoolMask</a></td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires on (Param1) <a href="spell_template#Id">spellId</a> or on (Param2) <a href="creature_ai_scripts#schoolMask">schoolMask</a> spellhit. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>9</td>
<td>EVENT_T_RANGE</td>
<td>MinDist</td>
<td>MaxDist</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when current target distance is greater than (Param1) and less than (Param2). Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="odd">
<td>10</td>
<td>EVENT_T_OOC_LOS</td>
<td>noHostile</td>
<td>MaxRange</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>OOC - Expires when a unit (friendly only if Param1 = 1) moves within (Param2) distance to creature. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>11</td>
<td>EVENT_T_SPAWNED</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Expires on Spawn</td>
</tr>
<tr class="odd">
<td>12</td>
<td>EVENT_T_TARGET_HP</td>
<td>HPMax%</td>
<td>HPMin%</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when current target HP% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>13</td>
<td>EVENT_T_TARGET_CASTING</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>NU</td>
<td>NU</td>
<td>Expires when current target is casting a spell. Will repeat every (Param1) and (Param2)</td>
</tr>
<tr class="odd">
<td>14</td>
<td>EVENT_T_FRIENDLY_HP</td>
<td>HPDeficit</td>
<td>Radius</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when a friendly unit (Target = 12) has at least (param1) HP missing in (param2) radius. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>15</td>
<td>EVENT_T_FRIENDLY_IS_CC</td>
<td>DispelType (US)</td>
<td>Radius</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when a friendly unit (Target = 12) is crowd controlled in (param2) radius. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="odd">
<td>16</td>
<td>EVENT_T_FRIENDLY_MISSING_BUFF</td>
<td><a href="spell_template#Id">spellId</a></td>
<td>Radius</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when a friendly unit (Target = 12) is missing aura given by (param1) <a href="spell_template#Id">spellId</a> in (param2) radius. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>17</td>
<td>EVENT_T_SUMMONED_UNIT</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>NU</td>
<td>Expires when creature with (Param1) <a href="creature_template#entry">CreatureEntry</a> spawned or for all spawns if (Param1 = 0). Will repeat every (Param2) and (Param3)</td>
</tr>
<tr class="odd">
<td>18</td>
<td>EVENT_T_TARGET_MANA</td>
<td>ManaMax%</td>
<td>ManaMin%</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when current target MP% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>21</td>
<td>EVENT_T_REACHED_HOME</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Expires on Reached Home (after Evade)</td>
</tr>
<tr class="odd">
<td>22</td>
<td>EVENT_T_RECEIVE_EMOTE</td>
<td>TextEmote</td>
<td><a href="conditions#condition_entry">ConditionId</a></td>
<td>NU</td>
<td>NU</td>
<td>Expires when creature receives <a href="https://github.com/cmangos/mangos-cata/blob/b76261946597de1200effc4236409a3978414056/src/game/Globals/SharedDefines.h#L1643">TextEmotes</a> from player paired with a potential condition (Param 2)</td>
</tr>
<tr class="even">
<td>23</td>
<td>EVENT_T_AURA</td>
<td><a href="spell_template#Id">spellId</a></td>
<td>AmmountInStack</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when creature has spell (Param1) aura stacks applied greater or equal to (Param2) amount. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="odd">
<td>24</td>
<td>EVENT_T_TARGET_AURA</td>
<td><a href="spell_template#Id">spellId</a></td>
<td>AmmountInStack</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when current target have spell (Param1) aura stacks applied greater or equal to (Param2) amount. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>25</td>
<td>EVENT_T_SUMMONED_JUST_DIED</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>NU</td>
<td>Expires after creature with (Param1) <a href="creature_template#entry">CreatureEntry</a> died or for all spawns if (Param1 = 0). Will repeat every (Param2) and (Param3)</td>
</tr>
<tr class="odd">
<td>26</td>
<td>EVENT_T_SUMMONED_JUST_DESPAWN</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>NU</td>
<td>Expires before creature with (Param1) <a href="creature_template#entry">CreatureEntry</a> despawned or for all spawns if (Param1 = 0). Will repeat every (Param2) and (Param3)</td>
</tr>
<tr class="even">
<td>27</td>
<td>EVENT_T_MISSING_AURA</td>
<td><a href="spell_template#Id">spellId</a></td>
<td>AmmountInStack</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when creature have spell (Param1) aura stacks applied less than (Param2) amount. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="odd">
<td>28</td>
<td>EVENT_T_TARGET_MISSING_AURA</td>
<td><a href="spell_template#Id">spellId</a></td>
<td>AmmountInStack</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when current target have spell (Param1) aura stacks applied less than (Param2) amount. Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="even">
<td>29</td>
<td>EVENT_T_TIMER_GENERIC</td>
<td>InitialMin</td>
<td>InitialMax</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires first between (Param1) and (Param2). Will repeat every (Param3) and (Param4)</td>
</tr>
<tr class="odd">
<td>30</td>
<td>EVENT_T_RECEIVE_AI_EVENT</td>
<td><a href="creature_ai_scripts#AIEventType">AIEventType</a></td>
<td>Sender-Entry</td>
<td>NU</td>
<td>NU</td>
<td>Expires when the creature receives an (Param1) <a href="creature_ai_scripts#AIEventType">AIEventType</a>, sent by (Param2 != 0) <a href="creature_template#entry">Sender-Entry</a>. If (Param2 = 0) then sent by any creature</td>
</tr>
<tr class="even">
<td>31</td>
<td>EVENT_T_ENERGY</td>
<td>EnergyMax%</td>
<td>EnergyMin%</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when Energy% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4) if Condition: between (Param1) and (Param2) are still met</td>
</tr>
<tr class="odd">
<td>32</td>
<td>EVENT_T_SELECT_ATTACKING_TARGET</td>
<td>MinRange</td>
<td>MaxRange</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when threat table has target with distance between (Param1) and (Param2). Will repeat every (Param3) and (Param4) if Condition: between (Param1) and (Param2) are still met</td>
</tr>
<tr class="even">
<td>33</td>
<td>EVENT_T_FACING_TARGET</td>
<td>Back(0)OrFront(1)</td>
<td>NU</td>
<td>RepeatMin</td>
<td>RepeatMax</td>
<td>Expires when creature is (behind = 0 / infront = 1 of target. Will repeat every (Param3) and (Param4) if Condition: (Param1) is still met</td>
</tr>
</tbody>
</table>

Now that all of the supported events have been listed and described, we shall now move on to the actions that can be performed.

Each event can take up to three actions. The actions will all be performed when the event is triggered and they will be performed in the order that they have been defined. This means that, for a certain event, action 1 will be performed first, followed by action 2, then lastly by action 3.

Just like event definitions, each action can use up to three different parameters but not all actions will use all three parameters. If a parameter isn't mentioned for an action, then that action does not need that parameter.

#### action\_type

<table>
<colgroup>
<col width="0%" />
<col width="6%" />
<col width="11%" />
<col width="11%" />
<col width="7%" />
<col width="61%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Name</th>
<th>Param 1</th>
<th>Param 2</th>
<th>Param 3</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>ACTION_T_NONE</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Does nothing!</td>
</tr>
<tr class="even">
<td>1</td>
<td>ACTION_T_TEXT</td>
<td>-TextId1</td>
<td>-TextId2</td>
<td>-TextId3</td>
<td>deprecated, [use action 54 for 1 / 4+ <a href="creature_ai_texts%5D">texts</a> and <a href="creature_ai_texts">texts</a> that require text targeting for correct text output: Displays the -TextId(s)(randomized) as defined in <a href="creature_ai_texts" class="uri">creature_ai_texts</a>. Optionally <a href="custom_texts" class="uri">custom_texts</a>. All values are required to be negative. Optionally <a href="custom_texts" class="uri">custom_texts</a> can be used</td>
</tr>
<tr class="odd">
<td>2</td>
<td>ACTION_T_SET_FACTION</td>
<td>factionId</td>
<td><a href="creature_ai_scripts#TemporaryFactionFlags">TemporaryFactionFlags</a></td>
<td>NU</td>
<td>Changes faction for a creature. When (Param1) is zero, creature will revert to it's default faction. Flags will determine when faction is restored to default (evade, respawn etc)</td>
</tr>
<tr class="even">
<td>3</td>
<td>ACTION_T_MORPH_TO_ENTRY_OR_MODEL</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td><a href="creature_template#modelId1">modelId</a></td>
<td>NU</td>
<td><a href="creature_template#entry(param1)">CreatureEntry</a> OR <a href="creature_template#modelId1">modelId</a> (param2) (or 0 for both to demorph)</td>
</tr>
<tr class="odd">
<td>4</td>
<td>ACTION_T_SOUND</td>
<td>SoundId</td>
<td>NU</td>
<td>NU</td>
<td>Creature plays Sound. IDs are contained in the DBC files</td>
</tr>
<tr class="even">
<td>5</td>
<td>ACTION_T_EMOTE</td>
<td><a href="creature_template_addon#emote">emoteId</a></td>
<td>NU</td>
<td>NU</td>
<td>Creature does visual emote. IDs are contained in the DBC files</td>
</tr>
<tr class="odd">
<td>6</td>
<td>ACTION_T_RANDOM_SAY</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>deprecated</td>
</tr>
<tr class="even">
<td>7</td>
<td>ACTION_T_RANDOM_YELL</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>deprecated</td>
</tr>
<tr class="odd">
<td>8</td>
<td>ACTION_T_RANDOM_TEXTEMOTE</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>deprecated</td>
</tr>
<tr class="even">
<td>9</td>
<td>ACTION_T_RANDOM_SOUND</td>
<td>Sound ID 1</td>
<td>Sound ID 2</td>
<td>Sound ID 3</td>
<td>Picks a sound ID at random and plays it; -1 = action skipped if chosen</td>
</tr>
<tr class="odd">
<td>10</td>
<td>ACTION_T_RANDOM_EMOTE</td>
<td>Emote ID 1</td>
<td>Emote ID 2</td>
<td>Emote ID 3</td>
<td>Picks an emote ID at random and does visual emote; -1 = action skipped if chosen</td>
</tr>
<tr class="even">
<td>11</td>
<td>ACTION_T_CAST</td>
<td><a href="spell_template#Id">spellId</a></td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td><a href="creature_ai_scripts#castFlags">castFlags</a></td>
<td>Creature cast spell on a target with specified <a href="creature_ai_scripts#castFlags">castFlags</a></td>
</tr>
<tr class="odd">
<td>12</td>
<td>ACTION_T_SPAWN</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>Duration in milliseconds</td>
<td>Creature spawns a creature with (Param1) <a href="creature_template#entry">CreatureEntry</a> at Target for a given duration (infinite if zero)</td>
</tr>
<tr class="even">
<td>13</td>
<td>ACTION_T_THREAT_SINGLE_PCT</td>
<td>Threat %</td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>NU</td>
<td>Modifies <a href="creature_ai_scripts#Target">target</a> threat by a percent (-100 to +100)</td>
</tr>
<tr class="odd">
<td>14</td>
<td>ACTION_T_THREAT_ALL_PCT</td>
<td>Threat %</td>
<td>NU</td>
<td>NU</td>
<td>Modifies everyone's threat by a percent (-100 to +100), will not cause Evade</td>
</tr>
<tr class="even">
<td>15</td>
<td>ACTION_T_QUEST_EVENT</td>
<td>Quest ID</td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>NU</td>
<td>Satisfies external script objective for a quest for the target (MUST be a player)</td>
</tr>
<tr class="odd">
<td>16</td>
<td>ACTION_T_CAST_EVENT</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td><a href="spell_template#Id">spellId</a></td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>Emulates spell cast on the creature for the target (must be a player) [hacky]</td>
</tr>
<tr class="even">
<td>17</td>
<td>ACTION_T_SET_UNIT_FIELD</td>
<td><a href="creature_ai_scripts#EUnitFields">EUnitFields</a></td>
<td>Value</td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>Sets unit field at the index to the value given for the target. More information on the field value indeces can be found at <a href="character">character data</a> data</td>
</tr>
<tr class="odd">
<td>18</td>
<td>ACTION_T_SET_UNIT_FLAG</td>
<td><a href="creature_template#unitflags">UnitFlags</a></td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>NU</td>
<td>Sets flag(s) on the target</td>
</tr>
<tr class="even">
<td>19</td>
<td>ACTION_T_REMOVE_UNIT_FLAG</td>
<td><a href="creature_template#unitflags">UnitFlags</a></td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>NU</td>
<td>Removes flag(s) from the target</td>
</tr>
<tr class="odd">
<td>20</td>
<td>ACTION_T_AUTO_ATTACK</td>
<td>Boolean</td>
<td>NU</td>
<td>NU</td>
<td>If 0 cant melee, else (1) continues/starts it</td>
</tr>
<tr class="even">
<td>21</td>
<td>ACTION_T_COMBAT_MOVEMENT</td>
<td>Boolean</td>
<td>NU</td>
<td>NU</td>
<td>If 0 stops movement, else (1) continues/starts it</td>
</tr>
<tr class="odd">
<td>22</td>
<td>ACTION_T_SET_PHASE</td>
<td>Phase #</td>
<td>NU</td>
<td>NU</td>
<td>Sets current phase to number given. This number must be an integer between 0 and 31 inclusive</td>
</tr>
<tr class="even">
<td>23</td>
<td>ACTION_T_INC_PHASE</td>
<td>Number</td>
<td>NU</td>
<td>NU</td>
<td>deprecated, increments (or decrements) the phase by given number</td>
</tr>
<tr class="odd">
<td>24</td>
<td>ACTION_T_EVADE</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Force creature reset. Exit combat + lose threat, true Evade</td>
</tr>
<tr class="even">
<td>25</td>
<td>ACTION_T_FLEE_FOR_ASSIST</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Force creature to flee from combat</td>
</tr>
<tr class="odd">
<td>26</td>
<td>ACTION_T_QUEST_EVENT_ALL</td>
<td>Quest ID</td>
<td>NU</td>
<td>NU</td>
<td>Satisfies external objective for a quest for all players in threat list similar to ACTION_T_QUEST_EVENT</td>
</tr>
<tr class="even">
<td>27</td>
<td>ACTION_T_CAST_EVENT_ALL</td>
<td>Quest ID</td>
<td><a href="spell_template#Id">spellId</a></td>
<td>NU</td>
<td>Emulates spell cast on creature for all players in threat list similar to ACTION_T_CAST_EVENT</td>
</tr>
<tr class="odd">
<td>28</td>
<td>ACTION_T_REMOVEAURASFROMSPELL</td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td><a href="spell_template#Id">spellId</a></td>
<td>NU</td>
<td>Removes all auras from a <a href="spell_template#Id">spellId</a> from the target</td>
</tr>
<tr class="even">
<td>29</td>
<td>ACTION_T_RANGED_MOVEMENT</td>
<td>Distance</td>
<td>Angle</td>
<td>NU</td>
<td>creature sets ranged movement generator keeping the creature at a distance. Note that specifying zero angle and distance will make it just melee instead</td>
</tr>
<tr class="odd">
<td>30</td>
<td>ACTION_T_RANDOM_PHASE</td>
<td>Phase 1</td>
<td>Phase 2</td>
<td>Phase 3</td>
<td>Randomly chooses a phase from the list of three phases</td>
</tr>
<tr class="even">
<td>31</td>
<td>ACTION_T_RANDOM_PHASE_RANGE</td>
<td>Min Phase</td>
<td>Max Phase + 1</td>
<td>NU</td>
<td>Chooses a random phase in the range specified. This number must be an integer between 0 and 31 inclusive</td>
</tr>
<tr class="odd">
<td>32</td>
<td>ACTION_T_SUMMON_ID</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>Summon ID</td>
<td>Summons a creature using the data specified in the separate <a href="creature_ai_summons" class="uri">creature_ai_summons</a> table</td>
</tr>
<tr class="even">
<td>33</td>
<td>ACTION_T_KILLED_MONSTER</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>NU</td>
<td>Simulates a kill for a <a href="creature_template#entry">CreatureEntry</a> given for the player from the <a href="creature_ai_scripts#Target">target</a></td>
</tr>
<tr class="odd">
<td>34</td>
<td>ACTION_T_SET_INST_DATA</td>
<td>Field</td>
<td>32 bit Value</td>
<td>NU</td>
<td>Sets data for the instance. Note that this will only work when the creature is inside an instantiable zone that has a valid script (ScriptedInstance) assigned.</td>
</tr>
<tr class="even">
<td>35</td>
<td>ACTION_T_SET_INST_DATA64</td>
<td>Field</td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>NU</td>
<td>Stores target's GUID at the field given in the instance script</td>
</tr>
<tr class="odd">
<td>36</td>
<td>ACTION_T_UPDATE_TEMPLATE</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td>Faction</td>
<td>NU</td>
<td>This function temporarily changes creature entry to new entry, display is changed, loot is changed, but AI is not changed. At respawn creature will be reverted to original entry. Alliance(0) or Horde (1)</td>
</tr>
<tr class="even">
<td>37</td>
<td>ACTION_T_DIE</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Kills the creature</td>
</tr>
<tr class="odd">
<td>38</td>
<td>ACTION_T_ZONE_COMBAT_PULSE</td>
<td>NU</td>
<td>NU</td>
<td>NU</td>
<td>Places all players within the instance into combat with the creature. Only works in combat and only works inside of instances</td>
</tr>
<tr class="even">
<td>39</td>
<td>ACTION_T_CALL_FOR_HELP</td>
<td>Radius</td>
<td>NU</td>
<td>NU</td>
<td>Call any friendly creatures (if its not in combat/etc) in radius attack creature target</td>
</tr>
<tr class="odd">
<td>40</td>
<td>ACTION_T_SET_SHEATH</td>
<td><a href="creature_ai_scripts#SheathState">SheathState</a></td>
<td>NU</td>
<td>NU</td>
<td>Set SheathState for creature (0-no weapon show (not used mostly by creatures), 1-melee weapon show, 2-ranged weapon show)</td>
</tr>
<tr class="even">
<td>41</td>
<td>ACTION_T_FORCE_DESPAWN</td>
<td>msDelay</td>
<td>NU</td>
<td>NU</td>
<td>Despawns the creature, If 0 despawn instant, other despawn after delay (in ms)</td>
</tr>
<tr class="odd">
<td>42</td>
<td>ACTION_T_SET_INVINCIBILITY_HP_LEVEL</td>
<td>Value</td>
<td>HP_Level(0) or HP_Percent(1)</td>
<td>NU</td>
<td>Set minimum health level for creature that can be set at damage as flat value or percent from max health</td>
</tr>
<tr class="even">
<td>43</td>
<td>ACTION_T_MOUNT_TO_ENTRY_OR_MODEL</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td><a href="creature_template#modelId1">modelId</a></td>
<td>NU</td>
<td><a href="creature_template#entry">CreatureEntry</a> (param1) or <a href="creature_template#modelId1">modelId</a> (param2) or 0 for both to dismount</td>
</tr>
<tr class="odd">
<td>44</td>
<td>ACTION_T_CHANCED_TEXT</td>
<td>Chance</td>
<td>-TextId1</td>
<td>-TextId2</td>
<td>deprecated, use 54! Chance to display the text, TextId1, optionally TextId2. If more than just -TextId1 is defined, randomize. Negative values</td>
</tr>
<tr class="even">
<td>45</td>
<td>ACTION_T_THROW_AI_EVENT</td>
<td><a href="creature_ai_scripts#AIEventType">AIEventType</a></td>
<td>Radius</td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>Throws an <a href="creature_ai_scripts#AIEventType">AIEventType</a> (Param1) to friendly Npcs in range (Param2), Invoker of event is Target</td>
</tr>
<tr class="odd">
<td>46</td>
<td>ACTION_T_SET_THROW_MASK</td>
<td>EventTypeMask</td>
<td>NU</td>
<td>NU</td>
<td>Marks for which AIEvents the npc will throw AIEvents on its own.</td>
</tr>
<tr class="even">
<td>47</td>
<td>ACTION_T_SET_STAND_STATE</td>
<td><a href="creature_template_addon#UnitStandStateType">UnitStandStateType</a></td>
<td>NU</td>
<td>NU</td>
<td>Set the UnitStandStateType (Param1) of the current creature</td>
</tr>
<tr class="odd">
<td>48</td>
<td>ACTION_T_CHANGE_MOVEMENT</td>
<td><a href="creature#MovementType">MovementType</a></td>
<td>spawndist/PathId</td>
<td>NU</td>
<td>Change the creature MovementGeneratorType (Param1). If the movement type is Random Movement (1), the spawndist (Param2) must be provided. If the movement type is Waypoint Movement (2), (Param2) is PathId</td>
</tr>
<tr class="even">
<td>49</td>
<td>ACTION_T_DYNAMIC_MOVEMENT</td>
<td>Off(0)On(1)</td>
<td>NU</td>
<td>NU</td>
<td>Disable / Enable dynamic movement behavior</td>
</tr>
<tr class="odd">
<td>50</td>
<td>ACTION_T_SET_REACT_STATE</td>
<td><a href="creature_ai_scripts#ReactStates">ReactStates</a></td>
<td>NU</td>
<td>NU</td>
<td>Change ReactState of the creature</td>
</tr>
<tr class="even">
<td>51</td>
<td>ACTION_T_PAUSE_WAYPOINTS</td>
<td>DoPause(0)UnPause(1)</td>
<td>NU</td>
<td>NU</td>
<td>Pause waypoints of creature, DoPause 0: unpause waypoint 1</td>
</tr>
<tr class="odd">
<td>52</td>
<td>ACTION_T_INTERRUPT_SPELL</td>
<td><a href="creature_ai_scripts#CurrentSpellTypes">CurrentSpellTypes</a></td>
<td>NU</td>
<td>NU</td>
<td>Interrupt spell in given slot for creature</td>
</tr>
<tr class="even">
<td>53</td>
<td>ACTION_T_START_RELAY_SCRIPT</td>
<td>RelayIDorTemplate</td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>NU</td>
<td>Launches dbscripts_on_relay script, either static one, or when (Param1) is &lt; 0 then random one chosen from dbscript_random_templates</td>
</tr>
<tr class="odd">
<td>54</td>
<td>ACTION_T_TEXT_NEW</td>
<td>-TextId</td>
<td>Target</td>
<td>TemplateId</td>
<td>Displays text, either static one or when (Param3) != 0, then random one chosen from dbscript_random_templates</td>
</tr>
<tr class="even">
<td>55</td>
<td>ACTION_T_ATTACK_START</td>
<td>Target</td>
<td>NU</td>
<td>NU</td>
<td>Starts attacking Target</td>
</tr>
<tr class="odd">
<td>56</td>
<td>ACTION_T_DESPAWN_GUARDIANS</td>
<td><a href="creature_template#entry">CreatureEntry</a></td>
<td>NU</td>
<td>NU</td>
<td>Despawns guardian with specified entry, or if 0 despawns all guardians</td>
</tr>
<tr class="even">
<td>57</td>
<td>ACTION_T_SET_RANGED_MODE</td>
<td><a href="creature_ai_scripts#RangeModeType">RangeModeType</a></td>
<td>chaseDistance</td>
<td>NU</td>
<td>Enable <a href="creature_ai_scripts#RangeModeType">RangeModeType</a>, distance to chase at, NU</td>
</tr>
<tr class="odd">
<td>58</td>
<td>ACTION_T_SET_WALK</td>
<td>WalkSettingType</td>
<td>NU</td>
<td>NU</td>
<td>RUN_DEFAULT (0), WALK_DEFAULT (1), RUN_CHASE (2), WALK_CHASE (3)</td>
</tr>
<tr class="even">
<td>59</td>
<td>ACTION_T_SET_FACING</td>
<td><a href="creature_ai_scripts#Target">target</a></td>
<td>Set (0), Reset (1)</td>
<td>NU</td>
<td>Sets facing, i.e. orientation to target, or resets it to last waypoint hit, or to respawn position</td>
</tr>
</tbody>
</table>

#### EventFlags

<table>
<colgroup>
<col width="5%" />
<col width="30%" />
<col width="63%" />
</colgroup>
<thead>
<tr class="header">
<th>Bit</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>EFLAG_REPEATABLE</td>
<td>Event repeats (Does not repeat if this flag is not set)</td>
</tr>
<tr class="even">
<td>2</td>
<td>EFLAG_NORMAL, EFLAG_DIFFICULTY_0</td>
<td>Event only occurs in Normal instance difficulty + [wotlk: (10-Man Normal)]</td>
</tr>
<tr class="odd">
<td>4</td>
<td>EFLAG_HEROIC, EFLAG_DIFFICULTY_1</td>
<td>Event only occurs in Heroic instance difficulty + [wotlk: (25-Man Normal)]</td>
</tr>
<tr class="even">
<td>8</td>
<td>EFLAG_DIFFICULTY_2</td>
<td>Event only occurs in [wotlk: (10-Man Heroic)]</td>
</tr>
<tr class="odd">
<td>16</td>
<td>EFLAG_DIFFICULTY_3</td>
<td>Event only occurs in [wotlk (25-Man Heroic)]</td>
</tr>
<tr class="even">
<td>32</td>
<td>EFLAG_RANDOM_ACTION</td>
<td>Random use action1, 2, or 3</td>
</tr>
<tr class="odd">
<td>64</td>
<td>EFLAG_RESERVED_6</td>
<td>Reserved</td>
</tr>
<tr class="even">
<td>128</td>
<td>EFLAG_DEBUG_ONLY</td>
<td>Event only occurs in debug build</td>
</tr>
<tr class="odd">
<td>256</td>
<td>EFLAG_RANGED_MODE_ONLY</td>
<td>Event only occurs in ranged mode</td>
</tr>
<tr class="even">
<td>512</td>
<td>EFLAG_MELEE_MODE_ONLY</td>
<td>Event only occurs in melee mode</td>
</tr>
<tr class="odd">
<td>1024</td>
<td>EFLAG_COMBAT_ACTION</td>
<td>Only one per cycle</td>
</tr>
</tbody>
</table>

#### Target

<table>
<colgroup>
<col width="2%" />
<col width="17%" />
<col width="80%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>TARGET_T_SELF</td>
<td>Targets itself</td>
</tr>
<tr class="even">
<td>1</td>
<td>TARGET_T_HOSTILE</td>
<td>Targets the current victim (usually the one with the most threat)</td>
</tr>
<tr class="odd">
<td>2</td>
<td>TARGET_T_HOSTILE_SECOND_AGGRO</td>
<td>Targets the unit with the second most threat in the threat list</td>
</tr>
<tr class="even">
<td>3</td>
<td>TARGET_T_HOSTILE_LAST_AGGRO</td>
<td>Targets the unit with the least threat in the threat list</td>
</tr>
<tr class="odd">
<td>4</td>
<td>TARGET_T_HOSTILE_RANDOM</td>
<td>Targets a random unit from the threat list</td>
</tr>
<tr class="even">
<td>5</td>
<td>TARGET_T_HOSTILE_RANDOM_NOT_TOP</td>
<td>Targets a random unit from the threat list excluding the one with the most threat</td>
</tr>
<tr class="odd">
<td>6</td>
<td>TARGET_T_ACTION_INVOKER</td>
<td>Targets the unit that caused the event; only for certain events only.</td>
</tr>
<tr class="even">
<td>7</td>
<td>TARGET_T_ACTION_INVOKER_OWNER</td>
<td>Targets unit who is responsible for Event to occur (only works for EVENT_T_AGGRO, EVENT_T_KILL, EVENT_T_DEATH, EVENT_T_SPELLHIT, EVENT_T_OOC_LOS, EVENT_T_RECEIVE_EMOTE, EVENT_T_RECEIVE_AI_EVENT)</td>
</tr>
<tr class="odd">
<td>8</td>
<td>TARGET_T_HOSTILE_RANDOM_PLAYER</td>
<td>Targets Random Player on The Threat List</td>
</tr>
<tr class="even">
<td>9</td>
<td>TARGET_T_HOSTILE_RANDOM_NOT_TOP_PLAYER</td>
<td>Targets Any Random Player Except Top Threat</td>
</tr>
<tr class="odd">
<td>10</td>
<td>TARGET_T_EVENT_SENDER</td>
<td>Creature who sent a received AIEvent - only triggered by EVENT_T_RECEIVE_AI_EVENT</td>
</tr>
<tr class="even">
<td>11</td>
<td>TARGET_T_SPAWNER</td>
<td>Owner of unit if exists</td>
</tr>
<tr class="odd">
<td>12</td>
<td>TARGET_T_EVENT_SPECIFIC</td>
<td>Filled by specific event (works for EVENT_T_FRIENDLY_HP, EVENT_T_FRIENDLY_IS_CC, EVENT_T_FRIENDLY_MISSING_BUFF)</td>
</tr>
<tr class="even">
<td>13</td>
<td>TARGET_T_PLAYER_INVOKER</td>
<td>Player who initiated hostile contact with this npc</td>
</tr>
<tr class="odd">
<td>14</td>
<td>TARGET_T_PLAYER_TAPPED</td>
<td>Player who currently holds to score the kill credit from the npc</td>
</tr>
<tr class="even">
<td>15</td>
<td>TARGET_T_NONE</td>
<td>Default spell target - sets nullptr which should be most common spell fill</td>
</tr>
<tr class="odd">
<td>16</td>
<td>TARGET_T_HOSTILE_RANDOM_MANA</td>
<td>Random target with mana</td>
</tr>
<tr class="even">
<td>17</td>
<td>TARGET_T_NEAREST_AOE_TARGET</td>
<td>Checks for available near aoe targets by EffectRadiusIndex[0] for the spell used</td>
</tr>
<tr class="odd">
<td>18</td>
<td>TARGET_T_HOSTILE_FARTHEST_AWAY</td>
<td>Farthest away target, excluding melee range</td>
</tr>
</tbody>
</table>

#### castFlags

<table>
<colgroup>
<col width="4%" />
<col width="24%" />
<col width="71%" />
</colgroup>
<thead>
<tr class="header">
<th>Bit</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>CAST_INTERRUPT_PREVIOUS</td>
<td>Interrupts any previous spell casting.</td>
</tr>
<tr class="even">
<td>2</td>
<td>CAST_TRIGGERED</td>
<td>Forces the cast to be instant and ignores any mana/reagents requirements.</td>
</tr>
<tr class="odd">
<td>4</td>
<td>CAST_FORCE_CAST</td>
<td>Forces spell to cast even if the target is possibly out of range or the creature is possibly out of mana</td>
</tr>
<tr class="even">
<td>8</td>
<td>CAST_NO_MELEE_IF_OOM</td>
<td>Prevents creature from entering melee if out of mana or out of range</td>
</tr>
<tr class="odd">
<td>16</td>
<td>CAST_FORCE_TARGET_SELF</td>
<td>Forces the target to cast this spell on itself</td>
</tr>
<tr class="even">
<td>32</td>
<td>CAST_AURA_NOT_PRESENT</td>
<td>Only casts the spell on the target if the target does not have the aura from that spell on itself already.</td>
</tr>
<tr class="odd">
<td>64</td>
<td>CAST_IGNORE_UNSELECTABLE_TARGET</td>
<td>Can target UNIT_FLAG_NOT_SELECTABLE - Needed in some scripts</td>
</tr>
<tr class="even">
<td>128</td>
<td>CAST_SWITCH_CASTER_TARGET</td>
<td>Switches target and caster for spell cast</td>
</tr>
<tr class="odd">
<td>256</td>
<td>CAST_MAIN_SPELL</td>
<td>Marks main spell for AI Type = Action 57 ACTION_T_SET_RANGED_MODE</td>
</tr>
<tr class="even">
<td>512</td>
<td>CAST_PLAYER_ONLY</td>
<td>Selects only player targets - substitution for EAI not having more params</td>
</tr>
<tr class="odd">
<td>1024</td>
<td>CAST_DISTANCE_YOURSELF</td>
<td>If spell with this cast flag hits main aggro target, caster distances himself - EAI only</td>
</tr>
</tbody>
</table>

#### schoolMask

| Value | Type                                      |
|-------|-------------------------------------------|
| 1     | SPELL\_SCHOOL\_MASK\_NORMAL (Physical)    |
| 2     | SPELL\_SCHOOL\_MASK\_HOLY                 |
| 4     | SPELL\_SCHOOL\_MASK\_FIRE                 |
| 8     | SPELL\_SCHOOL\_MASK\_NATURE               |
| 16    | SPELL\_SCHOOL\_MASK\_FROST                |
| 32    | SPELL\_SCHOOL\_MASK\_SHADOW               |
| 64    | SPELL\_SCHOOL\_MASK\_ARCANE               |
| 124   | SPELL\_SCHOOL\_MASK\_SPELL (without Holy) |
| 126   | SPELL\_SCHOOL\_MASK\_MAGIC                |
| 127   | SPELL\_SCHOOL\_MASK\_ALL                  |

#### DispelType

| Value | Type                 |
|-------|----------------------|
| 0     | DISPEL\_NONE         |
| 1     | DISPEL\_MAGIC        |
| 2     | DISPEL\_CURSE        |
| 3     | DISPEL\_DISEASE      |
| 4     | DISPEL\_POISON       |
| 5     | DISPEL\_STEALTH      |
| 6     | DISPEL\_INVISIBILITY |
| 7     | DISPEL\_ALL          |

#### AIEventType

<table style="width:100%;">
<colgroup>
<col width="6%" />
<col width="26%" />
<col width="25%" />
<col width="41%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Type</th>
<th>Sender</th>
<th>Invoker</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>AI_EVENT_JUST_DIED</td>
<td>Killed Npc</td>
<td>Killer</td>
</tr>
<tr class="even">
<td>1</td>
<td>AI_EVENT_CRITICAL_HEALTH</td>
<td>Hurt Npc</td>
<td>DamageDealer - Expected to be sent by 10% health</td>
</tr>
<tr class="odd">
<td>2</td>
<td>AI_EVENT_LOST_HEALTH</td>
<td>Hurt Npc</td>
<td>DamageDealer - Expected to be sent by 50% health</td>
</tr>
<tr class="even">
<td>3</td>
<td>AI_EVENT_LOST_SOME_HEALTH</td>
<td>Hurt Npc</td>
<td>DamageDealer - Expected to be sent by 90% health</td>
</tr>
<tr class="odd">
<td>4</td>
<td>AI_EVENT_GOT_FULL_HEALTH</td>
<td>Healed Npc</td>
<td>Healer</td>
</tr>
<tr class="even">
<td>5</td>
<td>AI_EVENT_CUSTOM_EVENTAI_A</td>
<td>Npc that throws custom event</td>
<td>TARGET_T_ACTION_INVOKER (if exists)</td>
</tr>
<tr class="odd">
<td>6</td>
<td>AI_EVENT_CUSTOM_EVENTAI_B</td>
<td>Npc that throws custom event</td>
<td>TARGET_T_ACTION_INVOKER (if exists)</td>
</tr>
<tr class="even">
<td>7</td>
<td>AI_EVENT_GOT_CCED</td>
<td>CCed Npc</td>
<td>Caster that CCed</td>
</tr>
<tr class="odd">
<td>8</td>
<td>AI_EVENT_CUSTOM_EVENTAI_C</td>
<td>Npc that throws custom event</td>
<td>TARGET_T_ACTION_INVOKER (if exists)</td>
</tr>
<tr class="even">
<td>9</td>
<td>AI_EVENT_CUSTOM_EVENTAI_D</td>
<td>Npc that throws custom event</td>
<td>TARGET_T_ACTION_INVOKER (if exists)</td>
</tr>
<tr class="odd">
<td>10</td>
<td>AI_EVENT_CUSTOM_EVENTAI_E</td>
<td>Npc that throws custom event</td>
<td>TARGET_T_ACTION_INVOKER (if exists)</td>
</tr>
<tr class="even">
<td>11</td>
<td>AI_EVENT_CUSTOM_EVENTAI_F</td>
<td>Npc that throws custom event</td>
<td>TARGET_T_ACTION_INVOKER (if exists)</td>
</tr>
</tbody>
</table>

#### TemporaryFactionFlags

<table>
<colgroup>
<col width="2%" />
<col width="3%" />
<col width="19%" />
<col width="75%" />
</colgroup>
<thead>
<tr class="header">
<th>Bit</th>
<th>Hex</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>0x00</td>
<td>TEMPFACTION_NONE</td>
<td>When no flag is used in temporary faction change, faction will be persistent. It will then require manual change back to default/another faction when changed once</td>
</tr>
<tr class="even">
<td>1</td>
<td>0x01</td>
<td>TEMPFACTION_RESTORE_RESPAWN</td>
<td>Default faction will be restored at respawn</td>
</tr>
<tr class="odd">
<td>2</td>
<td>0x02</td>
<td>TEMPFACTION_RESTORE_COMBAT_STOP</td>
<td>at CombatStop() (happens at creature death, at evade or custom scripte among others)</td>
</tr>
<tr class="even">
<td>4</td>
<td>0x04</td>
<td>TEMPFACTION_RESTORE_REACH_HOME</td>
<td>at reaching home in home movement (evade), if not already done at CombatStop()</td>
</tr>
<tr class="odd">
<td>8</td>
<td>0x08</td>
<td>TEMPFACTION_TOGGLE_NON_ATTACKABLE</td>
<td>Remove UNIT_FLAG_NON_ATTACKABLE(0x02) when faction is changed (reapply when temp-faction is removed)</td>
</tr>
<tr class="even">
<td>16</td>
<td>0x10</td>
<td>TEMPFACTION_TOGGLE_IMMUNE_TO_PLAYER</td>
<td>Remove UNIT_FLAG_IMMUNE_TO_PLAYER(0x100) when faction is changed (reapply when temp-faction is removed)</td>
</tr>
<tr class="odd">
<td>32</td>
<td>0x20</td>
<td>TEMPFACTION_TOGGLE_IMMUNE_TO_NPC</td>
<td>Remove UNIT_FLAG_PASSIVE(0x200) when faction is changed (reapply when temp-faction is removed)</td>
</tr>
<tr class="even">
<td>64</td>
<td>0x40</td>
<td>TEMPFACTION_TOGGLE_PACIFIED</td>
<td>Remove UNIT_FLAG_PACIFIED(0x20000) when faction is changed (reapply when temp-faction is removed)</td>
</tr>
<tr class="odd">
<td>128</td>
<td>0x80</td>
<td>TEMPFACTION_TOGGLE_NOT_SELECTABLE</td>
<td>Remove UNIT_FLAG_NOT_SELECTABLE(0x2000000) when faction is changed (reapply when temp-faction is removed)</td>
</tr>
</tbody>
</table>

#### EUnitFields

| Value | Type                        | Description      |
|-------|-----------------------------|------------------|
| 22    | UNIT\_FIELD\_HEALTH         | Health           |
| 24    | UNIT\_FIELD\_POWER2         | Mana             |
| 34    | UNIT\_FIELD\_LEVEL          | Level            |
| 150   | UNIT\_FIELD\_BOUNDINGRADIUS | bounding\_radius |
| 151   | UNIT\_FIELD\_COMBATREACH    | combat\_reach    |
| 164   | UNIT\_DYNAMIC\_FLAGS        | DynamicFlags     |
| 168   | UNIT\_NPC\_FLAGS            | NpcFlags         |

#### ReactStates

| Value | Type              | Description                                      |
|-------|-------------------|--------------------------------------------------|
| 0     | REACT\_PASSIVE    | Wont attack on its own, maybe due to CallForHelp |
| 1     | REACT\_DEFENSIVE  | Will attack when attacked                        |
| 2     | REACT\_AGGRESSIVE | Will attack (default)                            |

#### CurrentSpellTypes

| Value | Type                       | Description |
|-------|----------------------------|-------------|
| 0     | CURRENT\_MELEE\_SPELL      |             |
| 1     | CURRENT\_GENERIC\_SPELL    |             |
| 2     | CURRENT\_AUTOREPEAT\_SPELL |             |
| 3     | CURRENT\_CHANNELED\_SPELL  |             |

#### Instance\_Data\_Flags

| Value | Type    | Description                                             |
|-------|---------|---------------------------------------------------------|
| 1     | Aggro   | Creature SetInCombat                                    |
| 2     | Evade   | Creature remove from Combat                             |
| 3     | Death   | Creature just die                                       |
| 4     | Special | Need for more as one enemy in a fight (like 4 horseman) |

#### RangeModeType

| Value | Type               | Description                 |
|-------|--------------------|-----------------------------|
| 0     | TYPE\_NONE         | Melee Mode                  |
| 1     | TYPE\_FULL\_CASTER | Caster Mode                 |
| 2     | TYPE\_PROXIMITY    | Hunter Mode(keeps distance) |

#### SheathState

b2\_0\_sheath

| Bit | Name                   | Comment                     |
|-----|------------------------|-----------------------------|
| 0   | SHEATH\_STATE\_UNARMED | all weapons sheathed        |
| 1   | SHEATH\_STATE\_MELEE   | melee weapon(s) unsheathed  |
| 2   | SHEATH\_STATE\_RANGED  | ranged weapon(s) unsheathed |

#### UnitStandStateType

bytes1

<table>
<colgroup>
<col width="5%" />
<col width="35%" />
<col width="59%" />
</colgroup>
<thead>
<tr class="header">
<th>Bit</th>
<th>Name</th>
<th>Comment</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>UNIT_STAND_STATE_STAND</td>
<td>normal behavior</td>
</tr>
<tr class="even">
<td>1</td>
<td>UNIT_STAND_STATE_SIT</td>
<td>sitting on ground</td>
</tr>
<tr class="odd">
<td>2</td>
<td>UNIT_STAND_STATE_SIT_CHAIR</td>
<td>sitting on normal chair</td>
</tr>
<tr class="even">
<td>3</td>
<td>UNIT_STAND_STATE_SLEEP</td>
<td>sleeping</td>
</tr>
<tr class="odd">
<td>4</td>
<td>UNIT_STAND_STATE_SIT_LOW_CHAIR</td>
<td>sitting on low chair</td>
</tr>
<tr class="even">
<td>5</td>
<td>UNIT_STAND_STATE_SIT_MEDIUM_CHAIR</td>
<td>sitting on medium chair</td>
</tr>
<tr class="odd">
<td>6</td>
<td>UNIT_STAND_STATE_SIT_HIGH_CHAIR</td>
<td>sitting on high chair</td>
</tr>
<tr class="even">
<td>7</td>
<td>UNIT_STAND_STATE_DEAD</td>
<td>play dead</td>
</tr>
<tr class="odd">
<td>8</td>
<td>UNIT_STAND_STATE_KNEEL</td>
<td>kneel</td>
</tr>
<tr class="even">
<td>9</td>
<td>UNIT_STAND_STATE_CUSTOM</td>
<td>Depends on model animation. Submerge, freeze, hide, hibernate, rest</td>
</tr>
</tbody>
</table>

#### event\_inverse\_phase\_mask

#### Ranged mode - reference usage

('58902','589','11','0','100','0','0','0','0','0','0','0','57','1','35','0','0','0','0','0','0','0','0','0','Defias Pillager - Enable Caster Mode on Spawn'),
('58905','589','0','0','100','1025','0','0','3400','4900','0','0','11','20793','1','256','0','0','0','0','0','0','0','0','Defias Pillager - Cast Fireball'),

The ranged mode was designed to be toggled on spawn, but can effectively by toggled on phase change on other condition when needed. It automatically reverts itself on evade. It works in connection with its modes, and automatically changes chase distance. A main casting spell, which is supposed to be lowest in priority (highest ID), needs to use 256 cast flag. This notes that when this spell returns OOM error, ranged mode automatically adjusts its behaviour. Ranged mode also responds to kicks and silence on this spell. Last notable feature with ranged mode is distancing, which only occurs if cast flag 1024 is set, and when creature is in melee mode, and the target is hit, creature runs away from main aggro targets melee reach.
