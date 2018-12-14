Back to [world database](mangosdb_struct) list of tables.

The \`achievement\_criteria\_requirement\` table
------------------------------------------------

This table contains what need to be done to complete an achievement criteria.

### Structure

| Field                                                        | Type         | Attributes | Can be null | Default | Comments |
|--------------------------------------------------------------|--------------|------------|-------------|---------|----------|
| [criteria\_id](Achievement_criteria_requirement#criteria_id) | mediumint(8) | signed     | NO          | None    |          |
| [type](Achievement_criteria_requirement#type)                | tintint(3)   | unsigned   | NO          | 0       |          |
| [value1](Achievement_criteria_requirement#otherfields)       | mediumint(8) | unsigned   | NO          | 0       |          |
| [value2](Achievement_criteria_requirement#otherfields)       | mediumint(8) | unsigned   | NO          | 0       |          |

### Description of the fields

#### criteria\_id

Column 0 (ID) of achievement\_criteria.dbc This DBC contains the achievement\_id on 2nd column and will be later extracted to show relations.

#### type

Describes how to use value1 and value2.

| Type | Name                          |
|------|-------------------------------|
| 0    | TYPE\_NONE                    |
| 1    | TYPE\_T\_CREATURE             |
| 2    | TYPE\_T\_PLAYER\_CLASS\_RACE  |
| 3    | TYPE\_T\_PLAYER\_LESS\_HEALTH |
| 4    | TYPE\_T\_PLAYER\_DEAD         |
| 5    | TYPE\_S\_AURA                 |
| 6    | TYPE\_S\_AREA                 |
| 7    | TYPE\_T\_AURA                 |
| 8    | TYPE\_VALUE                   |
| 9    | TYPE\_T\_LEVEL                |
| 10   | TYPE\_T\_GENDER               |
| 11   | TYPE\_DISABLED                |
| 12   | TYPE\_MAP\_DIFFICULTY         |
| 13   | TYPE\_MAP\_PLAYER\_COUNT      |
| 14   | TYPE\_T\_TEAM                 |
| 15   | TYPE\_S\_DRUNK                |
| 16   | TYPE\_HOLIDAY                 |
| 17   | TYPE\_BG\_LOSS\_TEAM\_SCORE   |
| 18   | TYPE\_INSTANCE\_SCRIPT        |
| 19   | TYPE\_S\_EQUIPED\_ITEM\_LVL   |
| 20   | TYPE\_REQUIRE\_NTH\_BIRTHDAY  |
| 21   | TYPE\_REQUIRE\_KNOWN\_TITLE   |

#### OtherFields

Depending on what Type was set, the meaning and use for the following fields varies. TYPE\_T are for targets and TYPE\_S are for sources

-   **TYPE\_T\_CREATURE = 1**
    -   value1: Target creature\_template.[entry](creature_template#entry)

<!-- -->
-   '''TYPE\_T\_PLAYER\_CLASS\_RACE = 2 '''
    -   value1: Target Player class
    -   value2: Target Player race

<!-- -->
-   '''TYPE\_T\_PLAYER\_LESS\_HEALTH = 3 '''
    -   value1: Target Health percentage

<!-- -->
-   '''TYPE\_T\_PLAYER\_DEAD = 4 '''
    -   value1: Team value the source player and target dead player must both meet

<!-- -->
-   '''TYPE\_S\_AURA = 5 '''
    -   value1: Spell ID
    -   value2: Effect index

<!-- -->
-   '''TYPE\_S\_AREA = 6 '''
    -   value1: Area ID from [AreaTable.dbc](AreaTable.dbc)

<!-- -->
-   '''TYPE\_T\_AURA = 7 '''
    -   value1: Spell ID
    -   value2: Effect index

<!-- -->
-   **TYPE\_VALUE = 8**
    -   value1: Min Value. Value provided with achievement update must be not less that limit

<!-- -->
-   **TYPE\_T\_LEVEL = 9**
    -   value1: Target Min Level

<!-- -->
-   **TYPE\_T\_GENDER = 10**
    -   value1: Gender: 0=Male, 1=Female

<!-- -->
-   **TYPE\_DISABLED = 11**

Used to prevent achievement criteria to complete if not all requirements are implemented and listed in this table

-   **TYPE\_MAP\_DIFFICULTY = 12**
    -   value1: Map difficulty:

| Description                     | Flag |
|---------------------------------|------|
| DUNGEON\_DIFFICULTY\_NORMAL     | 0    |
| DUNGEON\_DIFFICULTY\_HEROIC     | 1    |
| RAID\_DIFFICULTY\_10MAN\_NORMAL | 0    |
| RAID\_DIFFICULTY\_25MAN\_NORMAL | 1    |
| RAID\_DIFFICULTY\_10MAN\_HEROIC | 2    |
| RAID\_DIFFICULTY\_25MAN\_HEROIC | 3    |

-   **TYPE\_MAP\_PLAYER\_COUNT = 13**
    -   value1: Count. For criteria "with less than %u people in the zone"

<!-- -->
-   **TYPE\_T\_TEAM = 14**
    -   value1: Team: HORDE = 67, ALLIANCE = 469

<!-- -->
-   **TYPE\_S\_DRUNK = 15**
    -   value1: Druken State. DRUNKEN\_SOBER = 0, DRUNKEN\_TIPSY = 1, DRUNKEN\_DRUNK = 2, DRUNKEN\_SMASHED = 3

<!-- -->
-   **TYPE\_HOLIDAY = 16**
    -   value1: Holiday ID which must be active from Holiday.dbc and [game\_event](Game_event#holiday)

<!-- -->
-   '''TYPE\_BG\_LOSS\_TEAM\_SCORE = 17 '''
    -   value1: min\_score
    -   value2: max\_score

<!-- -->
-   '''TYPE\_INSTANCE\_SCRIPT = 18 '''

Make instance script call for check current criteria requirements fit

-   '''TYPE\_S\_EQUIPED\_ITEM\_LVL = 19 '''
    -   value1: item\_level
    -   value2: item\_quality

For equipped item in slot \`misc1\` to item level and quality

-   '''TYPE\_REQUIRE\_NTH\_BIRTHDAY = 20 '''
    -   value1: nth-birthday

<!-- -->
-   '''TYPE\_CRITERIA\_REQUIRE\_KNOWN\_TITLE = 21 '''
    -   value1: [title\_id](CharTitles.dbc)

