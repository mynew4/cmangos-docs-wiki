Back to [dbc files](dbc_files) list.

### Achievement\_Criteria.dbc

This DBC contains the requirments to aquire an achievement.

**NOTE: Only a few entries from this DBC are included in this page as there are 6682 records in this DBC.**

**Version is : 3.1.3**

### Structure

| Field Nb | Name                                                    | Type   | Notes                                                                                                  |
| -------- | ------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------ |
| 1        | ID                                                      | Int    | ID of Criteria                                                                                         |
| 2        | AchievementID                                           | Int    | Achievement criteria is used for See -> [Achievements.dbc](Achievements.dbc)                           |
| 3        | [Type](Achievement_Criteria.dbc#known-types)            | Int    | Achievement_Criteria_Types]]                                                                           |
| 4        | Value1                                                  | Int    | Achievement_Criteria_Types]]                                                                           |
| 5        | Value2                                                  | Int    | Achievement_Criteria_Types]]                                                                           |
| 6        | Value3                                                  | Int    | Achievement_Criteria_Types]]                                                                           |
| 7        | Value4                                                  | Int    | Achievement_Criteria_Types]]                                                                           |
| 8        | Value5                                                  | Int    | Achievement_Criteria_Types]]                                                                           |
| 9        | Value6                                                  | Int    | Achievement_Criteria_Types]]                                                                           |
| 10-26    | Description                                             | String | Description of Criteria                                                                                |

Known types
-----------

This table explains what the 'type' and 'values' do in the [Achievement\_Criteria.dbc](Achievement_Criteria.dbc)

| Type | Name            | Value1                              | Value2      | Value3    | Value4    | Value5    | Value6  |
| ---- | --------------- | ----------------------------------- | ----------- | --------- | --------- | --------- | ------- |
| 1    | PvP Wins        | MapID]]                             | Unknown     | Unknown   | Unknown   | Unknown   | Unknown |
| 2    | Level Race      | RaceID]]                            | Level       | No Death? | No Death? | No Death? | Unknown |
| 3    | Level Class     | ClassID]]                           | Level       | No Death? | No Death? | No Death? | Unknown |
| 4    | Level Faction   | FactionID (0 - Alliance, 1 - Horde) | Level       | No Death? | No Death? | No Death? | Unknown |
| 5    | Level           | Unknown                             | Level       | No Death? | No Death? | No Death? | Unknown |
| 6    | Collect Pets    | Unknown                             | Amount      | Unknown   | Unknown   | Unknown   | Unknown |
| 7    | Skill           | SkillID                             | Skill Level | Unknown   | Unknown   | Unknown   | Unknown |
| 8    | Multi-Criteria? | Criteria Group ID?                  | Worth?      | Unknown   | Unknown   | Unknown   | Unknown |
| 9    | Quests          | Unknown                             | Amount      | Unknown   | Unknown   | Unknown   | Unknown |
| 10   | Daily Quests    | Unknown                             | Days        | Unknown   | Unknown   | Unknown   | Unknown |
| 11   | Zone Quests     | AreaID]]                            | Amount      | Unknown   | Unknown   | Unknown   | Unknown |
| 12   | Exploration     | MapID]]                             | Unknown     | Unknown   | Unknown   | Unknown   | Unknown |
| 13   | Damage          | Unknown                             | Unknown     | Unknown   | Unknown   | Unknown   | Unknown |
| 14   | Unknown         | Unknown                             | Unknown     | Unknown   | Unknown   | Unknown   | Unknown |
| 15   | PvP Played      | MapID]]                             | Unknown     | Unknown   | Unknown   | Unknown   | Unknown |
| 16   | PvP Deaths      | MapID]]                             | Unknown     | Unknown   | Unknown   | Unknown   | Unknown |

### Content

| **ID** | **AchievementID** | **Type** | **Value1** | **Value2** | **Value3** | **Value4** | **Value5** | **Value6** | **Description**                                            |
|--------|-------------------|----------|------------|------------|------------|------------|------------|------------|------------------------------------------------------------|
| 34     | 6                 | 5        | 0          | 10         | 0          | 0          | 0          | 0          | Reach level 10                                             |
| 35     | 7                 | 5        | 0          | 20         | 0          | 0          | 0          | 0          | Reach level 20                                             |
| 36     | 8                 | 5        | 0          | 30         | 0          | 0          | 0          | 0          | Reach level 30                                             |
| 37     | 9                 | 5        | 0          | 40         | 0          | 0          | 0          | 0          | Reach level 40                                             |
| 38     | 10                | 5        | 0          | 50         | 0          | 0          | 0          | 0          | Reach level 50                                             |
| 39     | 11                | 5        | 0          | 60         | 0          | 0          | 0          | 0          | Reach level 60                                             |
| 40     | 12                | 5        | 0          | 70         | 0          | 0          | 0          | 0          | Reach level 70                                             |
| 41     | 13                | 5        | 0          | 80         | 0          | 0          | 0          | 0          | Reach level 80                                             |
| 72     | 31                | 10       | 0          | 5          | 2          | 0          | 2          | 0          | Complete a daily quest every day for five consecutive days |
| 73     | 32                | 9        | 0          | 2000       | 0          | 0          | 0          | 0          | Complete 2000 quests                                       |
| 74     | 33                | 11       | 3537       | 130        | 0          | 0          | 0          | 0          | Complete 130 quests in Boren Tundra                        |
| 75     | 34                | 11       | 495        | 130        | 0          | 0          | 0          | 0          | Complete 130 quests in Howling Fjord                       |
| 76     | 35                | 11       | 65         | 115        | 0          | 0          | 0          | 0          | Complete 115 quests in Dragonblight                        |
| 77     | 36                | 11       | 66         | 100        | 0          | 0          | 0          | 0          | Complete 100 Zul'Drak Quests                               |
| 78     | 37                | 11       | 394        | 85         | 0          | 0          | 0          | 0          | Complete 85 quests in Grizzly Hills                        |
| 79     | 38                | 11       | 67         | 100        | 0          | 0          | 0          | 0          | Complete 100 Storm Peaks Quests                            |
| 80     | 39                | 11       | 3711       | 75         | 0          | 0          | 0          | 0          | Complete 75 Sholazar Basin quests.                         |
| 81     | 40                | 11       | 210        | 140        | 0          | 0          | 0          | 0          | Complete 140 Icecrown Glacier quests                       |
| 82     | 41                | 8        | 33         | 1          | 0          | 0          | 0          | 0          | Nothing Boring About Borean                                |
| 94     | 46                | 8        | 42         | 1          | 0          | 0          | 0          | 0          | Eastern Kingdoms                                           |
| 100    | 49                | 1        | 30         | 0          | 0          | 0          | 0          | 0          | Alterac Valley victories                                   |
| 101    | 52                | 1        | 566        | 0          | 0          | 0          | 0          | 0          | Eye of the Storm Wins: \[PH\]                              |
| 102    | 51                | 1        | 529        | 0          | 0          | 0          | 0          | 0          | Arathi Basin victories                                     |
| 103    | 50                | 15       | 489        | 0          | 0          | 0          | 0          | 0          | Warsong Gulch Played: \[PH\]                               |
| 104    | 53                | 15       | 30         | 0          | 0          | 0          | 0          | 0          | Alterac Valley battles                                     |
| 105    | 54                | 15       | 566        | 0          | 0          | 0          | 0          | 0          | Eye of the Storm battles                                   |
| 106    | 55                | 15       | 529        | 0          | 0          | 0          | 0          | 0          | Arathi Basin battles                                       |
| 107    | 56                | 16       | 489        | 0          | 0          | 0          | 0          | 0          | Deaths in Warsong Gulch                                    |
| 108    | 57                | 16       | 30         | 0          | 0          | 0          | 0          | 0          | Deaths in Alterac Valley                                   |
| 110    | 59                | 16       | 529        | 0          | 0          | 0          | 0          | 0          | Arathi Basin Deaths                                        |
| 111    | 60                | 17       | 0          | 0          | 0          | 0          | 0          | 0          | Total deaths                                               |
| 123    | 73                | 30       | 122        | 3          | 3          | 529        | 3          | 529        | Assault 3 bases in a single Arathi Basin battle            |
| 134    | 99                | 1        | 0          | 0          | 0          | 0          | 0          | 0          | Ruins of Lordaeron matches                                 |
| 137    | 103               | 15       | 0          | 0          | 0          | 0          | 0          | 0          | Circle of Blood matches                                    |
| 138    | 100               | 1        | 0          | 0          | 0          | 0          | 0          | 0          | Ring of Trials victories                                   |

**NOTE: This is not all of the DBC Data, it is far to large to post it all here.**
