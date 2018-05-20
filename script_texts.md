Back to [world database](https://github.com/cmangos/issues/wiki/mangosdb_struct) list of tables.

## The `script_texts` table

holds all the texts used by core scripted creatures (ScriptDev). This table handles the actual text, display type (say/yell/emote) and corresponding sounds or emote (if any).

### Structure

|Field|Type|Attributes|Null|Default|Comments|
|--- |--- |--- |--- |--- |--- |
|[entry](https://github.com/cmangos/issues/wiki/script_texts#entry)|int(11)|signed|NO|0|Text Entry|
|[content_default](https://github.com/cmangos/issues/wiki/script_texts#content_default)|text||YES|NULL|Default Locale Text|
|[content_loc1](https://github.com/cmangos/issues/wiki/script_texts#content_loc)|text||YES|NULL|Locale 1 Text|
|[content_loc2](https://github.com/cmangos/issues/wiki/script_texts#content_loc)|text||YES|NULL|Locale 2 Text|
|[content_loc3](https://github.com/cmangos/issues/wiki/script_texts#content_loc)|text||YES|NULL|Locale 3 Text|
|[content_loc4](https://github.com/cmangos/issues/wiki/script_texts#content_loc)|text||YES|NULL|Locale 4 Text|
|[content_loc5](https://github.com/cmangos/issues/wiki/script_texts#content_loc)|text||YES|NULL|Locale 5 Text|
|[content_loc6](https://github.com/cmangos/issues/wiki/script_texts#content_loc)|text||YES|NULL|Locale 6 Text|
|[content_loc7](https://github.com/cmangos/issues/wiki/script_texts#content_loc)|text||YES|NULL|Locale 7 Text|
|[content_loc8](https://github.com/cmangos/issues/wiki/script_texts#content_loc)|text||YES|NULL|Locale 8 Text|
|[sound](https://github.com/cmangos/issues/wiki/script_texts#sound)|int(11)|unsigned|NO|0|Sound Id|
|[type](https://github.com/cmangos/issues/wiki/script_texts#type)|int(11)|unsigned|NO|0|Text Type|
|[language](https://github.com/cmangos/issues/wiki/script_texts#language)|int(11)|unsigned|NO|0|Text Language|
|[emote](https://github.com/cmangos/issues/wiki/script_texts#emote)|int(11)|unsigned|NO|0|Emote Id|
|[comment](https://github.com/cmangos/issues/wiki/script_texts#comment)|text||YES|NULL|Comment|

### Description of the fields

#### entry

This is the entry of the text. It corresponds to a cpp script using DoScriptText(); to display the text. This number is always negative.

#### content_default

This is the actual text presented in the default language (English).

#### content_loc

This is the actual text presented in the Localization #(1-8) Clients

|Value|Localization|
|--- |--- |
|1|Korean|
|2|French|
|3|German|
|4|Chinese|
|5|Taiwanese|
|6|Spanish|
|7|Spanish Mexico|
|8|Russian|

#### sound

This is the sound Id that will play with along with the corresponding text. All sounds are from [SoundEntries.dbc](https://github.com/cmangos/issues/wiki/SoundEntries.dbc).

#### type

This is the method the text is displayed.

|Value|Type|
|--- |--- |
|0|Say|
|1|Yell|
|2|Text Emote|
|3|Boss Emote|
|4|Whisper|
|5|Boss Whisper|
|6|Zone Yell|
|7|Zone Text Emote|

#### language

This is the ingame language of the text. Languages are from [Languages.dbc](https://github.com/cmangos/issues/wiki/Languages.dbc).

|ID|Name|Description|
|--- |--- |--- |
|0|UNIVERSAL|Text in this language is understood by ALL Races.|
|1|ORCISH|Text in this language is understood ONLY by Horde Races.|
|2|DARNASSIAN|Text in this language is understood ONLY by the Night Elf Race.|
|3|TAURAHE|Text in this language is understood ONLY by the Tauren Race.|
|6|DWARVISH|Text in this language is understood ONLY by the Dwarf Race.|
|7|COMMON|Text in this language is understood ONLY by Alliance Races.|
|8|DEMONIC|Text in this language is understood ONLY by the Demon Race (Not Implemented).|
|9|TITAN|This language was used by Sargeras to speak with other Titians (Not Implemented).|
|10|THALASSIAN|Text in this language is understood ONLY by the Blood Elf Race.|
|11|DRACONIC|Text in this language is understood ONLY by the Dragon Race.|
|12|KALIMAG|Text will display as Kalimag (not readable by players, language of all elementals)|
|13|GNOMISH|Text in this language is understood ONLY by the Gnome Race.|
|14|TROLL|Text in this language is understood ONLY by the Troll Race.|
|33|GUTTERSPEAK|Text in this language is understood ONLY by the Undead Race.|
|35|DRAENEI|Text in this language is understood ONLY by the Draenai Race.|
|36|ZOMBIE|(not currently used?)|
|37|GNOMISH BINARY|Binary language used by Alliance when drinking Binary Brew|
|38|GOBLIN BINARY|Binary language used by Horce when drinking Binary Brew|                                                                                                    

#### emote

This is the emote that the creature performs along with the corresponding text.

#### comment

This field allows you to label a text entry.
