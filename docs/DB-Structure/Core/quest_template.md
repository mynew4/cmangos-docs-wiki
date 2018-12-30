Back to [world database](mangosdb_struct) list of tables.

The \`quest\_template\` table
-----------------------------

contains all basic definitions of quests available.

### Structure

| **Field**                                                      | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry](Quest_template#entry)                                  | int(10) unsigned      | NO       | PRI     | 0           |           |
| [Method](Quest_template#method)                                | tinyint(3)            | NO       |         | 2           |           |
| [ZoneOrSort](Quest_template#zoneorsort)                        | smallint(6)           | NO       |         | 0           |           |
| [MinLevel](Quest_template#minlevel)                            | tinyint(3) unsigned   | NO       |         | 0           |           |
| [QuestLevel](Quest_template#questlevel)                        | tinyint(3) unsigned   | NO       |         | 0           |           |
| [Type](Quest_template#type)                                    | smallint(5) unsigned  | NO       |         | 0           |           |
| [RequiredClasses](Quest_template#requiredclasses)              | smallint(5)           | NO       |         | 0           |           |
| [RequiredRaces](Quest_template#requiredraces)                  | smallint(5)           | NO       |         | 0           |           |
| [RequiredSkill](Quest_template#requiredskill)                  | smallint(5)           | NO       |         | 0           |           |
| [RequiredSkillValue](Quest_template#requiredskillvalue)        | smallint(5) unsigned  | NO       |         | 0           |           |
| [RequiredCondition](Quest_template#RequiredCondition)          | smallint(5) unsigned  | NO       |         | 0           |           |
| [RepObjectiveFaction](Quest_template#repobjectivefaction)      | smallint(5) unsigned  | NO       |         | 0           |           |
| [RepObjectiveValue](Quest_template#repobjectivevalue)          | mediumint(9)          | NO       |         | 0           |           |
| [RequiredMinRepFaction](Quest_template#requiredminrepfaction)  | mediumint(5) unsigned | NO       |         | 0           |           |
| [RequiredMinRepValue](Quest_template#requiredminrepvalue)      | mediumint(9)          | NO       |         | 0           |           |
| [RequiredMaxRepFaction](Quest_template#requiredmaxrepfaction)  | mediumint(5) unsigned | NO       |         | 0           |           |
| [RequiredMaxRepValue](Quest_template#requiredmaxrepvalue)      | mediumint(9)          | NO       |         | 0           |           |
| [SuggestedPlayers](Quest_template#suggestedplayers)            | mediumint(3) unsigned | NO       |         | 0           |           |
| [LimitTime](Quest_template#limittime)                          | int(10)               | NO       |         | 0           |           |
| [QuestFlags](Quest_template#questflags)                        | smallint(5) unsigned  | NO       |         | 0           |           |
| [SpecialFlags](Quest_template#specialflags)                    | tinyint(3) unsigned   | NO       |         | 0           |           |
| [CharTitleId](Quest_template#chartitleid)                      | tinyint(3) unsigned   | NO       |         | 0           |           |
| [PlayersSlain](Quest_template#playersslain)                    | tinyint(3) unsigned   | NO       |         | 0           | WOTLK     |
| [BonusTalents](Quest_template#bonustalents)                    | tinyint(3) unsigned   | NO       |         | 0           | WOTLK     |
| [PrevQuestId](Quest_template#prevquestid)                      | mediumint(9)          | NO       |         | 0           |           |
| [NextQuestId](Quest_template#nextquestid)                      | mediumint(9)          | NO       |         | 0           |           |
| [ExclusiveGroup](Quest_template#exclusivegroup)                | mediumint(9)          | NO       |         | 0           |           |
| [NextQuestInChain](Quest_template#nextquestinchain)            | mediumint(8)          | NO       |         | 0           |           |
| [RewXPId](Quest_template#rewxpid)                              | tinyint(3) unsigned   | NO       |         | 0           | WOTLK     |
| [SrcItemId](Quest_template#srcitemid)                          | mediumint(8) unsigned | NO       |         | 0           |           |
| [SrcItemCount](Quest_template#srcitemcount)                    | tinyint(3)            | NO       |         | 0           |           |
| [SrcSpell](Quest_template#srcspell)                            | mediumint(8)          | NO       |         | 0           |           |
| [Title](Quest_template#title)                                  | text                  | YES      |         |             |           |
| [Details](Quest_template#details)                              | text                  | YES      |         |             |           |
| [Objectives](Quest_template#objectives)                        | text                  | YES      |         |             |           |
| [OfferRewardText](Quest_template#offerrewardtext)              | text                  | YES      |         |             |           |
| [RequestItemsText](Quest_template#requestitemstext)            | text                  | YES      |         |             |           |
| [EndText](Quest_template#endtext)                              | text                  | YES      |         |             |           |
| [ObjectiveText1](Quest_template#objectivetext)                 | text                  | YES      |         |             |           |
| [ObjectiveText2](Quest_template#objectivetext)                 | text                  | YES      |         |             |           |
| [ObjectiveText3](Quest_template#objectivetext)                 | text                  | YES      |         |             |           |
| [ObjectiveText4](Quest_template#objectivetext)                 | text                  | YES      |         |             |           |
| [ReqItemId1](Quest_template#reqitemid)                         | mediumint(8) unsigned | NO       |         | 0           |           |
| [ReqItemId2](Quest_template#reqitemid)                         | mediumint(8) unsigned | NO       |         | 0           |           |
| [ReqItemId3](Quest_template#reqitemid)                         | mediumint(8) unsigned | NO       |         | 0           |           |
| [ReqItemId4](Quest_template#reqitemid)                         | mediumint(8) unsigned | NO       |         | 0           |           |
| [ReqItemCount1](Quest_template#reqitemcount)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [ReqItemCount2](Quest_template#reqitemcount)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [ReqItemCount3](Quest_template#reqitemcount)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [ReqItemCount4](Quest_template#reqitemcount)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [ReqSourceId1](Quest_template#reqsourceid)                     | mediumint(8)          | NO       |         | 0           |           |
| [ReqSourceId2](Quest_template#reqsourceid)                     | mediumint(8)          | NO       |         | 0           |           |
| [ReqSourceId3](Quest_template#reqsourceid)                     | mediumint(8)          | NO       |         | 0           |           |
| [ReqSourceId4](Quest_template#reqsourceid)                     | mediumint(8)          | NO       |         | 0           |           |
| [ReqSourceCount1](Quest_template#reqsourcecount)               | smallint(5)           | NO       |         | 0           |           |
| [ReqSourceCount2](Quest_template#reqsourcecount)               | smallint(5)           | NO       |         | 0           |           |
| [ReqSourceCount3](Quest_template#reqsourcecount)               | smallint(5)           | NO       |         | 0           |           |
| [ReqSourceCount4](Quest_template#reqsourcecount)               | smallint(5)           | NO       |         | 0           |           |
| [ReqCreatureOrGOId1](Quest_template#reqcreatureorgoid)         | mediumint(9)          | NO       |         | 0           |           |
| [ReqCreatureOrGOId2](Quest_template#reqcreatureorgoid)         | mediumint(9)          | NO       |         | 0           |           |
| [ReqCreatureOrGOId3](Quest_template#reqcreatureorgoid)         | mediumint(9)          | NO       |         | 0           |           |
| [ReqCreatureOrGOId4](Quest_template#reqcreatureorgoid)         | mediumint(9)          | NO       |         | 0           |           |
| [ReqCreatureOrGOCount1](Quest_template#reqcreatureorgocount)   | int(10) unsigned      | NO       |         | 0           |           |
| [ReqCreatureOrGOCount2](Quest_template#reqcreatureorgocount)   | smallint(5) unsigned  | NO       |         | 0           |           |
| [ReqCreatureOrGOCount3](Quest_template#reqcreatureorgocount)   | smallint(5) unsigned  | NO       |         | 0           |           |
| [ReqCreatureOrGOCount4](Quest_template#reqcreatureorgocount)   | smallint(5) unsigned  | NO       |         | 0           |           |
| [ReqSpellCast1](Quest_template#reqspellcast)                   | mediumint(8) unsigned | NO       |         | 0           |           |
| [ReqSpellCast2](Quest_template#reqspellcast)                   | mediumint(8)          | NO       |         | 0           |           |
| [ReqSpellCast3](Quest_template#reqspellcast)                   | mediumint(8)          | NO       |         | 0           |           |
| [ReqSpellCast4](Quest_template#reqspellcast)                   | mediumint(8)          | NO       |         | 0           |           |
| [RewChoiceItemId1](Quest_template#rewchoiceitemid)             | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewChoiceItemId2](Quest_template#rewchoiceitemid)             | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewChoiceItemId3](Quest_template#rewchoiceitemid)             | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewChoiceItemId4](Quest_template#rewchoiceitemid)             | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewChoiceItemId5](Quest_template#rewchoiceitemid)             | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewChoiceItemId6](Quest_template#rewchoiceitemid)             | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewChoiceItemCount1](Quest_template#rewchoiceitemcount)       | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewChoiceItemCount2](Quest_template#rewchoiceitemcount)       | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewChoiceItemCount3](Quest_template#rewchoiceitemcount)       | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewChoiceItemCount4](Quest_template#rewchoiceitemcount)       | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewChoiceItemCount5](Quest_template#rewchoiceitemcount)       | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewChoiceItemCount6](Quest_template#rewchoiceitemcount)       | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewItemId1](Quest_template#rewitemid)                         | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewItemId2](Quest_template#rewitemid)                         | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewItemId3](Quest_template#rewitemid)                         | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewItemId4](Quest_template#rewitemid)                         | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewItemCount1](Quest_template#rewitemcount)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewItemCount2](Quest_template#rewitemcount)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewItemCount3](Quest_template#rewitemcount)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewItemCount4](Quest_template#rewitemcount)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [RewRepFaction1](Quest_template#rewrepfaction)                 | smallint(5)           | NO       |         | 0           |           |
| [RewRepFaction2](Quest_template#rewrepfaction)                 | smallint(5)           | NO       |         | 0           |           |
| [RewRepFaction3](Quest_template#rewrepfaction)                 | smallint(5)           | NO       |         | 0           |           |
| [RewRepFaction4](Quest_template#rewrepfaction)                 | smallint(5)           | NO       |         | 0           |           |
| [RewRepFaction5](Quest_template#rewrepfaction)                 | smallint(5)           | NO       |         | 0           |           |
| [RewRepValue1](Quest_template#rewrepvalue)                     | mediumint(9)          | NO       |         | 0           |           |
| [RewRepValue2](Quest_template#rewrepvalue)                     | mediumint(9)          | NO       |         | 0           |           |
| [RewRepValue3](Quest_template#rewrepvalue)                     | mediumint(9)          | NO       |         | 0           |           |
| [RewRepValue4](Quest_template#rewrepvalue)                     | mediumint(9)          | NO       |         | 0           |           |
| [RewRepValue5](Quest_template#rewrepvalue)                     | mediumint(9)          | NO       |         | 0           |           |
| [RewHonorableKills](Quest_template#rewhonorablekills)          | int(11)               | NO       |         | 0           |           |
| [RewOrReqMoney](Quest_template#reworreqmoney)                  | int(11)               | NO       |         | 0           |           |
| [RewMoneyMaxLevel](Quest_template#rewmoneymaxlevel)            | int(10) unsigned      | NO       |         | 0           |           |
| [RewSpell](Quest_template#rewspell)                            | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewSpellCast](Quest_template#rewspellcast)                    | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewMailTemplateId](Quest_template#rewmailtemplateid)          | mediumint(8) unsigned | NO       |         | 0           |           |
| [RewMailDelaySecs](Quest_template#rewmaildelaysecs)            | int(11) unsigned      | NO       |         | 0           |           |
| [PointMapId](Quest_template#pointmapid)                        | smallint(5) unsigned  | NO       |         | 0           |           |
| [PointX](Quest_template#pointx)                                | float                 | NO       |         | 0           |           |
| [PointY](Quest_template#pointy)                                | float                 | NO       |         | 0           |           |
| [PointOpt](Quest_template#pointopt)                            | mediumint(8)          | NO       |         |             |           |
| [DetailsEmote1](Quest_template#detailsemote)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [DetailsEmote2](Quest_template#detailsemote)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [DetailsEmote3](Quest_template#detailsemote)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [DetailsEmote4](Quest_template#detailsemote)                   | smallint(5) unsigned  | NO       |         | 0           |           |
| [DetailsEmoteDelay1](Quest_template#DetailsEmoteDelay)         | smallint(5) unsigned  | NO       |         | 0           |           |
| [DetailsEmoteDelay2](Quest_template#DetailsEmoteDelay)         | smallint(5) unsigned  | NO       |         | 0           |           |
| [DetailsEmoteDelay3](Quest_template#DetailsEmoteDelay)         | smallint(5) unsigned  | NO       |         | 0           |           |
| [DetailsEmoteDelay4](Quest_template#DetailsEmoteDelay)         | smallint(5) unsigned  | NO       |         | 0           |           |
| [IncompleteEmote](Quest_template#incompleteemote)              | smallint(5) unsigned  | NO       |         | 0           |           |
| [CompleteEmote](Quest_template#completeemote)                  | smallint(5) unsigned  | NO       |         | 0           |           |
| [OfferRewardEmote1](Quest_template#offerrewardemote)           | smallint(5) unsigned  | NO       |         | 0           |           |
| [OfferRewardEmote2](Quest_template#offerrewardemote)           | smallint(5) unsigned  | NO       |         | 0           |           |
| [OfferRewardEmote3](Quest_template#offerrewardemote)           | smallint(5) unsigned  | NO       |         | 0           |           |
| [OfferRewardEmote4](Quest_template#offerrewardemote)           | smallint(5) unsigned  | NO       |         | 0           |           |
| [OfferRewardEmoteDelay1](Quest_template#OfferRewardEmoteDelay) | smallint(5) unsigned  | NO       |         | 0           |           |
| [OfferRewardEmoteDelay2](Quest_template#OfferRewardEmoteDelay) | smallint(5) unsigned  | NO       |         | 0           |           |
| [OfferRewardEmoteDelay3](Quest_template#OfferRewardEmoteDelay) | smallint(5) unsigned  | NO       |         | 0           |           |
| [OfferRewardEmoteDelay4](Quest_template#OfferRewardEmoteDelay) | smallint(5) unsigned  | NO       |         | 0           |           |
| [StartScript](Quest_template#startscript)                      | mediumint(8) unsigned | NO       |         | 0           |           |
| [CompleteScript](Quest_template#completescript)                | mediumint(8) unsigned | NO       |         | 0           |           |

#### entry

Quest Id. Quest ID is the Primary Key for the Table. Each Quest ID must be unique!

#### Method

Accepted values: 0, 1 or 2. If **value = 0** then Quest is autocompleted (skip objectives/details).

#### ZoneOrSort

This field defines under what category the quest falls in the quest log.

If **value > 0** then value is Zone IDs taken from [AreaTable.dbc.](AreaTable.dbc).

if **value < 0** then (**-value**) is quest sort id: (in general profession or class quests. Also see [RequiredSkillValue](quest_template#RequiredSkillValue)) Value is ID from QuestSort.dbc. [QuestSort.dbc](QuestSort.dbc)

#### RequiredSkill

This field defines any specific skill requirements for the quest to be available for a character.

If **value > 0** then value is a skill ID (see SkillLine.dbc)

#### MinLevel

Minimum level required to get the quest.

#### QuestLevel

Level of quest. Player receives full experience amount only if their level is less than or equal to QuestLevel+5.

If QuestLevel = -1, the quest uses current player level as its level.

#### Type

These values are ID taken from QuestInfo.dbc

| ID  | Name        |
|-----|-------------|
| 1   | Group       |
| 21  | Life        |
| 41  | PvP         |
| 62  | Raid        |
| 81  | Dungeon     |
| 82  | World Event |
| 83  | Legendary   |
| 84  | Escort      |
| 85  | Heroic      |

#### RequiredClasses

Class required to get the quest. 0 means available for all classes. Field's value is a decimal value that must be transform to a 8 bits binary in order to be understandable. In binary form, each different bit represent a different class. They're assigned as follow :

### Class

These values are 2^ID taken from [CharClasses.dbc](CharClasses.dbc)

#### RequiredRaces

Races required to get the quest. 0 means available for all races. Field's value is a decimal value that must be transform to a 8 bits binary in order to be understandable. In binary form, each different bit represent a different race. They're assigned as follow :

### Race

These values are 2^ID taken from [CharRaces.dbc](CharRaces.dbc)

NOTE: For Cataclysm Client Goblin=256 and Worgen=2097152

<big>Examples</big>

0,1791 = All Races

690 (2 + 16 + 32 + 128 + 512) = Horde Quest

1101 (1 + 4 + 8 + 64 + 1024) = Alliance Quest

#### RequiredSkillValue

Player skill value requirement for skill if in [ZoneOrSort](quest_template#ZoneOrSort) field < 0 and have some from skill related values.

#### RequiredCondition

#### RepObjectiveFaction

Faction ID for an objective to achieve a certain reputation value with. See [Faction.dbc](Faction.dbc)

#### RepObjectiveValue

Reputation value that the player must achieve with the faction in [RepObjectiveFaction](#RepObjectiveFaction) as part of the quest objectives.

#### RequiredMinRepFaction

Faction ID for reputation requirement. See [Faction.dbc](Faction.dbc)

#### RequiredMinRepValue

Players must have this reputation or higher in order to receive the quest.

#### RequiredMaxRepFaction

The Faction ID for the faction that controls the maximum reputation value that the player can have and still get the quest. See [Faction.dbc](Faction.dbc)

#### RequiredMaxRepValue

The maximum reputation value that the player can have with a faction and still get the quest. If the player has more reputation than the value in this field, the quest will not be able to be taken anymore.

#### SuggestedPlayers

Info about how many players should do unite for the quest.

#### LimitTime

Time in seconds that the player has to complete this quest.

#### QuestFlags

This flag field defines more specifically the type of quest it is. Aside from the daily flag and sharable flag, this field is used just for grouping purposes and NOT for any other quest requirements. The quest requirements are calculated from non-zero values in other quest template fields. Also, while some of these flags are known, others have yet an unknown purpose and the comments below is simply guesswork on them.

At the moment (rev 6055), the core does not actually handle these flags any differently (again, except for the daily flag and the sharable flag).

| Bit  | Name                       | Comments                                                                                                                                                  |
| ---- | -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0    | QUEST_FLAGS_NONE           | No flags, so no groups assigned to this quest.                                                                                                            |
| 1    | QUEST_FLAGS_STAY_ALIVE     | If the player dies, the quest is failed. (?)                                                                                                              |
| 2    | QUEST_FLAGS_EVENT          | Escort quests or any other event-driven quests. If player in party, all players that can accept this quest will receive confirmation box to accept quest. |
| 4    | QUEST_FLAGS_EXPLORATION    | Involves the activation of an areatrigger.                                                                                                                |
| 8    | QUEST_FLAGS_SHARABLE       | Allows the quest to be shared with other players.                                                                                                         |
| 16   | QUEST_FLAGS_NONE2          | Unknown at this time and not used.                                                                                                                        |
| 32   | QUEST_FLAGS_EPIC           | Epic class quests (hunter) (??)                                                                                                                           |
| 64   | QUEST_FLAGS_RAID           | Raid or similiar player group needed for quest.                                                                                                           |
| 128  | QUEST_FLAGS_TBC            | Added with or after TBC.                                                                                                                                  |
| 256  | QUEST_FLAGS_UNK2           | Quest needs extra non-objective items dropped (eg. ReqSourceID fields) (?)                                                                                |
| 512  | QUEST_FLAGS_HIDDEN_REWARDS | Item and monetary rewards are hidden in the initial quest details page and in the quest log but will appear once ready to be rewarded.                    |
| 1024 | QUEST_FLAGS_AUTO_REWARDED  | These quests are automatically rewarded on quest complete.                                                                                                |
| 2048 | QUEST_FLAGS_TBC_RACES      | Blood elf/draenei starting zone quests.                                                                                                                   |
| 4096 | QUEST_FLAGS_DAILY          | Daily repeatable quests (only flag that the core applies specific behavior for)                                                                           |
| 8192 | QUEST_FLAGS_UNK5           | Grizzly Hills PvP daily? Puts PvP-tag on? No idea.)                                                                                                       |

Like all flag based fields, **QuestFlags** can be added for the different types of quest.

#### SpecialFlags

This field is a bitmask and controls only two extra requirements and has only 4 possible values.

-   0: No extra requirements
-   1: Makes the quest repeatable.
-   2: Makes the quest only completable by some external event (an entry in [areatrigger\_involvedrelation,](areatrigger_involvedrelation), spell effect quest complete or an entry in [spell\_scripts](spell_scripts) with command 7 as some examples)
-   3: Both repeatable and completable only through an external event
-   4: Quest resets for player at beginning of month (must be combined with SpecialFlags 1 (repeatable))

#### CharTitleId

The title the character will receive upon completion of the quest. See CharTitles.dbc

#### PlayersSlain

#### BonusTalents

#### PrevQuestId

**If value > 0:** Contains the previous quest id, that must be completed before this quest can be started.

**If value < 0:** Contains the parent quest id, that must be active before this quest can be started.

See the [examples section](#Examples) for examples.

#### NextQuestId

**If value > 0:** Contains the next quest id, if PrevQuestId of that quest is not sufficient.

**If value < 0:** Contains the sub quest id, if PrevQuestId of that quest is not sufficient. If quest have many alternative next quests (class specific quests lead from single not class specific quest) field PrevQuestId in next quests can used for setting this dependence.

See the [examples section](#Examples) for examples.

#### ExclusiveGroup

**If ExclusiveGroup > 0**

Allows to define a group of quests of which only one may be chosen and completed. E.g. if from quests 1200, 1201 and 1202 only one should be allowed to be chosen, insert 1200 into ExclusiveGroup of all 3 quests.

**If ExclusiveGroup < 0**

Allows to define a group of quests of which all must be completed and rewarded to start next quest. E.g. if quest 1000 dependent from one of quests 1200, 1201 and 1202 and all this quests have same negative exclusive group then all this quest must be completed and rewarded before quest 1000 can be started.

See the [examples section](#Examples) for examples.

#### NextQuestInChain

The quest entry from a **creature** or **gameobject** that ends a quest and starts a new one. The result is, that if you end the quest, the new quest instantly appears from the quest giver.

See the [examples section](#Examples) for examples.

#### RewXPId

The reward XP index for [QuestXP.dbc.](QuestXP.dbc).

That DBC file lists 9 different XP amounts (from 0 to 8) for each [QuestLevel](#QuestLevel). This field selects the correct amount among them. As of 3.3.5a, the RewXPId index 0 means no XP for all QuestLevels.

#### SrcItemId

Item's ID given by the quest giver at beginning of the quest. Items will be deleted when quest is abandoned.

#### SrcItemCount

Amount of items given.

#### SrcSpell

Spell casted on player when quest is started. Can be a buff or a learning spell.

#### Title

Title of the quest.

#### Details

The quest text. You can use certain placeholders that will be filled in in-game: - line break, - name, - race, - class, :female; (male and female can be replace with any synonymn you want, but the order must stay the same. IE: boy:girl / man:woman / sir:madam / dude:chick)

#### Objectives

Objectives of the quest. If empty, quest is an auto-complete quest that can be immediately finished without accepting it first.

#### OfferRewardText

First text send to the player by the NPC when completing the quest. You can use certain placeholders that will be filled in in-game: - line break, - name, - race, - class, :female; (male and female can be replace with any synonymn you want, but the order must stay the same. IE: boy:girl / man:woman / sir:madam / dude:chick)

#### RequestItemsText

Text sent to player when the player tries to talk to the NPC with the quest active but incomplete. (The text under the "Progress" title in Wowhead.) You can use certain placeholders that will be filled in in-game: - line break, - name, - race, - class, :female; (male and female can be replace with any synonymn you want, but the order must stay the same. IE: boy:girl / man:woman / sir:madam / dude:chick)

#### EndText

Used only when [SpecialFlags](#SpecialFlags) 2 is active. This is the objective text sent to the player describing the external event that is required to complete the quest.

#### ObjectiveText

Used to define non-standard objective texts, that show up in the questlog. Example, "Heal fallen warrior" and the number gets added by Count values.

#### ReqItemId

Item\_template Id of required item to complete the quest.

#### ReqItemCount

Amount of required items

#### ReqSourceID

Item ID that is needed indirectly by the quest. For example, the quests asks for item X but the only way to get item X is by activating item Y; however, item Y is also a quest item. Therefore you set item Y's ID in this field. This requirement will not appear in the quest text, it is just for the core to know when to drop a quest item that isn't in the ReqItemID field but is still needed by the quest.

#### ReqSourceCount

The maximum number of copies of the item in ReqSourceID that can be picked up (and dropped by the core).
Setting this value to 0 means the item stack size will be the maximum amount that is dropped by core.

#### ReqCreatureOrGOId

**Value > 0:** required creature\_template ID the player needs to kill/cast on in order to complete the quest.

**Value < 0:** required gameobject\_template ID the player needs to cast on in order to complete the quest.

If **ReqSpellCast** is != 0, the objective is to cast on target, else kill.

NOTE: If ReqSpellCast is != 0 and the spell has effects Send Event or Quest Complete, this field may be left empty.

#### ReqCreatureOrGOCount

The number of times the creature or gameobject must be killed or casted upon.

#### ReqSpellCast

Spell ID of Spell that needs to be cast in order to fulfill a quest objective. A spell normally needs a target which is [ReqCreatureOrGOId](quest_template#ReqCreatureOrGOId)

And for spells with "SpellEffect with ImpliciteTargetA-B == 38" check table [Spell\_script\_target](Spell_script_target)

NOTE: If the spell has spell effects Send Event or Quest Complete, it can be entered here WITHOUT the need for a target and count.

#### RewChoiceItemId, RewChoiceItemCount

Id of item available for reward choice.

Number of Charges in rewarded item available.

#### RewItemId, RewItemCount

Number of RewItem

item Id given for reward (no choice).

#### RewRepFaction, RewRepValue

Faction Id (from [Faction.dbc](Faction.dbc)) for which the quest give reputation points.

Number of gain or lost reputation points for Faction at quest completion. This is special reputation rewarding. Normal reputation reward to quest rewarding creature faction calculated and added automatically.

#### RewHonorableKills

Number of honorable kill honor rewarded for completing this quest.

Example: An example value is 15 for quest 8388: At level 70 an honorable kill is 20.9 honor worth. Multiply this with 15 and you receive 313.5, after the multiplication the value is rounded up. So the honor rewarded at level 70 is 314 for this quest.

#### RewOrReqMoney

Money earned by completing the quest (if value > 0). Money quest requirement (if value < 0).

#### RewMoneyMaxLevel

The money a character at level 80 would get when they complete this quest. This field also controls the XP given as the XP is calculated from the value in this field by the following formula. If the quest is repeatable, XP will be given only once. The total XP that a character will receive is also affected by the level difference between the character's level and the quest's level.

The formula for calculating XP from the value in this field:
**QuestLevel >= 65:** XP = RewMoneyMaxLevel / 6.0
**QuestLevel == 64:** XP = RewMoneyMaxLevel / 4.8
**QuestLevel == 63:** XP = RewMoneyMaxLevel / 3.6
**QuestLevel == 62:** XP = RewMoneyMaxLevel / 2.4
**QuestLevel == 61:** XP = RewMoneyMaxLevel / 1.2
**QuestLevel <= 60:** XP = RewMoneyMaxLevel / 0.6

#### RewSpell

Spell that is shown to be casted on quest completion in the quest log. Note that this spell will NOT be casted if [RewSpellCast](#RewSpellCast) is non-zero. The spell in the other field will be casted instead, in which case the spell here only serves as the visual in the quest log.

NOTE: This field comes straight from the WDB and should not be changed.

#### RewSpellCast

Spell that will always be casted at player when completing the quest. This can be learn spell and player learned some spell in result, or buff spell, for example. If this field is non-zero then this spell will ALWAYS be casted and the spell in [RewSpell](#RewSpell) will not.

NOTE: This field comes straight from the WDB and should not be changed.

#### RewMailTemplateId

If the quest gives as a reward an item from a possible list of items, the ID here corresponds to the proper loot template in [mail\_loot\_template.](mail_loot_template). According to the rules in that loot template, items "looted" will be sent by mail at the completion of the quest.

#### RewMailDelaySecs

How many seconds to wait until the mail is sent to the character that turned in a quest rewarding items from a loot template defined in [RewMailTemplateId](#RewMailTemplateId)

#### PointMapId

MapId of a quest point of interest (POI - Point Of Interest). POI will be shown on the map when quest is active.

#### PointX

X coordinate of quest POI.

#### PointY

Y coordinate of quest POI.

#### PointOpt

#### DetailsEmote

Emote(s) played by the related NPC when you view the quest details before clicking the "Accept"-button.
This is found in the SMSG\_QUEST\_GIVER\_QUEST\_DETAILS-packet in sniffs.

#### DetailsEmoteDelay

Delay from the last DetailsEmote before this one is played (in milliseconds)
This is found in the SMSG\_QUEST\_GIVER\_QUEST\_DETAILS-packet in sniffs.

#### IncompleteEmote

Emote played by the related NPC when you view the quest details and one or more quest objective is not yet completed.

#### CompleteEmote

Emote played by the related NPC at the time all quest objects are completed.
This is found in the SMSG\_QUEST\_GIVER\_REQUEST\_ITEMS-packet in sniffs.

#### OfferRewardEmote

Emote played by the NPC at the time the character is rewarded for the quest.
This is found in the SMSG\_QUEST\_GIVER\_OFFER\_REWARD\_MESSAGE-packet in sniffs.

#### OfferRewardEmoteDelay

Delay from the last OfferRewardEmote before this one is played (in milliseconds)
This is found in the SMSG\_QUEST\_GIVER\_OFFER\_REWARD\_MESSAGE-packet in sniffs.

#### StartScript

ID of the start script. See [DBScripts.id](DBScripts#id)

#### CompleteScript

ID of the end script. See [DBScripts.id](DBScripts#id)

Examples
--------

**The "rules of engagement" dealing with quests**

1.  Always use PrevQuestId before using NextQuestId. NextQuestId is considered optional and to be used only when PrevQuestId is not sufficient

**Basic quest**

*Single, stand-alone quest with no prerequisites*

        *questA*

    PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = 0        entry = questA

*When this quest require another quest to be rewarded*

        *questA*

    PrevQuestId = questX   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = 0        entry = questA

**Chain of quests**

*Player get quests in a strict chain that must be completed in a specific order.*

        *questA*
            |
        *questB*
            |
        *questC*
            |
        *questD*

    PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = questB    entry = questA
    PrevQuestId = questA   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = questC    entry = questB
    PrevQuestId = questB   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = questD    entry = questC
    PrevQuestId = questC   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = 0         entry = questD

**Chain of quests with multiple start quests.**

*Player should only be allowed to complete one of three possible*

        *questA*     *questB*    *questC*
            \           |           /
              ------ *questD* -----
                        |
                     *questE*

    PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = questA   NextQuestInChain = questD    entry = questA
    PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = questA   NextQuestInChain = questD    entry = questB
    PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = questA   NextQuestInChain = questD    entry = questC
    PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = questE    entry = questD
    PrevQuestId = questD   NextQuestId = 0        ExclusiveGroup = 0        NextQuestInChain = 0         entry = questE

**Chain of quests with multiple start quests.**

*Player must complete all three initial quests before D becomes available*

        *questA*    *questB*    *questC*
            \          |          /
             ------ *questD* -----
                       |
                    *questE*

    PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questA
    PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questB
    PrevQuestId = 0        NextQuestId = questD   ExclusiveGroup = -questA    NextQuestInChain = questD    entry = questC
    PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0          NextQuestInChain = questE    entry = questD
    PrevQuestId = questD   NextQuestId = 0        ExclusiveGroup = 0          NextQuestInChain = 0         entry = questE

**Quests with split and a child quest**

*Completing A unlocks B and C that can be done at the same time. They both need to be completed before D becomes available. X is needed to obtain item for C and this quest should only be available if C is active*

                    *questA*
                      /    \
              *questB*      *questC* <-> *questX*
                      \    /
                     *questD*

    PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0         NextQuestInChain = 0        entry = questA
    PrevQuestId = questA   NextQuestId = questD   ExclusiveGroup = -questB   NextQuestInChain = 0        entry = questB
    PrevQuestId = questA   NextQuestId = questD   ExclusiveGroup = -questB   NextQuestInChain = 0        entry = questC
    PrevQuestId = -questC  NextQuestId = 0        ExclusiveGroup = 0         NextQuestInChain = 0        entry = questX
    PrevQuestId = 0        NextQuestId = 0        ExclusiveGroup = 0         NextQuestInChain = 0        entry = questD

**Multiple quest chains, leading to one final quest**

*Player may complete (not required to) X, but has to complete all three quest chains before final quest becomes available*

                    *questX*
                       |
        *questA*    *questC*    *questE*
           |           |            |
        *questB*    *questD*    *questF*
           \           |           /
             ------ *questG* -----

    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questC    entry = questX

    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questB    entry = questA
    PrevQuestId = questA   NextQuestId = questG    ExclusiveGroup = -questB    NextQuestInChain = 0         entry = questB
    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questD    entry = questC
    PrevQuestId = questC   NextQuestId = questG    ExclusiveGroup = -questB    NextQuestInChain = 0         entry = questD
    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questF    entry = questE
    PrevQuestId = questE   NextQuestId = questG    ExclusiveGroup = -questB    NextQuestInChain = 0         entry = questF

    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questG

**Complicated**

*Player must first complete A, then B to unlock the chain from C to E. Three other quests in a group will also be unlocked, those can be done at the same time. The three grouped quests must all be completed before I becomes available. Completion of E and I is required to obtain the final quest.*

                    *questA*
                       |
                    *questB*
                  /          \
              *questC*     *questF*    
                 |         *questG*
              *questD*     *questH*
                 |            |
              *questE*     *questI*
                  \          /
                    *questJ*

    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questB    entry = questA
    PrevQuestId = questA   NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questB

    PrevQuestId = questB   NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questD    entry = questC
    PrevQuestId = questC   NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questE    entry = questD
    PrevQuestId = questD   NextQuestId = questJ    ExclusiveGroup = -questE    NextQuestInChain = 0         entry = questE

    PrevQuestId = questB   NextQuestId = questI    ExclusiveGroup = -questF    NextQuestInChain = 0         entry = questF
    PrevQuestId = questB   NextQuestId = questI    ExclusiveGroup = -questF    NextQuestInChain = 0         entry = questG
    PrevQuestId = questB   NextQuestId = questI    ExclusiveGroup = -questF    NextQuestInChain = 0         entry = questH

    PrevQuestId = 0        NextQuestId = questJ    ExclusiveGroup = -questE    NextQuestInChain = 0         entry = questI

    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questJ

**Impossible - many quests may unlock many**

*Player can choose between two alternative chains (Chain A or B, but not both chains). A2 or B2 should unlock C, D and E when complete. When all three complete, F should be unlocked. If player get A3 or B3 after complete F, depends on if chain A or B was chosen.*

                    *questA1*          *questB1*
                        |                  |
                    *questA2*          *questB2*
                        \                 /
                          --- *questC* ---
                              *questD*
                              *questE*
                                 |
                              *questF*
                             /        \
                    *questA3*          *questB3*

    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questA2   entry = questA1
    PrevQuestId = questA1  NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questA2

    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = questB2   entry = questB1
    PrevQuestId = questB1  NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questB2

    PrevQuestId = 0        NextQuestId = questF    ExclusiveGroup = -questC    NextQuestInChain = 0         entry = questC
    PrevQuestId = 0        NextQuestId = questF    ExclusiveGroup = -questC    NextQuestInChain = 0         entry = questD
    PrevQuestId = 0        NextQuestId = questF    ExclusiveGroup = -questC    NextQuestInChain = 0         entry = questE

    PrevQuestId = 0        NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questF

    PrevQuestId = questF   NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questA3
    PrevQuestId = questF   NextQuestId = 0         ExclusiveGroup = 0          NextQuestInChain = 0         entry = questB3

*Note: if player can choose between chain A or B may be determined by faction status (aldor or scryer), using ReqMinRepFaction = 1. Player should not be able to be neutral+1 with both at the same time. This may be the common threshold to obtain aldor or scryer quests (this is unsure). If that is the case, only the unlock of C, D and E after complete A2 *or* B2 is the impossible part.*
