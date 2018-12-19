Back to [world database](mangosdb_struct) list of tables.

The \`achievement\_reward\` table
---------------------------------

This table contains the rewards for achievements added with Wrath of the Lichking.

### Structure

| Field                                 | Type         | Attributes | Can be null | Default | Comments   |
|---------------------------------------|--------------|------------|-------------|---------|------------|
| [entry](Achievement_reward#entry)     | mediumint(8) | unsigned   | NO          | 0       | Identifier |
| [gender](Achievement_reward#gender)   | TINYINT (3)  | unsigned   | YES         | 2       |            |
| [title\_A](Achievement_reward#title)  | mediumint(8) | unsigned   | NO          | 0       |            |
| [title\_H](Achievement_reward#title)  | mediumint(8) | unsigned   | NO          | 0       |            |
| [item](Achievement_reward#item)       | mediumint(8) | unsigned   | NO          | 0       |            |
| [sender](Achievement_reward#sender)   | mediumint(8) | unsigned   | NO          | 0       |            |
| [subject](Achievement_reward#subject) | varchar(255) |            | YES         | NULL    |            |
| [text](Achievement_reward#text)       | text         |            | YES         | NULL    |            |

### Description of the fields

#### entry

This is the achievement identifier from [Achievements.dbc](Achievements.dbc)

#### gender

Indicates characters of which gender may gain that reward. MALE = 0 FEMALE = 1 BOTH = 2

#### title

This is the reference to [CharTitles.dbc.](CharTitles.dbc). Player has the right to wear the title as name affix.

#### item

The item you get by mail for the achievement. Reference to [item\_template](item_template#entry).

#### sender

You recieve mail from this sender. Reference to [creature\_template](creature_template#entry)

#### subject

The mail subject. Just plain text up to 255 chars.

#### text

The mail text.
