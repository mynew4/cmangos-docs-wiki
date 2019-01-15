Back to the [characters database](charactersdb_struct) list of tables.

The \`character\_action\` table
-------------------------------

Contains all the individual button data for each character. A button is any of the places in the GUI where you can place for example a spell, item, or macro as a shortcut.

### Structure

| **Field**                         | **Type**             | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------|----------------------|----------|---------|-------------|-----------|
| [guid](Character_action#guid)     | int(11) unsigned     | NO       | PRI     | 0           |           |
| [button](Character_action#button) | tinyint(3) unsigned  | NO       | PRI     | 0           |           |
| [action](Character_action#action) | smallint(5) unsigned | NO       |         | 0           |           |
| [type](Character_action#type)     | tinyint(3) unsigned  | NO       |         | 0           |           |
| [misc](Character_action#misc)     | tinyint(3) unsigned  | NO       |         | 0           |           |

### Description of the fields

#### guid

The GUID of the character. See [characters.guid](characters#guid)

#### button

The ID of the button on the action bar where the action icon will be placed.<br>
Special bars are used for stances, auras, pets, stealth, and other similar special modes.

| Button IDs | Set (key)                       |
| ---------- | ------------------------------- |
| 1-11       | 1 (SHIFT + 1)                   |
| 12-23      | 2 (SHIFT + 2)                   |
| 24-35      | 3 (SHIFT + 3) == Right Side Bar |
| 36-47      | 4 (SHIFT + 4)  Right Side Bar 2 |
| 48-59      | 5 (SHIFT + 5)  Bottom Right Bar |
| 60-71      | 6 (SHIFT + 6)  Bottom Left Bar  |
| 72-83      | 1 SpecialA                      |
| 84-95      | 1 SpecialB                      |
| 96-107     | 1 SpecialC                      |
| 108-119    | 1 SpecialD                      |

#### action

Depending on the type value, this could be either the spell ID (Spell.dbc), the [item ID](item_template#entry) or macro ID.

#### type

The type of action:

| Value | Type  |
| ----- | ----- |
| 0     | Spell |
| 64    | Macro |
| 128   | Item  |

#### misc

More info needed here.<br>
It is mostly 0 however it is sometimes 11.<br>
If it is 11, the type is always 128 and the action ID is 57xxx.
