Back to [world database](mangosdb_struct) list of tables.

With this table and the new conditions it is possible to create tree like and very complicated combined conditions (like HasAura && (HasItem || HasQuest))

Used in:

-   [DBScript](DBScripts)
-   [gossip\_menu](gossip_menu)
-   [gossip\_menu\_option](gossip_menu_option)
-   [npc\_spellclick\_spells](npc_spellclick_spells)
-   [spell\_area](spell_area)

The \`conditions\` table
------------------------

### Structure

| **Field**                                      | **Type**     | **Attributes** | **Key** | **Null** | **Default** |
|------------------------------------------------|--------------|----------------|---------|----------|-------------|
| [condition\_entry](Conditions#condition_entry) | mediumint(8) | unsigned       | PRI     | YES      | NULL        |
| [type](Conditions#type)                        | tinyint(3)   | signed         |         | NO       | 0           |
| [value1](Conditions#value1)                    | mediumint(8) | unsigned       |         | NO       | 0           |
| [value2](Conditions#value2)                    | mediumint(8) | unsigned       |         | NO       | 0           |

### Description of the fields

#### condition\_entry

Identifier

#### type

Type of the condition

#### value1

data field one for the condition

#### value2

data field one for the condition

### Possible condition types

This is a description of the values in [type](Conditions#type)

| Value of type | Condition                       | Comments                                                                                              |
| ------------- | ------------------------------- | ----------------------------------------------------------------------------------------------------- |
| -3            | CONDITION_NOT                   | NOT combination of another condition_entry *                                                          |
| -2            | CONDITION_OR                    | OR combination of 2 other condition_entry *                                                           |
| -1            | CONDITION_AND                   | AND combination of 2 other condition_entry *                                                          |
| 0             | CONDITION_NONE                  | No condition, returns always true                                                                     |
| 1             | CONDITION_AURA                  | Player must have an aura active                                                                       |
| 2             | CONDITION_ITEM                  | Player must have a number of items in his/her inventory                                               |
| 3             | CONDITION_ITEM_EQUIPPED         | Player must have an item equipped                                                                     |
| 4             | CONDITION_AREAID                | Player must be in a certain area/zone                                                                 |
| 5             | CONDITION_REPUTATION_RANK_MIN   | Player must have a certain reputation rank with a certain faction                                     |
| 6             | CONDITION_TEAM                  | Player must be part of the specified team (Alliance or Horde)                                         |
| 7             | CONDITION_SKILL                 | Player must have a certain skill value                                                                |
| 8             | CONDITION_QUESTREWARDED         | Player must have completed a quest first                                                              |
| 9             | CONDITION_QUESTTAKEN            | Players must have the quest in the quest log and not completed yet                                    |
| 10            | CONDITION_AD_COMMISSION_AURA    |                                                                                                       |
| 11            | CONDITION_NO_AURA               | Miss some aura.                                                                                       |
| 12            | CONDITION_ACTIVE_EVENT          | Event is active.                                                                                      |
| 13            | CONDITION_AREA_FLAG             |                                                                                                       |
| 14            | CONDITION_RACE_CLASS            | Has special race or class.                                                                            |
| 15            | CONDITION_LEVEL                 | Has special level.                                                                                    |
| 16            | CONDITION_NOITEM                | Has not enough items yet.                                                                             |
| 17            | CONDITION_SPELL                 | Knows some spell.                                                                                     |
| 18            | CONDITION_INSTANCE_SCRIPT       | SD2-Based condition                                                                                   |
| 19            | CONDITION_QUESTAVAILABLE        | Some quest is available.                                                                              |
| 20            | CONDITION_ACHIEVEMENT           | Has or has no special achievement.                                                                    |
| 21            | CONDITION_ACHIEVEMENT_REALM     | Realm-wideversion of 20.                                                                              |
| 22            | CONDITION_QUEST_NONE            | Has not taken a quest yet.                                                                            |
| 23            | CONDITION_ITEM_WITH_BANK        | Checks presence of required amount of items in inventory or bank.                                     |
| 24            | CONDITION_NOITEM_WITH_BANK      | Checks absence of required amount of items in inventory or bank.                                      |
| 25            | CONDITION_NOT_ACTIVE_GAME_EVENT |                                                                                                       |
| 26            | CONDITION_ACTIVE_HOLIDAY        |                                                                                                       |
| 27            | CONDITION_NOT_ACTIVE_HOLIDAY    |                                                                                                       |
| 28            | CONDITION_LEARNABLE_ABILITY     | Checks if the player has high enough skill level and may check if a special item is in the inventory. |
| 29            | CONDITION_SKILL_BELOW           |                                                                                                       |
| 30            | CONDITION_REPUTATION_RANK_MAX   |                                                                                                       |
| 31            | CONDITION_COMPLETED_ENCOUNTER   | Checks if some encounter is completed                                                                 |
| 32            | CONDITION_SOURCE_AURA           | Checks if the source of the condition (like looted npc) has an aura                                   |
| 33            | CONDITION_LAST_WAYPOINT         | Checks the waypoint-state of the source of the condition                                              |
| 34            | CONDITION_XP_USER               | Checks if a player has turned XP earning on/off                                                       |
| 35            | CONDITION_GENDER                | Checks the gender of a player                                                                         |
| 36            | CONDITION_DEAD_OR_AWAY          |                                                                                                       |
| 37            | CONDITION_CREATURE_IN_RANGE     |                                                                                                       |
| 38            | CONDITION_PVP_SCRIPT            |                                                                                                       |
| 39            | CONDITION_SPAWN_COUNT           | Returns if specified count of creature entry exists on map                                            |

(\*) Meta-Condition types CONDITION\_AND (-1) and CONDITION\_OR (-2) which are used as: value1 (as condition\_entry) AND / OR value2 (as condition\_entry). With these meta-conditions it is possible to create tree like and very complicated combined conditions (like HasAura && (HasItem || HasQuest))

### Detailed description of available condition types

The meaning of the values in [value1](Conditions#value1) / [value2](Conditions#value2) depend of the [type](Possible-condition-types) of the condition

-   CONDITION\_NOT (-3)
    -   value1: condition\_entry
    -   Must have higher condition\_entry than value1
        Returns NOT condidition (of value1)

<!-- -->
-   CONDITION\_OR (-2)
    -   value1: condition\_entry
    -   value2: condition\_entry
    -   Must have higher condition\_entry than value1 OR value2
        Returns condidition (of value1) OR condidition (of value2)

<!-- -->
-   CONDITION\_AND (-1)
    -   value1: condition\_entry
    -   value2: condition\_entry
    -   Must have higher condition\_entry than value1 OR value2
        Returns condidition (of value1) AND condidition (of value2)

<!-- -->
-   CONDITION\_NONE (0)
    No condition - is always met

<!-- -->
-   CONDITION\_AURA (1)
    -   value1: The spell ID from where the aura came from.
    -   value2: The effect index of the spell that applied the aura (0, 1, or 2)
        Returns if a player has an aura

<!-- -->
-   CONDITION\_ITEM (2)
    -   value1: Item ID
    -   value2: Count
        Returns if a player has Count items in his inventory

<!-- -->
-   CONDITION\_ITEM\_EQUIPPED (3)
    -   value1: Item ID
        Returns if a player has an item equipped

<!-- -->
-   CONDITION\_AREAID (4)
    -   value1: Area ID
    -   value2: 0, 1 (0: in (sub)area, 1: not in (sub)area)
        Returns if (or if not depending on value2) a player is in an area/zone

<!-- -->
-   CONDITION\_REPUTATION\_RANK\_MIN (5)
    -   value1: Faction ID
    -   value2: Minimum rank
        Returns if a player has at least (>=) minimum rank at the given faction

| ID  | Rank       |
|-----|------------|
| 0   | Hated      |
| 1   | Hostile    |
| 2   | Unfriendly |
| 3   | Neutral    |
| 4   | Friendly   |
| 5   | Honored    |
| 6   | Revered    |
| 7   | Exalted    |

-   CONDITION\_TEAM (6)
    -   value1: Player team (469 - Alliance, 67 - Horde)
        Returns if a player has the team of value1

<!-- -->
-   CONDITION\_SKILL (7)
    -   value1: Skill ID (SkillLine.dbc)
    -   value2: Skill value needed
        Returns if a player has Skill ID of value

<!-- -->
-   CONDITION\_QUESTREWARDED (8)
    -   value1: Quest ID
        Returns if a player already got a quest rewarded

<!-- -->
-   CONDITION\_QUESTTAKEN (9)
    -   value1: Quest ID
    -   value2:

| 0   | Returns true if quest is taken, no matter if completed or not |
|-----|---------------------------------------------------------------|
| 1   | Returns true if quest is taken but not completed              |
| 2   | Returns true if quest is taken and completed                  |

-   CONDITION\_AD\_COMMISSION\_AURA (10)
    Returns if a Player has any Argent Dawn Commission Aura Active (17670,23930,24198,29112,29113)

<!-- -->
-   CONDITION\_NO\_AURA (11)
    -   value1: spellid
    -   value2: EffectIndex
        Returns if a player has not an aura

<!-- -->
-   CONDITION\_ACTIVE\_EVENT (12)
    -   value1: [event](game_event)
        Returns if a event is active

<!-- -->
-   CONDITION\_AREA\_FLAG (13)
    -   value1: area\_flag
    -   value2: not\_have\_flag
        Returns if area\_flag is present in current area (if area\_flag set != 0) AND if not\_have\_flag is not present in current area (if not\_have\_flag != 0)

<!-- -->
-   CONDITION\_RACE\_CLASS (14)
    -   value1: race\_mask
    -   value2: class\_mask
        Returns if a player is of race (if race\_mask set != 0) AND if a player is of class (if class\_mask != 0)

| Mask | Race      |
|------|-----------|
| 1    | Human     |
| 2    | Orc       |
| 4    | Dwarf     |
| 8    | Night Elf |
| 16   | Undead    |
| 32   | Tauren    |
| 64   | Gnome     |
| 128  | Troll     |
| 512  | Blood Elf |
| 1024 | Draenei   |

| Mask | Class        |
|------|--------------|
| 1    | Warrior      |
| 2    | Paladin      |
| 4    | Hunter       |
| 8    | Rogue        |
| 16   | Priest       |
| 32   | Death Knight |
| 64   | Shaman       |
| 128  | Mage         |
| 256  | Warlock      |
| 1024 | Druid        |

-   CONDITION\_LEVEL (15)
    -   value1: level
    -   value2: 0: equal to, 1: equal or higher than, 2: equal or less than
        Returns if a player is of/ has a higher/ has a lower level

<!-- -->
-   CONDITION\_NOITEM (16)
    -   value1: itemid
    -   value2: count
        Returns if a player has not count items in Inventory

<!-- -->
-   CONDITION\_SPELL (17)
    -   value1: spellid
    -   value2: 0: has spell, 1: has no spell
        Returns if a player has (not) learned a spell

<!-- -->
-   CONDITION\_INSTANCE\_SCRIPT (18)
    -   value1: instance\_condition\_id (see InstanceData.h enum InstanceConditionIDs)
        Returns the result of the current instance's instance-script function CheckConditionCriteriaMeet (which must be implemented for such an instance)
        To ''communicate'' with the instance script, there are a few instance\_condition\_id predefined, which can be used:
        for hard-mode loot (0 normal; 1,2... hard,harder... mode)
        * INSTANCE\_CONDITION\_ID\_NORMAL\_MODE = 0,
        * INSTANCE\_CONDITION\_ID\_HARD\_MODE = 1,
        * INSTANCE\_CONDITION\_ID\_HARD\_MODE\_2 = 2,
        * INSTANCE\_CONDITION\_ID\_HARD\_MODE\_3 = 3,
        * INSTANCE\_CONDITION\_ID\_HARD\_MODE\_4 = 4,
        to check for which team the instance is doing scripts
        * INSTANCE\_CONDITION\_ID\_TEAM\_HORDE = 67,
        * INSTANCE\_CONDITION\_ID\_TEAM\_ALLIANCE = 469,

<!-- -->
-   CONDITION\_QUESTAVAILABLE (19)
    -   value1: questid
        Returns if a player could start a quest (ie. if all requirements for accepting like pre-quests are met)

<!-- -->
-   CONDITION\_ACHIEVEMENT (20)
    -   value1: achievementid
    -   value2: 0: has achievement, 1: has no achievement
        Returns if a player has (not) earned an achievement

<!-- -->
-   CONDITION\_ACHIEVEMENT\_REALM (21)
    -   value1: achievementid
    -   value2: 0: has achievement, 1: has no achievement
        Returns if an achivement was (not) already earned by any player on the realm

<!-- -->
-   CONDITION\_QUEST\_NONE (22)
    -   value1: questid
        Returns if a player has a quest neither taken nor ever rewarded

<!-- -->
-   CONDITION\_ITEM\_WITH\_BANK (23)
    -   value1: item\_id
    -   value2: count
        Returns if a player has at least count of items (including inventory stored in the bank)

<!-- -->
-   CONDITION\_NOITEM\_WITH\_BANK (24)
    -   value1: item\_id
    -   value2: count
        Returns if a player has less than count of items (including inventory stored in the bank)

<!-- -->
-   CONDITION\_NOT\_ACTIVE\_GAME\_EVENT (25)
    -   value1: event\_id
        Returns if a game event is not active

<!-- -->
-   CONDITION\_ACTIVE\_HOLIDAY (26)
    -   value1: holiday\_id
        Returns if a holidy is active

<!-- -->
-   CONDITION\_NOT\_ACTIVE\_HOLIDAY (27)
    -   value1: holiday\_id
        Returns if a holiday is not active

<!-- -->
-   CONDITION\_LEARNABLE\_ABILITY (28)
    -   value1: spell\_id
    -   value2: 0 or item\_id
        Returns player can learn ability (using min skill value from SkillLineAbility).
        Item\_id can be defined in addition, to check if player has one (1) item in inventory or bank.
        When player has spell or has item (when defined), condition return false.

<!-- -->
-   CONDITION\_SKILL\_BELOW (29)
    -   value1: skill\_id
    -   value2: skill\_value
        Returns if player has skill skill\_id and skill less than (and not equal) skill\_value (for skill\_value > 1)
        If skill\_value == 1, then true if player has not skill skill\_id

<!-- -->
-   CONDITION\_REPUTATION\_RANK\_MAX (30)
    value1: faction\_id
    value2: max\_rank
    Returns if a player has at most (<=) max\_rank with a faction

| ID  | Rank       |
|-----|------------|
| 0   | Hated      |
| 1   | Hostile    |
| 2   | Unfriendly |
| 3   | Neutral    |
| 4   | Friendly   |
| 5   | Honored    |
| 6   | Revered    |
| 7   | Exalted    |

-   CONDITION\_COMPLETED\_ENCOUNTER (31)
    -   value1: encounter\_id (DungeonEncounter(dbc).id)
    -   value2: encounter\_id2 (DungeonEncounter(dbc).id)
        Returns if encounter\_id is complete (if encounter\_id2 provided it will return if encounter\_id is completed OR if encounter\_id2 is completed)

<!-- -->
-   CONDITION\_SOURCE\_AURA (32)
    -   value1: spell\_id
    -   value2: effindex
        Returns true if the source of the condition check has aura of spell\_id, effIndex

<!-- -->
-   CONDITION\_LAST\_WAYPOINT (33)
    -   value1: waypointId
    -   value2: 0 = exact, 1: wp <= waypointId, 2: wp > waypointId
        Returns if the source of the condition is on/ has reached/ has passed a waypoint

<!-- -->
-   CONDITION\_XP\_USER (34)
    -   value1: 0, 1 (0: XP off, 1: XP on)
        Returns if a player has his XP earning turned off/on

<!-- -->
-   CONDITION\_GENDER (35)
    -   value1: 0=male, 1=female, 2=none (see enum Gender)
        Returns if a player is male or female (none cannot happen)

<!-- -->
-   CONDITION\_DEAD\_OR\_AWAY (36)
    -   value1: 0=player dead, 1=player is dead (with group dead), 2=player in instance are dead, 3=creature is dead
    -   value2: optional\_range
        Returns if a player / a player's group / all players in an instance / or a creature is dead or left the map.
        If the optional\_range is provided the condition will also fail if the player\[s\] are out of range

<!-- -->
-   CONDITION\_CREATURE\_IN\_RANGE (37)
    -   value1: creatureEntry
    -   value2: range
        Returns if the creature of the given entry is found in the given range

<!-- -->
-   CONDITION\_PVP\_SCRIPT (38)
    -   value1: area\_id of the outdoor PvP script
    -   value2: opvp\_condition\_id (defined in the actual script)
        Returns the result of the outdoor PvP script function IsConditionFulfilled (which must be implemented for the required scripts)

<!-- -->
-   CONDITION\_SPAWN\_COUNT (39)
    -   value1: [creature\_template.entry](creature_template#entry)
    -   value2: Minimum amount of specified creature to exist on map for condition to return true
        Condition returns true if there are more than or equal amounts of creature on map.
        Note: The creature specified in value1 must have ExtraFlags CREATURE\_EXTRA\_FLAG\_COUNT\_SPAWNS!
