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

| Field                                                                    | Type | Null | Key | Default | Description                                                                                                                                                                                  |
| ------------------------------------------------------------------------ | ---- | ---- | --- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [id](creature_ai_scripts#id)                                             |      | NO   | PRI | None    | Primary Key                                                                                                                                                                                  |
| [creature_id](creature_ai_scripts#id)                                    |      | NO   |     |         | [CreatureEntry](creature_template#entry)                                                                                                                                                     |
| [event_type](creature_ai_scripts#event_type)                             |      | NO   |     |         | Event                                                                                                                                                                                        |
| [event_inverse_phase_mask](creature_ai_scripts#event_inverse_phase_mask) |      | NO   |     |         | PhaseMask                                                                                                                                                                                    |
| [event_chance](creature_ai_scripts#event_chance)                         |      | NO   |     |         | Chance. Using a value of 0 in this field will make the event never occur. Values are from 0 to 100.                                                                                          |
| [event_flags](creature_ai_scripts#eventflags)                            |      | NO   |     |         | Every event also has a `chance` field that controls the chance of that event actually occurring. Using a value of 0 in this field will make the event never occur. Values are from 0 to 100. |
| [event_param](creature_ai_scripts#event_param)                           |      | NO   |     |         | event_param1-3 for Event                                                                                                                                                                     |
| [action_type](creature_ai_scripts#action_type)                           |      | NO   |     |         | action_type1-3 for Event                                                                                                                                                                     |
| [action_param](creature_ai_scripts#action_param)                         |      | NO   |     |         | action_param1-3 for action_type1-3                                                                                                                                                           |
| [comment](creature_ai_scripts#comment)                                   |      |      |     |         | comment describing the actions performed on event                                                                                                                                            |

Example:

let's say that a certain creature using EventAI will have a max of four phases. We are then dealing with a 4 bit number in this field. Let's further say that that certain creature has an event that will only trigger in its phase 2 (a timed spell cast for instance). Then the field should contain all of the phases the event SHOULDN'T be triggered in...then out of the four bits, we leave the **third** bit alone (off) and turn on all of the other bits so we get 1011 which is equal to 11, so we put in 11 as the inverse phase mask for the event entry. As another example, let's say that the same creature previously mentioned has another event that is only triggered in the phase 0 and phase 3. This would mean that we need to ignore phase 1 and 2, so our bitmask would be 0110 which is equal to 6 so we put in 6 for this event's inverse phase mask field. Please note that both examples were tailored for a creature with four and only four phases. If you decide to add more phases later on, you will have to redefine all of the nonzero bitmasks for all of the mob's events.

EventAI can also support phases. A <u>phase</u> is just a way to group certain events + actions together so that the creature will perform certain actions based on what event it is currently on. The way the phase system works in EventAI is that for every event added, it needs to be specified under which phases the event <u>SHOULD NOT</u> occur. This is a bit confusing at first, so let's look at it more closely. A creature can have more than one phase, up to a max of 32 different phases (with the first one being phase 0, and last one being phase 31). How the phase selection field works is that it contains a 32bit number. Each bit in the number represents a possible phase, with the bit in the least significant position signifying phase 0 and the most significant bit signifying phase 31. The default value of zero in this field has no bits set and since the field controls when the event should NOT trigger, it would then mean that the event will always be triggered independent of the current phase the creature is in. Therefore, if you want to specify what phases the event should occur in, you need to add up all of the corresponding bits for all the other phases where the event shouldn't trigger in (confusing...yes).

All of the [events](creature_ai_scripts#event_type), [EventFlags](creature_ai_scripts#EventFlags), [actions](creature_ai_scripts#action_type) and possible [targets](creature_ai_scripts#Target) are summarized and described below.

-   NU = Not Used\*
-   IC = In Combat Only\*
-   OOC = Out Of Combat Only\*
-   US = Unsupported

#### event\_type

| ID  | Name                                | Param1                                         | Param2                                       | Param3    | Param4    | Description                                                                                                                                                                                                                      |
| --- | ----------------------------------- | ---------------------------------------------- | -------------------------------------------- | --------- | --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0   | EVENT_T_TIMER_IN_COMBAT             | InitialMin                                     | InitialMax                                   | RepeatMin | RepeatMax | IC - Expires first between (Param1) and (Param2). Will repeat every (Param3) and (Param4)                                                                                                                                        |
| 1   | EVENT_T_TIMER_OOC                   | InitialMin                                     | InitialMax                                   | RepeatMin | RepeatMax | OOC - Expires first between (Param1) and (Param2). Will repeat every (Param3) and (Param4)                                                                                                                                       |
| 2   | EVENT_T_HP                          | HPMax%                                         | HPMin%                                       | RepeatMin | RepeatMax | IC - Expires when HP% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4)                                                                                                                                  |
| 3   | EVENT_T_MANA                        | ManaMax%                                       | ManaMin%                                     | RepeatMin | RepeatMax | IC - Expires when Mana% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4)                                                                                                                                |
| 4   | EVENT_T_AGGRO                       | NU                                             | NU                                           | NU        | NU        | Expires on Aggro                                                                                                                                                                                                                 |
| 5   | EVENT_T_KILL                        | RepeatMin                                      | RepeatMax                                    | NU        | NU        | Expires on Player Kill. Will repeat every (Param3) and (Param4)                                                                                                                                                                  |
| 6   | EVENT_T_DEATH                       | NU                                             | NU                                           | NU        | NU        | Expires on Death                                                                                                                                                                                                                 |
| 7   | EVENT_T_EVADE                       | NU                                             | NU                                           | NU        | NU        | Expires on Evade                                                                                                                                                                                                                 |
| 8   | EVENT_T_SPELLHIT                    | [spellId](spell_template#Id)                   | [schoolMask](creature_ai_scripts#schoolMask) | RepeatMin | RepeatMax | Expires on (Param1) [schoolMask](creature_ai_scripts#schoolMask) spellhit. Will repeat every (Param3) and (Param4)                                                                                                               |
| 9   | EVENT\_T\_RANGE                     | MinDist                                        | MaxDist                                      | RepeatMin | RepeatMax | Expires when current target distance is greater than (Param1) and less than (Param2). Will repeat every (Param3) and (Param4)                                                                                                    |
| 10  | EVENT\_T\_OOC\_LOS                  | noHostile                                      | MaxRange                                     | RepeatMin | RepeatMax | OOC - Expires when a unit (friendly only if Param1 = 1) moves within (Param2) distance to creature. Will repeat every (Param3) and (Param4)                                                                                      |
| 11  | EVENT\_T\_SPAWNED                   | NU                                             | NU                                           | NU        | NU        | Expires on Spawn                                                                                                                                                                                                                 |
| 12  | EVENT\_T\_TARGET\_HP                | HPMax%                                         | HPMin%                                       | RepeatMin | RepeatMax | Expires when current target HP% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4)                                                                                                                        |
| 13  | EVENT\_T\_TARGET\_CASTING           | RepeatMin                                      | RepeatMax                                    | NU        | NU        | Expires when current target is casting a spell. Will repeat every (Param1) and (Param2)                                                                                                                                          |
| 14  | EVENT\_T\_FRIENDLY\_HP              | HPDeficit                                      | Radius                                       | RepeatMin | RepeatMax | Expires when a friendly unit (Target = 12) has at least (param1) HP missing in (param2) radius. Will repeat every (Param3) and (Param4)                                                                                          |
| 15  | EVENT\_T\_FRIENDLY\_IS\_CC          | DispelType (US)                                | Radius                                       | RepeatMin | RepeatMax | Expires when a friendly unit (Target = 12) is crowd controlled in (param2) radius. Will repeat every (Param3) and (Param4)                                                                                                       |
| 16  | EVENT\_T\_FRIENDLY\_MISSING\_BUFF   | [spellId](spell_template#Id)                   | Radius                                       | RepeatMin | RepeatMax | Expires when a friendly unit (Target = 12) is missing aura given by (param1) [spellId](spell_template#Id) in (param2) radius. Will repeat every (Param3) and (Param4)                                                            |
| 17  | EVENT\_T\_SUMMONED\_UNIT            | [CreatureEntry](creature_template#entry)       | RepeatMin                                    | RepeatMax | NU        | Expires when creature with (Param1) [CreatureEntry](creature_template#entry) spawned or for all spawns if (Param1 = 0). Will repeat every (Param2) and (Param3)                                                                  |
| 18  | EVENT\_T\_TARGET\_MANA              | ManaMax%                                       | ManaMin%                                     | RepeatMin | RepeatMax | Expires when current target MP% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4)                                                                                                                        |
| 21  | EVENT\_T\_REACHED\_HOME             | NU                                             | NU                                           | NU        | NU        | Expires on Reached Home (after Evade)                                                                                                                                                                                            |
| 22  | EVENT\_T\_RECEIVE\_EMOTE            | TextEmote                                      | [ConditionId](conditions#condition_entry)    | NU        | NU        | Expires when creature receives [TextEmotes](https://github.com/cmangos/mangos-cata/blob/b76261946597de1200effc4236409a3978414056/src/game/Globals/SharedDefines.h#L1643) from player paired with a potential condition (Param 2) |
| 23  | EVENT\_T\_AURA                      | [spellId](spell_template#Id)                   | AmmountInStack                               | RepeatMin | RepeatMax | Expires when creature has spell (Param1) aura stacks applied greater or equal to (Param2) amount. Will repeat every (Param3) and (Param4)                                                                                        |
| 24  | EVENT\_T\_TARGET\_AURA              | [spellId](spell_template#Id)                   | AmmountInStack                               | RepeatMin | RepeatMax | Expires when current target have spell (Param1) aura stacks applied greater or equal to (Param2) amount. Will repeat every (Param3) and (Param4)                                                                                 |
| 25  | EVENT\_T\_SUMMONED\_JUST\_DIED      | [CreatureEntry](creature_template#entry)       | RepeatMin                                    | RepeatMax | NU        | Expires after creature with (Param1) [CreatureEntry](creature_template#entry) died or for all spawns if (Param1 = 0). Will repeat every (Param2) and (Param3)                                                                    |
| 26  | EVENT\_T\_SUMMONED\_JUST\_DESPAWN   | [CreatureEntry](creature_template#entry)       | RepeatMin                                    | RepeatMax | NU        | Expires before creature with (Param1) [CreatureEntry](creature_template#entry) despawned or for all spawns if (Param1 = 0). Will repeat every (Param2) and (Param3)                                                              |
| 27  | EVENT\_T\_MISSING\_AURA             | [spellId](spell_template#Id)                   | AmmountInStack                               | RepeatMin | RepeatMax | Expires when creature have spell (Param1) aura stacks applied less than (Param2) amount. Will repeat every (Param3) and (Param4)                                                                                                 |
| 28  | EVENT\_T\_TARGET\_MISSING\_AURA     | [spellId](spell_template#Id)                   | AmmountInStack                               | RepeatMin | RepeatMax | Expires when current target have spell (Param1) aura stacks applied less than (Param2) amount. Will repeat every (Param3) and (Param4)                                                                                           |
| 29  | EVENT\_T\_TIMER\_GENERIC            | InitialMin                                     | InitialMax                                   | RepeatMin | RepeatMax | Expires first between (Param1) and (Param2). Will repeat every (Param3) and (Param4)                                                                                                                                             |
| 30  | EVENT\_T\_RECEIVE\_AI\_EVENT        | [AIEventType](creature_ai_scripts#AIEventType) | Sender-Entry                                 | NU        | NU        | Expires when the creature receives an (Param1) [Sender-Entry](creature_template#entry). If (Param2 = 0) then sent by any creature                                                                                                |
| 31  | EVENT\_T\_ENERGY                    | EnergyMax%                                     | EnergyMin%                                   | RepeatMin | RepeatMax | Expires when Energy% is between (Param1) and (Param2). Will repeat every (Param3) and (Param4) if Condition: between (Param1) and (Param2) are still met                                                                         |
| 32  | EVENT\_T\_SELECT\_ATTACKING\_TARGET | MinRange                                       | MaxRange                                     | RepeatMin | RepeatMax | Expires when threat table has target with distance between (Param1) and (Param2). Will repeat every (Param3) and (Param4) if Condition: between (Param1) and (Param2) are still met                                              |
| 33  | EVENT\_T\_FACING\_TARGET            | Back(0)OrFront(1)                              | NU                                           | RepeatMin | RepeatMax | Expires when creature is (behind = 0 / infront = 1 of target. Will repeat every (Param3) and (Param4) if Condition: (Param1) is still met                                                                                        |

Now that all of the supported events have been listed and described, we shall now move on to the actions that can be performed.

Each event can take up to three actions. The actions will all be performed when the event is triggered and they will be performed in the order that they have been defined. This means that, for a certain event, action 1 will be performed first, followed by action 2, then lastly by action 3.

Just like event definitions, each action can use up to three different parameters but not all actions will use all three parameters. If a parameter isn't mentioned for an action, then that action does not need that parameter.

#### action\_type

| ID  | Name                                     | Param 1                                                          | Param 2                                                            | Param 3                                    | Description                                                                                                                                                                                                 |
| --- | ---------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------ | ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0   | ACTION_T_NONE                            | NU                                                               | NU                                                                 | NU                                         | Does nothing!                                                                                                                                                                                               |
| 1   | ACTION_T_TEXT                            | -TextId1                                                         | -TextId2                                                           | -TextId3                                   | deprecated, \[use action 54 for 1 / 4+ [custom\_texts](creature_ai_texts) can be used                                                                                                                       |
| 2   | ACTION\_T\_SET\_FACTION                  | factionId                                                        | [TemporaryFactionFlags](creature_ai_scripts#TemporaryFactionFlags) | NU                                         | Changes faction for a creature. When (Param1) is zero, creature will revert to it's default faction. Flags will determine when faction is restored to default (evade, respawn etc)                          |
| 3   | ACTION\_T\_MORPH\_TO\_ENTRY\_OR\_MODEL   | [CreatureEntry](creature_template#entry)                         | [modelId](creature_template#modelId1)                              | NU                                         | [modelId](ccreature_template#modelId1) (param2) (or 0 for both to demorph)                                                                                                                                  |
| 4   | ACTION\_T\_SOUND                         | SoundId                                                          | NU                                                                 | NU                                         | Creature plays Sound. IDs are contained in the DBC files                                                                                                                                                    |
| 5   | ACTION\_T\_EMOTE                         | [emoteId](creature_template_addon#emote)                         | NU                                                                 | NU                                         | Creature does visual emote. IDs are contained in the DBC files                                                                                                                                              |
| 6   | ACTION\_T\_RANDOM\_SAY                   | NU                                                               | NU                                                                 | NU                                         | deprecated                                                                                                                                                                                                  |
| 7   | ACTION\_T\_RANDOM\_YELL                  | NU                                                               | NU                                                                 | NU                                         | deprecated                                                                                                                                                                                                  |
| 8   | ACTION\_T\_RANDOM\_TEXTEMOTE             | NU                                                               | NU                                                                 | NU                                         | deprecated                                                                                                                                                                                                  |
| 9   | ACTION\_T\_RANDOM\_SOUND                 | Sound ID 1                                                       | Sound ID 2                                                         | Sound ID 3                                 | Picks a sound ID at random and plays it; -1 = action skipped if chosen                                                                                                                                      |
| 10  | ACTION\_T\_RANDOM\_EMOTE                 | Emote ID 1                                                       | Emote ID 2                                                         | Emote ID 3                                 | Picks an emote ID at random and does visual emote; -1 = action skipped if chosen                                                                                                                            |
| 11  | ACTION\_T\_CAST                          | [spellId](spell_template#Id)                                     | [target](creature_ai_scripts#Target)                               | [castFlags](creature_ai_scripts#castFlags) | Creature cast spell on a target with specified [castFlags](creature_ai_scripts#castFlags)                                                                                                                   |
| 12  | ACTION\_T\_SPAWN                         | [CreatureEntry](creature_template#entry)                         | [target](creature_ai_scripts#Target)                               | Duration in milliseconds                   | Creature spawns a creature with (Param1) [CreatureEntry](creature_template#entry) at Target for a given duration (infinite if zero)                                                                         |
| 13  | ACTION\_T\_THREAT\_SINGLE\_PCT           | Threat %                                                         | [target](creature_ai_scripts#Target)                               | NU                                         | Modifies [target](creature_ai_scripts#Target) threat by a percent (-100 to +100)                                                                                                                            |
| 14  | ACTION\_T\_THREAT\_ALL\_PCT              | Threat %                                                         | NU                                                                 | NU                                         | Modifies everyone's threat by a percent (-100 to +100), will not cause Evade                                                                                                                                |
| 15  | ACTION\_T\_QUEST\_EVENT                  | Quest ID                                                         | [target](creature_ai_scripts#Target)                               | NU                                         | Satisfies external script objective for a quest for the target (MUST be a player)                                                                                                                           |
| 16  | ACTION\_T\_CAST\_EVENT                   | [CreatureEntry](creature_template#entry)                         | [spellId](spell_template#Id)                                       | [target](creature_ai_scripts#Target)       | Emulates spell cast on the creature for the target (must be a player) \[hacky\]                                                                                                                             |
| 17  | ACTION\_T\_SET\_UNIT\_FIELD              | [EUnitFields](creature_ai_scripts#EUnitFields)                   | Value                                                              | [target](creature_ai_scripts#Target)       | Sets unit field at the index to the value given for the target. More information on the field value indeces can be found at [character data](character) data                                                |
| 18  | ACTION\_T\_SET\_UNIT\_FLAG               | [UnitFlags](creature_template#unitflags)                         | [target](creature_ai_scripts#Target)                               | NU                                         | Sets flag(s) on the target                                                                                                                                                                                  |
| 19  | ACTION\_T\_REMOVE\_UNIT\_FLAG            | [UnitFlags](creature_template#unitflags)                         | [target](creature_ai_scripts#Target)                               | NU                                         | Removes flag(s) from the target                                                                                                                                                                             |
| 20  | ACTION\_T\_AUTO\_ATTACK                  | Boolean                                                          | NU                                                                 | NU                                         | If 0 cant melee, else (1) continues/starts it                                                                                                                                                               |
| 21  | ACTION\_T\_COMBAT\_MOVEMENT              | Boolean                                                          | NU                                                                 | NU                                         | If 0 stops movement, else (1) continues/starts it                                                                                                                                                           |
| 22  | ACTION\_T\_SET\_PHASE                    | Phase \#                                                         | NU                                                                 | NU                                         | Sets current phase to number given. This number must be an integer between 0 and 31 inclusive                                                                                                               |
| 23  | ACTION\_T\_INC\_PHASE                    | Number                                                           | NU                                                                 | NU                                         | deprecated, increments (or decrements) the phase by given number                                                                                                                                            |
| 24  | ACTION\_T\_EVADE                         | NU                                                               | NU                                                                 | NU                                         | Force creature reset. Exit combat + lose threat, true Evade                                                                                                                                                 |
| 25  | ACTION\_T\_FLEE\_FOR\_ASSIST             | NU                                                               | NU                                                                 | NU                                         | Force creature to flee from combat                                                                                                                                                                          |
| 26  | ACTION\_T\_QUEST\_EVENT\_ALL             | Quest ID                                                         | NU                                                                 | NU                                         | Satisfies external objective for a quest for all players in threat list similar to ACTION\_T\_QUEST\_EVENT                                                                                                  |
| 27  | ACTION\_T\_CAST\_EVENT\_ALL              | Quest ID                                                         | [spellId](spell_template#Id)                                       | NU                                         | Emulates spell cast on creature for all players in threat list similar to ACTION\_T\_CAST\_EVENT                                                                                                            |
| 28  | ACTION\_T\_REMOVEAURASFROMSPELL          | [target](creature_ai_scripts#Target)                             | [spellId](spell_template#Id)                                       | NU                                         | Removes all auras from a [spellId](spell_template#Id) from the target                                                                                                                                       |
| 29  | ACTION\_T\_RANGED\_MOVEMENT              | Distance                                                         | Angle                                                              | NU                                         | creature sets ranged movement generator keeping the creature at a distance. Note that specifying zero angle and distance will make it just melee instead                                                    |
| 30  | ACTION\_T\_RANDOM\_PHASE                 | Phase 1                                                          | Phase 2                                                            | Phase 3                                    | Randomly chooses a phase from the list of three phases                                                                                                                                                      |
| 31  | ACTION\_T\_RANDOM\_PHASE\_RANGE          | Min Phase                                                        | Max Phase + 1                                                      | NU                                         | Chooses a random phase in the range specified. This number must be an integer between 0 and 31 inclusive                                                                                                    |
| 32  | ACTION\_T\_SUMMON\_ID                    | [CreatureEntry](creature_template#entry)                         | [target](creature_ai_scripts#Target)                               | Summon ID                                  | Summons a creature using the data specified in the separate [creature\_ai\_summons](creature_ai_summons) table                                                                                              |
| 33  | ACTION\_T\_KILLED\_MONSTER               | [CreatureEntry](creature_template#entry)                         | [target](creature_ai_scripts#Target)                               | NU                                         | Simulates a kill for a [target](creature_template#creature_ai_scripts#Target)                                                                                                                               |
| 34  | ACTION\_T\_SET\_INST\_DATA               | Field                                                            | 32 bit Value                                                       | NU                                         | Sets data for the instance. Note that this will only work when the creature is inside an instantiable zone that has a valid script (ScriptedInstance) assigned.                                             |
| 35  | ACTION\_T\_SET\_INST\_DATA64             | Field                                                            | [target](creature_ai_scripts#Target)                               | NU                                         | Stores target's GUID at the field given in the instance script                                                                                                                                              |
| 36  | ACTION\_T\_UPDATE\_TEMPLATE              | [CreatureEntry](creature_template#entry)                         | Faction                                                            | NU                                         | This function temporarily changes creature entry to new entry, display is changed, loot is changed, but AI is not changed. At respawn creature will be reverted to original entry. Alliance(0) or Horde (1) |
| 37  | ACTION\_T\_DIE                           | NU                                                               | NU                                                                 | NU                                         | Kills the creature                                                                                                                                                                                          |
| 38  | ACTION\_T\_ZONE\_COMBAT\_PULSE           | NU                                                               | NU                                                                 | NU                                         | Places all players within the instance into combat with the creature. Only works in combat and only works inside of instances                                                                               |
| 39  | ACTION\_T\_CALL\_FOR\_HELP               | Radius                                                           | NU                                                                 | NU                                         | Call any friendly creatures (if its not in combat/etc) in radius attack creature target                                                                                                                     |
| 40  | ACTION\_T\_SET\_SHEATH                   | [SheathState](creature_ai_scripts#SheathState)                   | NU                                                                 | NU                                         | Set SheathState for creature (0-no weapon show (not used mostly by creatures), 1-melee weapon show, 2-ranged weapon show)                                                                                   |
| 41  | ACTION\_T\_FORCE\_DESPAWN                | msDelay                                                          | NU                                                                 | NU                                         | Despawns the creature, If 0 despawn instant, other despawn after delay (in ms)                                                                                                                              |
| 42  | ACTION\_T\_SET\_INVINCIBILITY\_HP\_LEVEL | Value                                                            | HP\_Level(0) or HP\_Percent(1)                                     | NU                                         | Set minimum health level for creature that can be set at damage as flat value or percent from max health                                                                                                    |
| 43  | ACTION\_T\_MOUNT\_TO\_ENTRY\_OR\_MODEL   | [CreatureEntry](creature_template#entry)                         | [modelId](creature_template#modelId1)                              | NU                                         | [modelId](creature_template#creature_template#modelId1) (param2) or 0 for both to dismount                                                                                                                  |
| 44  | ACTION\_T\_CHANCED\_TEXT                 | Chance                                                           | -TextId1                                                           | -TextId2                                   | deprecated, use 54! Chance to display the text, TextId1, optionally TextId2. If more than just -TextId1 is defined, randomize. Negative values                                                              |
| 45  | ACTION\_T\_THROW\_AI\_EVENT              | [AIEventType](creature_ai_scripts#AIEventType)                   | Radius                                                             | [target](creature_ai_scripts#Target)       | Throws an [AIEventType](creature_ai_scripts#AIEventType) (Param1) to friendly Npcs in range (Param2), Invoker of event is Target                                                                            |
| 46  | ACTION\_T\_SET\_THROW\_MASK              | EventTypeMask                                                    | NU                                                                 | NU                                         | Marks for which AIEvents the npc will throw AIEvents on its own.                                                                                                                                            |
| 47  | ACTION\_T\_SET\_STAND\_STATE             | [UnitStandStateType](creature_template_addon#UnitStandStateType) | NU                                                                 | NU                                         | Set the UnitStandStateType (Param1) of the current creature                                                                                                                                                 |
| 48  | ACTION\_T\_CHANGE\_MOVEMENT              | [MovementType](creature#MovementType)                            | spawndist/PathId                                                   | NU                                         | Change the creature MovementGeneratorType (Param1). If the movement type is Random Movement (1), the spawndist (Param2) must be provided. If the movement type is Waypoint Movement (2), (Param2) is PathId |
| 49  | ACTION\_T\_DYNAMIC\_MOVEMENT             | Off(0)On(1)                                                      | NU                                                                 | NU                                         | Disable / Enable dynamic movement behavior                                                                                                                                                                  |
| 50  | ACTION\_T\_SET\_REACT\_STATE             | [ReactStates](creature_ai_scripts#ReactStates)                   | NU                                                                 | NU                                         | Change ReactState of the creature                                                                                                                                                                           |
| 51  | ACTION\_T\_PAUSE\_WAYPOINTS              | DoPause(0)UnPause(1)                                             | NU                                                                 | NU                                         | Pause waypoints of creature, DoPause 0: unpause waypoint 1                                                                                                                                                  |
| 52  | ACTION\_T\_INTERRUPT\_SPELL              | [CurrentSpellTypes](creature_ai_scripts#CurrentSpellTypes)       | NU                                                                 | NU                                         | Interrupt spell in given slot for creature                                                                                                                                                                  |
| 53  | ACTION\_T\_START\_RELAY\_SCRIPT          | RelayIDorTemplate                                                | [target](creature_ai_scripts#Target)                               | NU                                         | Launches dbscripts\_on\_relay script, either static one, or when (Param1) is < 0 then random one chosen from dbscript\_random\_templates                                                                    |
| 54  | ACTION\_T\_TEXT\_NEW                     | -TextId                                                          | Target                                                             | TemplateId                                 | Displays text, either static one or when (Param3) != 0, then random one chosen from dbscript\_random\_templates                                                                                             |
| 55  | ACTION\_T\_ATTACK\_START                 | Target                                                           | NU                                                                 | NU                                         | Starts attacking Target                                                                                                                                                                                     |
| 56  | ACTION\_T\_DESPAWN\_GUARDIANS            | [CreatureEntry](creature_template#entry)                         | NU                                                                 | NU                                         | Despawns guardian with specified entry, or if 0 despawns all guardians                                                                                                                                      |
| 57  | ACTION\_T\_SET\_RANGED\_MODE             | [RangeModeType](creature_ai_scripts#RangeModeType)               | chaseDistance                                                      | NU                                         | Enable [RangeModeType](creature_ai_scripts#RangeModeType), distance to chase at, NU                                                                                                                         |
| 58  | ACTION\_T\_SET\_WALK                     | WalkSettingType                                                  | NU                                                                 | NU                                         | RUN\_DEFAULT (0), WALK\_DEFAULT (1), RUN\_CHASE (2), WALK\_CHASE (3)                                                                                                                                        |
| 59  | ACTION\_T\_SET\_FACING                   | [target](creature_ai_scripts#Target)                             | Set (0), Reset (1)                                                 | NU                                         | Sets facing, i.e. orientation to target, or resets it to last waypoint hit, or to respawn position                                                                                                          |

#### EventFlags

| Bit  | Name                             | Description                                                                |
| ---- | -------------------------------- | -------------------------------------------------------------------------- |
| 1    | EFLAG_REPEATABLE                 | Event repeats (Does not repeat if this flag is not set)                    |
| 2    | EFLAG_NORMAL, EFLAG_DIFFICULTY_0 | Event only occurs in Normal instance difficulty + [wotlk: (10-Man Normal)] |
| 4    | EFLAG_HEROIC, EFLAG_DIFFICULTY_1 | Event only occurs in Heroic instance difficulty + [wotlk: (25-Man Normal)] |
| 8    | EFLAG_DIFFICULTY_2               | Event only occurs in [wotlk: (10-Man Heroic)]                              |
| 16   | EFLAG_DIFFICULTY_3               | Event only occurs in [wotlk (25-Man Heroic)]                               |
| 32   | EFLAG_RANDOM_ACTION              | Random use action1, 2, or 3                                                |
| 64   | EFLAG_RESERVED_6                 | Reserved                                                                   |
| 128  | EFLAG_DEBUG_ONLY                 | Event only occurs in debug build                                           |
| 256  | EFLAG_RANGED_MODE_ONLY           | Event only occurs in ranged mode                                           |
| 512  | EFLAG_MELEE_MODE_ONLY            | Event only occurs in melee mode                                            |
| 1024 | EFLAG_COMBAT_ACTION              | Only one per cycle                                                         |

#### Target

| ID  | Name                                   | Description                                                                                                                                                                                        |
| --- | -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0   | TARGET_T_SELF                          | Targets itself                                                                                                                                                                                     |
| 1   | TARGET_T_HOSTILE                       | Targets the current victim (usually the one with the most threat)                                                                                                                                  |
| 2   | TARGET_T_HOSTILE_SECOND_AGGRO          | Targets the unit with the second most threat in the threat list                                                                                                                                    |
| 3   | TARGET_T_HOSTILE_LAST_AGGRO            | Targets the unit with the least threat in the threat list                                                                                                                                          |
| 4   | TARGET_T_HOSTILE_RANDOM                | Targets a random unit from the threat list                                                                                                                                                         |
| 5   | TARGET_T_HOSTILE_RANDOM_NOT_TOP        | Targets a random unit from the threat list excluding the one with the most threat                                                                                                                  |
| 6   | TARGET_T_ACTION_INVOKER                | Targets the unit that caused the event; only for certain events only.                                                                                                                              |
| 7   | TARGET_T_ACTION_INVOKER_OWNER          | Targets unit who is responsible for Event to occur (only works for EVENT_T_AGGRO, EVENT_T_KILL, EVENT_T_DEATH, EVENT_T_SPELLHIT, EVENT_T_OOC_LOS, EVENT_T_RECEIVE_EMOTE, EVENT_T_RECEIVE_AI_EVENT) |
| 8   | TARGET_T_HOSTILE_RANDOM_PLAYER         | Targets Random Player on The Threat List                                                                                                                                                           |
| 9   | TARGET_T_HOSTILE_RANDOM_NOT_TOP_PLAYER | Targets Any Random Player Except Top Threat                                                                                                                                                        |
| 10  | TARGET_T_EVENT_SENDER                  | Creature who sent a received AIEvent - only triggered by EVENT_T_RECEIVE_AI_EVENT                                                                                                                  |
| 11  | TARGET_T_SPAWNER                       | Owner of unit if exists                                                                                                                                                                            |
| 12  | TARGET_T_EVENT_SPECIFIC                | Filled by specific event (works for EVENT_T_FRIENDLY_HP, EVENT_T_FRIENDLY_IS_CC, EVENT_T_FRIENDLY_MISSING_BUFF)                                                                                    |
| 13  | TARGET_T_PLAYER_INVOKER                | Player who initiated hostile contact with this npc                                                                                                                                                 |
| 14  | TARGET_T_PLAYER_TAPPED                 | Player who currently holds to score the kill credit from the npc                                                                                                                                   |
| 15  | TARGET_T_NONE                          | Default spell target - sets nullptr which should be most common spell fill                                                                                                                         |
| 16  | TARGET_T_HOSTILE_RANDOM_MANA           | Random target with mana                                                                                                                                                                            |
| 17  | TARGET_T_NEAREST_AOE_TARGET            | Checks for available near aoe targets by EffectRadiusIndex[0] for the spell used                                                                                                                   |
| 18  | TARGET_T_HOSTILE_FARTHEST_AWAY         | Farthest away target, excluding melee range                                                                                                                                                        |

#### castFlags

| Bit  | Name                            | Description                                                                                                |
| ---- | ------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| 1    | CAST_INTERRUPT_PREVIOUS         | Interrupts any previous spell casting.                                                                     |
| 2    | CAST_TRIGGERED                  | Forces the cast to be instant and ignores any mana/reagents requirements.                                  |
| 4    | CAST_FORCE_CAST                 | Forces spell to cast even if the target is possibly out of range or the creature is possibly out of mana   |
| 8    | CAST_NO_MELEE_IF_OOM            | Prevents creature from entering melee if out of mana or out of range                                       |
| 16   | CAST_FORCE_TARGET_SELF          | Forces the target to cast this spell on itself                                                             |
| 32   | CAST_AURA_NOT_PRESENT           | Only casts the spell on the target if the target does not have the aura from that spell on itself already. |
| 64   | CAST_IGNORE_UNSELECTABLE_TARGET | Can target UNIT_FLAG_NOT_SELECTABLE - Needed in some scripts                                               |
| 128  | CAST_SWITCH_CASTER_TARGET       | Switches target and caster for spell cast                                                                  |
| 256  | CAST_MAIN_SPELL                 | Marks main spell for AI Type = Action 57 ACTION_T_SET_RANGED_MODE                                          |
| 512  | CAST_PLAYER_ONLY                | Selects only player targets - substitution for EAI not having more params                                  |
| 1024 | CAST_DISTANCE_YOURSELF          | If spell with this cast flag hits main aggro target, caster distances himself - EAI only                   |

#### schoolMask

| Value | Type                                      |
| ----- | ----------------------------------------- |
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
| ----- | -------------------- |
| 0     | DISPEL\_NONE         |
| 1     | DISPEL\_MAGIC        |
| 2     | DISPEL\_CURSE        |
| 3     | DISPEL\_DISEASE      |
| 4     | DISPEL\_POISON       |
| 5     | DISPEL\_STEALTH      |
| 6     | DISPEL\_INVISIBILITY |
| 7     | DISPEL\_ALL          |

#### AIEventType

| Value | Type                      | Sender                       | Invoker                                          |
| ----- | ------------------------- | ---------------------------- | ------------------------------------------------ |
| 0     | AI_EVENT_JUST_DIED        | Killed Npc                   | Killer                                           |
| 1     | AI_EVENT_CRITICAL_HEALTH  | Hurt Npc                     | DamageDealer - Expected to be sent by 10% health |
| 2     | AI_EVENT_LOST_HEALTH      | Hurt Npc                     | DamageDealer - Expected to be sent by 50% health |
| 3     | AI_EVENT_LOST_SOME_HEALTH | Hurt Npc                     | DamageDealer - Expected to be sent by 90% health |
| 4     | AI_EVENT_GOT_FULL_HEALTH  | Healed Npc                   | Healer                                           |
| 5     | AI_EVENT_CUSTOM_EVENTAI_A | Npc that throws custom event | TARGET_T_ACTION_INVOKER (if exists)              |
| 6     | AI_EVENT_CUSTOM_EVENTAI_B | Npc that throws custom event | TARGET_T_ACTION_INVOKER (if exists)              |
| 7     | AI_EVENT_GOT_CCED         | CCed Npc                     | Caster that CCed                                 |
| 8     | AI_EVENT_CUSTOM_EVENTAI_C | Npc that throws custom event | TARGET_T_ACTION_INVOKER (if exists)              |
| 9     | AI_EVENT_CUSTOM_EVENTAI_D | Npc that throws custom event | TARGET_T_ACTION_INVOKER (if exists)              |
| 10    | AI_EVENT_CUSTOM_EVENTAI_E | Npc that throws custom event | TARGET_T_ACTION_INVOKER (if exists)              |
| 11    | AI_EVENT_CUSTOM_EVENTAI_F | Npc that throws custom event | TARGET_T_ACTION_INVOKER (if exists)              |

#### TemporaryFactionFlags

| Bit | Hex  | Type                                | Description                                                                                                                                                        |
| --- | ---- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 0   | 0x00 | TEMPFACTION_NONE                    | When no flag is used in temporary faction change, faction will be persistent. It will then require manual change back to default/another faction when changed once |
| 1   | 0x01 | TEMPFACTION_RESTORE_RESPAWN         | Default faction will be restored at respawn                                                                                                                        |
| 2   | 0x02 | TEMPFACTION_RESTORE_COMBAT_STOP     | at CombatStop() (happens at creature death, at evade or custom scripte among others)                                                                               |
| 4   | 0x04 | TEMPFACTION_RESTORE_REACH_HOME      | at reaching home in home movement (evade), if not already done at CombatStop()                                                                                     |
| 8   | 0x08 | TEMPFACTION_TOGGLE_NON_ATTACKABLE   | Remove UNIT_FLAG_NON_ATTACKABLE(0x02) when faction is changed (reapply when temp-faction is removed)                                                               |
| 16  | 0x10 | TEMPFACTION_TOGGLE_IMMUNE_TO_PLAYER | Remove UNIT_FLAG_IMMUNE_TO_PLAYER(0x100) when faction is changed (reapply when temp-faction is removed)                                                            |
| 32  | 0x20 | TEMPFACTION_TOGGLE_IMMUNE_TO_NPC    | Remove UNIT_FLAG_PASSIVE(0x200) when faction is changed (reapply when temp-faction is removed)                                                                     |
| 64  | 0x40 | TEMPFACTION_TOGGLE_PACIFIED         | Remove UNIT_FLAG_PACIFIED(0x20000) when faction is changed (reapply when temp-faction is removed)                                                                  |
| 128 | 0x80 | TEMPFACTION_TOGGLE_NOT_SELECTABLE   | Remove UNIT_FLAG_NOT_SELECTABLE(0x2000000) when faction is changed (reapply when temp-faction is removed)                                                          |

#### EUnitFields

| Value | Type                        | Description      |
| ----- | --------------------------- | ---------------- |
| 22    | UNIT\_FIELD\_HEALTH         | Health           |
| 24    | UNIT\_FIELD\_POWER2         | Mana             |
| 34    | UNIT\_FIELD\_LEVEL          | Level            |
| 150   | UNIT\_FIELD\_BOUNDINGRADIUS | bounding\_radius |
| 151   | UNIT\_FIELD\_COMBATREACH    | combat\_reach    |
| 164   | UNIT\_DYNAMIC\_FLAGS        | DynamicFlags     |
| 168   | UNIT\_NPC\_FLAGS            | NpcFlags         |

#### ReactStates

| Value | Type              | Description                                      |
| ----- | ----------------- | ------------------------------------------------ |
| 0     | REACT\_PASSIVE    | Wont attack on its own, maybe due to CallForHelp |
| 1     | REACT\_DEFENSIVE  | Will attack when attacked                        |
| 2     | REACT\_AGGRESSIVE | Will attack (default)                            |

#### CurrentSpellTypes

| Value | Type                       | Description |
| ----- | -------------------------- | ----------- |
| 0     | CURRENT\_MELEE\_SPELL      |             |
| 1     | CURRENT\_GENERIC\_SPELL    |             |
| 2     | CURRENT\_AUTOREPEAT\_SPELL |             |
| 3     | CURRENT\_CHANNELED\_SPELL  |             |

#### Instance\_Data\_Flags

| Value | Type    | Description                                             |
| ----- | ------- | ------------------------------------------------------- |
| 1     | Aggro   | Creature SetInCombat                                    |
| 2     | Evade   | Creature remove from Combat                             |
| 3     | Death   | Creature just die                                       |
| 4     | Special | Need for more as one enemy in a fight (like 4 horseman) |

#### RangeModeType

| Value | Type               | Description                 |
| ----- | ------------------ | --------------------------- |
| 0     | TYPE\_NONE         | Melee Mode                  |
| 1     | TYPE\_FULL\_CASTER | Caster Mode                 |
| 2     | TYPE\_PROXIMITY    | Hunter Mode(keeps distance) |

#### SheathState

b2\_0\_sheath

| Bit | Name                   | Comment                     |
| --- | ---------------------- | --------------------------- |
| 0   | SHEATH\_STATE\_UNARMED | all weapons sheathed        |
| 1   | SHEATH\_STATE\_MELEE   | melee weapon(s) unsheathed  |
| 2   | SHEATH\_STATE\_RANGED  | ranged weapon(s) unsheathed |

#### UnitStandStateType

bytes1

| Bit | Name                              | Comment                                                             |
| --- | --------------------------------- | ------------------------------------------------------------------- |
| 0   | UNIT_STAND_STATE_STAND            | normal behavior                                                     |
| 1   | UNIT_STAND_STATE_SIT              | sitting on ground                                                   |
| 2   | UNIT_STAND_STATE_SIT_CHAIR        | sitting on normal chair                                             |
| 3   | UNIT_STAND_STATE_SLEEP            | sleeping                                                            |
| 4   | UNIT_STAND_STATE_SIT_LOW_CHAIR    | sitting on low chair                                                |
| 5   | UNIT_STAND_STATE_SIT_MEDIUM_CHAIR | sitting on medium chair                                             |
| 6   | UNIT_STAND_STATE_SIT_HIGH_CHAIR   | sitting on high chair                                               |
| 7   | UNIT_STAND_STATE_DEAD             | play dead                                                           |
| 8   | UNIT_STAND_STATE_KNEEL            | kneel                                                               |
| 9   | UNIT_STAND_STATE_CUSTOM           | Depends on model animation. Submerge, freeze, hide, hibernate, rest |

#### event\_inverse\_phase\_mask

#### Ranged mode - reference usage

('58902','589','11','0','100','0','0','0','0','0','0','0','57','1','35','0','0','0','0','0','0','0','0','0','Defias Pillager - Enable Caster Mode on Spawn'),
('58905','589','0','0','100','1025','0','0','3400','4900','0','0','11','20793','1','256','0','0','0','0','0','0','0','0','Defias Pillager - Cast Fireball'),

The ranged mode was designed to be toggled on spawn, but can effectively by toggled on phase change on other condition when needed. It automatically reverts itself on evade. It works in connection with its modes, and automatically changes chase distance. A main casting spell, which is supposed to be lowest in priority (highest ID), needs to use 256 cast flag. This notes that when this spell returns OOM error, ranged mode automatically adjusts its behaviour. Ranged mode also responds to kicks and silence on this spell. Last notable feature with ranged mode is distancing, which only occurs if cast flag 1024 is set, and when creature is in melee mode, and the target is hit, creature runs away from main aggro targets melee reach.
