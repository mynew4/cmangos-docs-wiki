Back to [world database](mangosdb_struct) list of tables.

The \`dbscript\_string\` table
------------------------------

Holds texts for scripts.

### Structure

| **Field**                                           | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Dbscript_string#entry)                      | int(11) unsigned | NO       | PRI     | 0           |           |
| [content\_default](Dbscript_string#content_default) | text             | NO       |         |             |           |
| [content\_loc1](Dbscript_string#content_loc)        | text             | YES      |         | NULL        |           |
| [content\_loc2](Dbscript_string#content_loc)        | text             | YES      |         | NULL        |           |
| [content\_loc3](Dbscript_string#content_loc)        | text             | YES      |         | NULL        |           |
| [content\_loc4](Dbscript_string#content_loc)        | text             | YES      |         | NULL        |           |
| [content\_loc5](Dbscript_string#content_loc)        | text             | YES      |         | NULL        |           |
| [content\_loc6](Dbscript_string#content_loc)        | text             | YES      |         | NULL        |           |
| [content\_loc7](Dbscript_string#content_loc)        | text             | YES      |         | NULL        |           |
| [content\_loc8](Dbscript_string#content_loc)        | text             | YES      |         | NULL        |           |
| [sound](Dbscript_string#sound)                      | mediumint        | NO       |         | 0           |           |
| [type](Dbscript_string#type)                        | tinyint          | NO       |         | 0           |           |
| [language](Dbscript_string#language)                | tinyint          | NO       |         | 0           |           |
| [emote](Dbscript_string#emote)                      | smallint         | NO       |         | 0           |           |
| [comment](Dbscript_string#comment)                  | text             | YES      |         | NULL        |           |

### Description of the fields

#### entry

The ID to identify the text. Referenced by [event\_scripts](event_scripts#dataint), [gameobject\_scripts](gameobject_scripts#dataint), [quest\_start\_scripts](quest_start_scripts#dataint), [quest\_end\_scripts](quest_end_scripts#dataint), [spell\_scripts](spell_scripts#dataint) and [creature\_movement](creature_movement#text).

Entries must be between 2000000000 and 2000010000.

#### content\_default

The text for default language. UDB provides english, see e.g. GMDB[1](http://sourceforge.net/projects/gm-db/%7CGMDB) for german support.

#### content\_loc

The translation in another language depending on the locale ID of that language.

| **locale ID** | **language**                   |
|---------------|--------------------------------|
| 1             | Korean (koKR)                  |
| 2             | French (frFR)                  |
| 3             | German (deDE)                  |
| 4             | Chinese (zhCN)                 |
| 5             | Taiwan (zhTW)                  |
| 6             | Spanish (esES) / Mexico (esMX) |
| 7             | Russian (ruRU)                 |

#### sound

[Sound ID](SoundEntries.dbc#Content).

#### type

| Type | Description            | Details                                                       |
| ---- | ---------------------- | ------------------------------------------------------------- |
| 0    | CHAT_TYPE_SAY          | 'white' text                                                  |
| 1    | CHAT_TYPE_YELL         | 'red' text                                                    |
| 2    | CHAT_TYPE_TEXT_EMOTE   | 'brown' small emote-text                                      |
| 3    | CHAT_TYPE_BOSS_EMOTE   | 'big yellow' emote-text displayed in the center of the screen |
| 4    | CHAT_TYPE_WHISPER      | whisper, needs a target                                       |
| 5    | CHAT_TYPE_BOSS_WHISPER | whipser, needs a target                                       |
| 6    | CHAT_TYPE_ZONE_YELL    | 'red' text, displayed to everyone in the zone                 |
| 7    | CHAT_TYPE_ZONE_EMOTE   | 'brown' zone-wide text emote                                  |

#### language

[Language ID](Languages.dbc#Content).

#### emote

Emote ID to play.

#### comment

Description.
