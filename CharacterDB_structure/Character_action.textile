Back to the "characters database":charactersdb_struct list of tables.

h2. The `character&#95;action` table

Contains all the individual button data for each character. A button is any of the places in the GUI where you can place for example a spell, item, or macro as a shortcut.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"guid":Character_action#guid|int(11) unsigned|NO|PRI|0||
|"button":Character_action#button|tinyint(3) unsigned|NO|PRI|0||
|"action":Character_action#action|smallint(5) unsigned|NO||0||
|"type":Character_action#type|tinyint(3) unsigned|NO||0||
|"misc":Character_action#misc|tinyint(3) unsigned|NO||0||


h3. Description of the fields

h4. guid

The GUID of the character. See "character.guid":character#guid

h4. button

The ID of the button on the action bar where the action icon will be placed.
Special bars are used for stances, auras, pets, stealth, and other similar special modes.

<table>
<caption>Possible values</caption>
<thead>
<tr class="header">
<th align="left">Button IDs
</th>
<th align="left">Set (key)
</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1-11
</td>
<td align="left">1 (SHIFT + 1)
</td>
</tr>
<tr class="even">
<td align="left">12-23
</td>
<td align="left">2 (SHIFT + 2)
</td>
</tr>
<tr class="odd">
<td align="left">24-35
</td>
<td align="left">3 (SHIFT + 3) == Right Side Bar
</td>
</tr>
<tr class="even">
<td align="left">36-47
</td>
<td align="left">4 (SHIFT + 4) == Right Side Bar 2
</td>
</tr>
<tr class="odd">
<td align="left">48-59
</td>
<td align="left">5 (SHIFT + 5) == Bottom Right Bar
</td>
</tr>
<tr class="even">
<td align="left">60-71
</td>
<td align="left">6 (SHIFT + 6) == Bottom Left Bar
</td>
</tr>
<tr class="odd">
<td align="left">72-83
</td>
<td align="left">1 SpecialA
</td>
</tr>
<tr class="even">
<td align="left">84-95
</td>
<td align="left">1 SpecialB
</td>
</tr>
<tr class="odd">
<td align="left">96-107
</td>
<td align="left">1 SpecialC
</td>
</tr>
<tr class="even">
<td align="left">108-119
</td>
<td align="left">1 SpecialD
</td>
</tr>
</tbody>
</table>

h4. action

Depending on the type value, this could be either the spell ID (Spell.dbc), the "item ID":item_template#entry or macro ID.

h4. type

The type of action:

<table>
<caption>Possible types</caption>
<tbody>
<tr class="odd">
<td align="left">0
</td>
<td align="left">Spell
</td>
</tr>
<tr class="even">
<td align="left">64
</td>
<td align="left">Macro
</td>
</tr>
<tr class="odd">
<td align="left">128
</td>
<td align="left">Item
</td>
</tr>
</tbody>
</table>

h4. misc

More info needed here.
It is mostly 0 however it is sometimes 11.
If it is 11, the type is always 128 and the action ID is 57xxx.
