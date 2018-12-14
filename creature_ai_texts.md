Back to [creature\_ai\_scripts](creature_ai_scripts) tables.

The \`creature\_ai\_texts\` table
---------------------------------

This table holds all the texts used within the eventai (ACID) scripts. This table handles the actual text, display type (say/yell/emote) and corresponding sounds or emote (if any).

### Structure

| Field                                                 | Type    | Attributes | Can be null | Default | Comments            |
|-------------------------------------------------------|---------|------------|-------------|---------|---------------------|
| [entry](creature_ai_texts#entry)                      | int(11) | signed     | NO          | 0       | Text Entry          |
| [content\_default](creature_ai_texts#content_default) | text    |            | YES         | NULL    | Default Locale Text |
| [content\_loc1](creature_ai_texts#content_loc)        | text    |            | YES         | NULL    | Locale 1 Text       |
| [content\_loc2](creature_ai_texts#content_loc)        | text    |            | YES         | NULL    | Locale 2 Text       |
| [content\_loc3](creature_ai_texts#content_loc)        | text    |            | YES         | NULL    | Locale 3 Text       |
| [content\_loc4](creature_ai_texts#content_loc)        | text    |            | YES         | NULL    | Locale 4 Text       |
| [content\_loc5](creature_ai_texts#content_loc)        | text    |            | YES         | NULL    | Locale 5 Text       |
| [content\_loc6](creature_ai_texts#content_loc)        | text    |            | YES         | NULL    | Locale 6 Text       |
| [content\_loc7](creature_ai_texts#content_loc)        | text    |            | YES         | NULL    | Locale 7 Text       |
| [content\_loc8](creature_ai_texts#content_loc)        | text    |            | YES         | NULL    | Locale 8 Text       |
| [sound](creature_ai_texts#sound)                      | int(11) | unsigned   | NO          | 0       | Sound Id            |
| [type](creature_ai_texts#type)                        | int(11) | unsigned   | NO          | 0       | Text Type           |
| [language](creature_ai_texts#language)                | int(11) | unsigned   | NO          | 0       | Text Language       |
| [emote](creature_ai_texts#emote)                      | int(11) | unsigned   | NO          | 0       | Emote Id            |
| [comment](creature_ai_texts#comment)                  | text    |            | YES         | NULL    | Comment             |

### Description of the fields

#### entry

This is the entry of the text. It corresponds to a script using ACTION\_T\_TEXT\_NEW 54 or ACTION\_T\_TEXT 1 in the [creature\_ai\_scripts](creature_ai_scripts) table. This number is always negative.

#### content\_default

This is the actual text presented in the default language (English).

#### content\_loc

This is the actual text presented in the Localization \#(1-8) Clients

| Value | Localization   |
|-------|----------------|
| 1     | Korean         |
| 2     | French         |
| 3     | German         |
| 4     | Chinese        |
| 5     | Taiwanese      |
| 6     | Spanish        |
| 7     | Spanish Mexico |
| 8     | Russian        |

#### sound

This is the sound Id that will play with along with the corresponding text. All sounds are from [SoundEntries.dbc](SoundEntries.dbc).

#### type

This is the method the text is displayed.

| Value | Type            |
|-------|-----------------|
| 0     | Say             |
| 1     | Yell            |
| 2     | Text Emote      |
| 3     | Boss Emote      |
| 4     | Whisper         |
| 5     | Boss Whisper    |
| 6     | Zone Yell       |
| 7     | Zone Text Emote |

#### language

This is the ingame language of the text. Languages are from [Languages.dbc.](Languages.dbc).

<table>
<colgroup>
<col width="5%" />
<col width="15%" />
<col width="78%" />
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
<td>UNIVERSAL</td>
<td>Text in this language is understood by ALL Races.</td>
</tr>
<tr class="even">
<td>1</td>
<td>ORCISH</td>
<td>Text in this language is understood ONLY by Horde Races.</td>
</tr>
<tr class="odd">
<td>2</td>
<td>DARNASSIAN</td>
<td>Text in this language is understood ONLY by the Night Elf Race.</td>
</tr>
<tr class="even">
<td>3</td>
<td>TAURAHE</td>
<td>Text in this language is understood ONLY by the Tauren Race.</td>
</tr>
<tr class="odd">
<td>6</td>
<td>DWARVISH</td>
<td>Text in this language is understood ONLY by the Dwarf Race.</td>
</tr>
<tr class="even">
<td>7</td>
<td>COMMON</td>
<td>Text in this language is understood ONLY by Alliance Races.</td>
</tr>
<tr class="odd">
<td>8</td>
<td>DEMONIC</td>
<td>Text in this language is understood ONLY by the Demon Race (Not Implemented).</td>
</tr>
<tr class="even">
<td>9</td>
<td>TITAN</td>
<td>This language was used by Sargeras to speak with other Titians (Not Implemented).</td>
</tr>
<tr class="odd">
<td>10</td>
<td>THALASSIAN</td>
<td>Text in this language is understood ONLY by the Blood Elf Race.</td>
</tr>
<tr class="even">
<td>11</td>
<td>DRACONIC</td>
<td>Text in this language is understood ONLY by the Dragon Race.</td>
</tr>
<tr class="odd">
<td>12</td>
<td>KALIMAG</td>
<td>Text will display as Kalimag (not readable by players, language of all elementals)</td>
</tr>
<tr class="even">
<td>13</td>
<td>GNOMISH</td>
<td>Text in this language is understood ONLY by the Gnome Race.</td>
</tr>
<tr class="odd">
<td>14</td>
<td>TROLL</td>
<td>Text in this language is understood ONLY by the Troll Race.</td>
</tr>
<tr class="even">
<td>33</td>
<td>GUTTERSPEAK</td>
<td>Text in this language is understood ONLY by the Undead Race.</td>
</tr>
<tr class="odd">
<td>35</td>
<td>DRAENEI</td>
<td>Text in this language is understood ONLY by the Draenai Race.</td>
</tr>
<tr class="even">
<td>36</td>
<td>ZOMBIE</td>
<td>(not currently used?)</td>
</tr>
<tr class="odd">
<td>37</td>
<td>GNOMISH BINARY</td>
<td>Binary language used by Alliance when drinking Binary Brew</td>
</tr>
<tr class="even">
<td>38</td>
<td>GOBLIN BINARY</td>
<td>Binary language used by Horce when drinking Binary Brew</td>
</tr>
</tbody>
</table>

#### emote

This is the emote that the creature performs along with the corresponding text.

#### comment

This field allows you to label a text entry.
