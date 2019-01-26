The following is a table containing indices and what values they contain for [characters.data](characters#data). The source of this data is UpdateFields.h

The .getvalue and .setvalue commands deal with the indices in this table. To modify any of the values in this table in real time, use the .setvalue command with the correct index (eg. .setvalue 4 2 0 sets the target's size to 2.00 (notice that it is a float, hence the 0 at the end)).

All objects in the game (game objects, creatures, and players) share the OBJECT*\* fields while only creatures and players share the UNIT*\* fields while only players use the PLAYER\_\* fields.

If you want to use direct SQL to extract a single value from this rather large blob, the syntax to use is this:

```
SELECT CAST(SUBSTRING_INDEX(SUBSTRING_INDEX(`data`, ' ', <index + 1>), ' ', -1) AS UNSIGNED) AS `fieldName` FROM `characters`;
```

Just replace `<index + 1>` with the index in this table and add one to it.<br> 
The reason why you are adding one is because of how the nested SUBSTRING\_INDEX syntax works. Let's analyze the function calls. Working from the inside out, the first function called is `` SUBSTRING_INDEX(`data`, ' ', <index + 1>) ``. The SUBSTRING\_INDEX function creates a substring from the big data blob after `<index + 1>` spaces. Notice that if we used just <index>, the substring would be everything up to the value we want **but not including it**. The second function call is `SUBSTRING_INDEX(<substring from inner function>, ' ', -1)`. This function call uses -1 as the count, meaning that it will substring from the end to the front. Since it is a count of one, it will create a substring that is exactly the value we want because the value we want is sandwiched between the end of the string and a space. The final function call `CAST(<substring> AS UNSIGNED)` casts the final string into an unsigned integer. This is because the data blob contains only numbers and if we cast the string into an integer, we can use integer operations on it (say if we use it in a WHERE clause to compare to another integer).

An example of the syntax in use is the following query where we are making a list of characters and their levels who have more than 1000 gold.

```
SELECT `guid`, `name`, CAST(SUBSTRING_INDEX(SUBSTRING_INDEX(`data`, ' ', 35), ' ', -1) AS UNSIGNED) AS `level` FROM `characters`
    WHERE CAST(SUBSTRING_INDEX(SUBSTRING_INDEX(`data`, ' ', 1398), ' ', -1) AS UNSIGNED) > 10000000;
```

If you want to edit the value of one of these fields, the query to do that is the following but don't forget to backup your table first:

```
UPDATE `characters` SET `data`=CONCAT(CAST(SUBSTRING_INDEX(`data`, ' ', <index>) AS CHAR), ' ', <value>, ' ',
    CAST(SUBSTRING_INDEX(`data`, ' ', <-(max index - index) - 1>)AS CHAR)) [WHERE ...]
```

Replace `<index>` with the index that you want to change (look at table below), `<-(max_index - index) - 1>` with the negative of the subtraction of the last index (look at table) minus the index that you want to change and finally minus one. Finally replace `<value>` with the new value you want to put.

For example, to reset gold to zero for all characters with level higher than 70, you can use the following query:

```
UPDATE `characters` SET `data`=CONCAT(CAST(SUBSTRING_INDEX(`data`, ' ', 1397) AS CHAR), ' ', 0, ' ',
CAST(SUBSTRING_INDEX(`data`, ' ', -131) AS CHAR)) WHERE CAST(SUBSTRING_INDEX(SUBSTRING_INDEX
(`data`, ' ', 35), ' ', -1) AS UNSIGNED) > 70;
```

Again, don't forget to backup first!!

### 3.3.5 Character Data Table

**This table was last updated for 3.3.5 values.**


| Index | Value Name                                       | Comments                                                                                                     |
| ----- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| 0     | OBJECT_FIELD_GUID                                | Character GUID (full GUID includes both index 0 and index 1 as 64bit number)                                 |
| 2     | OBJECT_FIELD_TYPE                                |                                                                                                              |
| 3     | OBJECT_FIELD_ENTRY                               |                                                                                                              |
| 4     | OBJECT_FIELD_SCALE_X                             | Size of how model appears in-game (float value)                                                              |
| 5     | OBJECT_FIELD_PADDING                             |                                                                                                              |
| 6     | UNIT_FIELD_CHARM                                 |                                                                                                              |
| 8     | UNIT_FIELD_SUMMON                                |                                                                                                              |
| 10    | UNIT_FIELD_CRITTER                               |                                                                                                              |
| 12    | UNIT_FIELD_CHARMEDBY                             |                                                                                                              |
| 14    | UNIT_FIELD_SUMMONEDBY                            |                                                                                                              |
| 16    | UNIT_FIELD_CREATEDBY                             |                                                                                                              |
| 18    | UNIT_FIELD_TARGET                                |                                                                                                              |
| 20    | UNIT_FIELD_CHANNEL_OBJECT                        |                                                                                                              |
| 22    | UNIT_FIELD_CHANNEL_SPELL                         |                                                                                                              |
| 23    | UNIT_FIELD_BYTES_0                               | (gender << 16) &#124; (class_ << 8) &#124; (race)                                                            |
| 24    | UNIT_FIELD_HEALTH                                | Current health                                                                                               |
| 25    | UNIT_FIELD_POWER1                                | Current mana                                                                                                 |
| 26    | UNIT_FIELD_POWER2                                | Current rage                                                                                                 |
| 27    | UNIT_FIELD_POWER3                                | Current focus                                                                                                |
| 28    | UNIT_FIELD_POWER4                                | Current energy                                                                                               |
| 29    | UNIT_FIELD_POWER5                                | Current happiness                                                                                            |
| 30    | UNIT_FIELD_POWER6                                |                                                                                                              |
| 31    | UNIT_FIELD_POWER7                                |                                                                                                              |
| 32    | UNIT_FIELD_MAXHEALTH                             | Max health                                                                                                   |
| 33    | UNIT_FIELD_MAXPOWER1                             | Max mana                                                                                                     |
| 34    | UNIT_FIELD_MAXPOWER2                             | Max rage                                                                                                     |
| 35    | UNIT_FIELD_MAXPOWER3                             | Max focus                                                                                                    |
| 36    | UNIT_FIELD_MAXPOWER4                             | Max energy                                                                                                   |
| 37    | UNIT_FIELD_MAXPOWER5                             | Max happiness                                                                                                |
| 38    | UNIT_FIELD_MAXPOWER6                             |                                                                                                              |
| 39    | UNIT_FIELD_MAXPOWER7                             |                                                                                                              |
| 40    | UNIT_FIELD_POWER_REGEN_FLAT_MODIFIER             |                                                                                                              |
| 47    | UNIT_FIELD_POWER_REGEN_INTERRUPTED_FLAT_MODIFIER |                                                                                                              |
| 54    | UNIT_FIELD_LEVEL                                 | Character level                                                                                              |
| 55    | UNIT_FIELD_FACTIONTEMPLATE                       | Currently used faction template ID ([FactionTemplate.dbc](FactionTemplate.dbc))                              |
| 56    | UNIT_VIRTUAL_ITEM_SLOT_ID                        |                                                                                                              |
| 59    | UNIT_FIELD_FLAGS                                 |                                                                                                              |
| 60    | UNIT_FIELD_FLAGS_2                               |                                                                                                              |
| 61    | UNIT_FIELD_AURASTATE                             |                                                                                                              |
| 62    | UNIT_FIELD_BASEATTACKTIME                        |                                                                                                              |
| 64    | UNIT_FIELD_RANGEDATTACKTIME                      |                                                                                                              |
| 65    | UNIT_FIELD_BOUNDINGRADIUS                        |                                                                                                              |
| 66    | UNIT_FIELD_COMBATREACH                           |                                                                                                              |
| 67    | UNIT_FIELD_DISPLAYID                             | Current model ID (can be different from regular if character is morphed, etc)                                |
| 68    | UNIT_FIELD_NATIVEDISPLAYID                       | The native model ID. Model always reverts to this number when player is demorphed.                           |
| 69    | UNIT_FIELD_MOUNTDISPLAYID                        | Units current mount display id.                                                                              |
| 70    | UNIT_FIELD_MINDAMAGE                             |                                                                                                              |
| 71    | UNIT_FIELD_MAXDAMAGE                             |                                                                                                              |
| 72    | UNIT_FIELD_MINOFFHANDDAMAGE                      |                                                                                                              |
| 73    | UNIT_FIELD_MAXOFFHANDDAMAGE                      |                                                                                                              |
| 74    | UNIT_FIELD_BYTES_1                               | (stealthFlag << 16) &#124; (petTalentPoints << 8) &#124; ([standState](#standState))                         |
| 75    | UNIT_FIELD_PETNUMBER                             |                                                                                                              |
| 76    | UNIT_FIELD_PET_NAME_TIMESTAMP                    |                                                                                                              |
| 77    | UNIT_FIELD_PETEXPERIENCE                         |                                                                                                              |
| 78    | UNIT_FIELD_PETNEXTLEVELEXP                       |                                                                                                              |
| 79    | UNIT_DYNAMIC_FLAGS                               |                                                                                                              |
| 80    | UNIT_CHANNEL_SPELL                               |                                                                                                              |
| 81    | UNIT_MOD_CAST_SPEED                              | Units cast speed multiplier (float)                                                                          |
| 82    | UNIT_CREATED_BY_SPELL                            |                                                                                                              |
| 83    | UNIT_NPC_FLAGS                                   | npc flag]]                                                                                                   |
| 84    | UNIT_NPC_EMOTESTATE                              |                                                                                                              |
| 85    | UNIT_FIELD_STAT0                                 | Base strength (before any item bonuses)                                                                      |
| 86    | UNIT_FIELD_STAT1                                 | Base agility                                                                                                 |
| 87    | UNIT_FIELD_STAT2                                 | Base stamina                                                                                                 |
| 88    | UNIT_FIELD_STAT3                                 | Base intellect                                                                                               |
| 89    | UNIT_FIELD_STAT4                                 | Base spirit                                                                                                  |
| 90    | UNIT_FIELD_POSSTAT0                              |                                                                                                              |
| 91    | UNIT_FIELD_POSSTAT1                              |                                                                                                              |
| 92    | UNIT_FIELD_POSSTAT2                              |                                                                                                              |
| 93    | UNIT_FIELD_POSSTAT3                              |                                                                                                              |
| 94    | UNIT_FIELD_POSSTAT4                              |                                                                                                              |
| 95    | UNIT_FIELD_NEGSTAT0                              |                                                                                                              |
| 96    | UNIT_FIELD_NEGSTAT1                              |                                                                                                              |
| 97    | UNIT_FIELD_NEGSTAT2                              |                                                                                                              |
| 98    | UNIT_FIELD_NEGSTAT3                              |                                                                                                              |
| 99    | UNIT_FIELD_NEGSTAT4                              |                                                                                                              |
| 100   | UNIT_FIELD_RESISTANCES                           | Base armor (before any item bonuses)                                                                         |
| 101   |                                                  | Base holy resistance                                                                                         |
| 102   |                                                  | Base fire resistance                                                                                         |
| 103   |                                                  | Base nature resistance                                                                                       |
| 104   |                                                  | Base frost resistance                                                                                        |
| 105   |                                                  | Base shadow resistance                                                                                       |
| 106   |                                                  | Base arcane resistance                                                                                       |
| 107   | UNIT_FIELD_RESISTANCEBUFFMODSPOSITIVE            |                                                                                                              |
| 114   | UNIT_FIELD_RESISTANCEBUFFMODSNEGATIVE            |                                                                                                              |
| 121   | UNIT_FIELD_BASE_MANA                             |                                                                                                              |
| 122   | UNIT_FIELD_BASE_HEALTH                           |                                                                                                              |
| 123   | UNIT_FIELD_BYTES_2                               | ([unitRename](#unitRename) << 16) &#124; ([unitFlags](#unitFlags) << 8) &#124; ([sheathState](#sheathState)) |
| 124   | UNIT_FIELD_ATTACK_POWER                          |                                                                                                              |
| 125   | UNIT_FIELD_ATTACK_POWER_MODS                     |                                                                                                              |
| 126   | UNIT_FIELD_ATTACK_POWER_MULTIPLIER               |                                                                                                              |
| 127   | UNIT_FIELD_RANGED_ATTACK_POWER                   |                                                                                                              |
| 128   | UNIT_FIELD_RANGED_ATTACK_POWER_MODS              |                                                                                                              |
| 129   | UNIT_FIELD_RANGED_ATTACK_POWER_MULTIPLIER        |                                                                                                              |
| 130   | UNIT_FIELD_MINRANGEDDAMAGE                       |                                                                                                              |
| 131   | UNIT_FIELD_MAXRANGEDDAMAGE                       |                                                                                                              |
| 132   | UNIT_FIELD_POWER_COST_MODIFIER                   |                                                                                                              |
| 139   | UNIT_FIELD_POWER_COST_MULTIPLIER                 |                                                                                                              |
| 146   | UNIT_FIELD_MAXHEALTHMODIFIER                     |                                                                                                              |
| 147   | UNIT_FIELD_HOVERHEIGHT                           |                                                                                                              |
| 148   | UNIT_FIELD_PADDING                               |                                                                                                              |
| 149   | PLAYER_DUEL_ARBITER                              | GUID of the players duel flag (if in a duel)                                                                 |
| 151   | PLAYER_FLAGS                                     |                                                                                                              |
| 152   | PLAYER_GUILDID                                   | Id of guild the player is in (guild.guildid)                                                                 |
| 153   | PLAYER_GUILDRANK                                 | The player's rank ID (guild_rank.rid)                                                                        |
| 154   | PLAYER_BYTES                                     | (hairStyle << 16) &#124; (face << 8) &#124; (skin)                                                           |
| 155   | PLAYER_BYTES_2                                   | (maxslot << 16) &#124; (unused << 8) &#124; (facialHair)                                                     |
| 156   | PLAYER_BYTES_3                                   | gender, drunken state                                                                                        |
| 157   | PLAYER_DUEL_TEAM                                 |                                                                                                              |
| 158   | PLAYER_GUILD_TIMESTAMP                           |                                                                                                              |
| 159   | PLAYER_QUEST_LOG_1_1                             |                                                                                                              |
| 160   | PLAYER_QUEST_LOG_1_2                             |                                                                                                              |
| 161   | PLAYER_QUEST_LOG_1_3                             |                                                                                                              |
| 162   | PLAYER_QUEST_LOG_1_4                             |                                                                                                              |
| 163   | PLAYER_QUEST_LOG_2_1                             |                                                                                                              |
| 164   | PLAYER_QUEST_LOG_2_2                             |                                                                                                              |
| 165   | PLAYER_QUEST_LOG_2_3                             |                                                                                                              |
| 166   | PLAYER_QUEST_LOG_2_4                             |                                                                                                              |
| 167   | PLAYER_QUEST_LOG_3_1                             |                                                                                                              |
| 168   | PLAYER_QUEST_LOG_3_2                             |                                                                                                              |
| 169   | PLAYER_QUEST_LOG_3_3                             |                                                                                                              |
| 170   | PLAYER_QUEST_LOG_3_4                             |                                                                                                              |
| 171   | PLAYER_QUEST_LOG_4_1                             |                                                                                                              |
| 172   | PLAYER_QUEST_LOG_4_2                             |                                                                                                              |
| 173   | PLAYER_QUEST_LOG_4_3                             |                                                                                                              |
| 174   | PLAYER_QUEST_LOG_4_4                             |                                                                                                              |
| 175   | PLAYER_QUEST_LOG_5_1                             |                                                                                                              |
| 176   | PLAYER_QUEST_LOG_5_2                             |                                                                                                              |
| 177   | PLAYER_QUEST_LOG_5_3                             |                                                                                                              |
| 178   | PLAYER_QUEST_LOG_5_4                             |                                                                                                              |
| 179   | PLAYER_QUEST_LOG_6_1                             |                                                                                                              |
| 180   | PLAYER_QUEST_LOG_6_2                             |                                                                                                              |
| 181   | PLAYER_QUEST_LOG_6_3                             |                                                                                                              |
| 182   | PLAYER_QUEST_LOG_6_4                             |                                                                                                              |
| 183   | PLAYER_QUEST_LOG_7_1                             |                                                                                                              |
| 184   | PLAYER_QUEST_LOG_7_2                             |                                                                                                              |
| 185   | PLAYER_QUEST_LOG_7_3                             |                                                                                                              |
| 186   | PLAYER_QUEST_LOG_7_4                             |                                                                                                              |
| 187   | PLAYER_QUEST_LOG_8_1                             |                                                                                                              |
| 188   | PLAYER_QUEST_LOG_8_2                             |                                                                                                              |
| 189   | PLAYER_QUEST_LOG_8_3                             |                                                                                                              |
| 190   | PLAYER_QUEST_LOG_8_4                             |                                                                                                              |
| 191   | PLAYER_QUEST_LOG_9_1                             |                                                                                                              |
| 192   | PLAYER_QUEST_LOG_9_2                             |                                                                                                              |
| 193   | PLAYER_QUEST_LOG_9_3                             |                                                                                                              |
| 194   | PLAYER_QUEST_LOG_9_4                             |                                                                                                              |
| 195   | PLAYER_QUEST_LOG_10_1                            |                                                                                                              |
| 196   | PLAYER_QUEST_LOG_10_2                            |                                                                                                              |
| 197   | PLAYER_QUEST_LOG_10_3                            |                                                                                                              |
| 198   | PLAYER_QUEST_LOG_10_4                            |                                                                                                              |
| 199   | PLAYER_QUEST_LOG_11_1                            |                                                                                                              |
| 200   | PLAYER_QUEST_LOG_11_2                            |                                                                                                              |
| 201   | PLAYER_QUEST_LOG_11_3                            |                                                                                                              |
| 202   | PLAYER_QUEST_LOG_11_4                            |                                                                                                              |
| 203   | PLAYER_QUEST_LOG_12_1                            |                                                                                                              |
| 204   | PLAYER_QUEST_LOG_12_2                            |                                                                                                              |
| 205   | PLAYER_QUEST_LOG_12_3                            |                                                                                                              |
| 206   | PLAYER_QUEST_LOG_12_4                            |                                                                                                              |
| 207   | PLAYER_QUEST_LOG_13_1                            |                                                                                                              |
| 208   | PLAYER_QUEST_LOG_13_2                            |                                                                                                              |
| 209   | PLAYER_QUEST_LOG_13_3                            |                                                                                                              |
| 210   | PLAYER_QUEST_LOG_13_4                            |                                                                                                              |
| 211   | PLAYER_QUEST_LOG_14_1                            |                                                                                                              |
| 212   | PLAYER_QUEST_LOG_14_2                            |                                                                                                              |
| 213   | PLAYER_QUEST_LOG_14_3                            |                                                                                                              |
| 214   | PLAYER_QUEST_LOG_14_4                            |                                                                                                              |
| 215   | PLAYER_QUEST_LOG_15_1                            |                                                                                                              |
| 216   | PLAYER_QUEST_LOG_15_2                            |                                                                                                              |
| 217   | PLAYER_QUEST_LOG_15_3                            |                                                                                                              |
| 218   | PLAYER_QUEST_LOG_15_4                            |                                                                                                              |
| 219   | PLAYER_QUEST_LOG_16_1                            |                                                                                                              |
| 220   | PLAYER_QUEST_LOG_16_2                            |                                                                                                              |
| 221   | PLAYER_QUEST_LOG_16_3                            |                                                                                                              |
| 222   | PLAYER_QUEST_LOG_16_4                            |                                                                                                              |
| 223   | PLAYER_QUEST_LOG_17_1                            |                                                                                                              |
| 224   | PLAYER_QUEST_LOG_17_2                            |                                                                                                              |
| 225   | PLAYER_QUEST_LOG_17_3                            |                                                                                                              |
| 226   | PLAYER_QUEST_LOG_17_4                            |                                                                                                              |
| 227   | PLAYER_QUEST_LOG_18_1                            |                                                                                                              |
| 228   | PLAYER_QUEST_LOG_18_2                            |                                                                                                              |
| 229   | PLAYER_QUEST_LOG_18_3                            |                                                                                                              |
| 230   | PLAYER_QUEST_LOG_18_4                            |                                                                                                              |
| 231   | PLAYER_QUEST_LOG_19_1                            |                                                                                                              |
| 232   | PLAYER_QUEST_LOG_19_2                            |                                                                                                              |
| 233   | PLAYER_QUEST_LOG_19_3                            |                                                                                                              |
| 234   | PLAYER_QUEST_LOG_19_4                            |                                                                                                              |
| 235   | PLAYER_QUEST_LOG_20_1                            |                                                                                                              |
| 236   | PLAYER_QUEST_LOG_20_2                            |                                                                                                              |
| 237   | PLAYER_QUEST_LOG_20_3                            |                                                                                                              |
| 238   | PLAYER_QUEST_LOG_20_4                            |                                                                                                              |
| 239   | PLAYER_QUEST_LOG_21_1                            |                                                                                                              |
| 240   | PLAYER_QUEST_LOG_21_2                            |                                                                                                              |
| 241   | PLAYER_QUEST_LOG_21_3                            |                                                                                                              |
| 242   | PLAYER_QUEST_LOG_21_4                            |                                                                                                              |
| 243   | PLAYER_QUEST_LOG_22_1                            |                                                                                                              |
| 244   | PLAYER_QUEST_LOG_22_2                            |                                                                                                              |
| 245   | PLAYER_QUEST_LOG_22_3                            |                                                                                                              |
| 246   | PLAYER_QUEST_LOG_22_4                            |                                                                                                              |
| 247   | PLAYER_QUEST_LOG_23_1                            |                                                                                                              |
| 248   | PLAYER_QUEST_LOG_23_2                            |                                                                                                              |
| 249   | PLAYER_QUEST_LOG_23_3                            |                                                                                                              |
| 250   | PLAYER_QUEST_LOG_23_4                            |                                                                                                              |
| 251   | PLAYER_QUEST_LOG_24_1                            |                                                                                                              |
| 252   | PLAYER_QUEST_LOG_24_2                            |                                                                                                              |
| 253   | PLAYER_QUEST_LOG_24_3                            |                                                                                                              |
| 254   | PLAYER_QUEST_LOG_24_4                            |                                                                                                              |
| 255   | PLAYER_QUEST_LOG_25_1                            |                                                                                                              |
| 256   | PLAYER_QUEST_LOG_25_2                            |                                                                                                              |
| 257   | PLAYER_QUEST_LOG_25_3                            |                                                                                                              |
| 258   | PLAYER_QUEST_LOG_25_4                            |                                                                                                              |
| 259   | PLAYER_VISIBLE_ITEM_1_CREATOR                    |                                                                                                              |
| 261   | PLAYER_VISIBLE_ITEM_1_0                          | Item ID equipped on head slot                                                                                |
| 274   | PLAYER_VISIBLE_ITEM_1_PROPERTIES                 |                                                                                                              |
| 275   | PLAYER_VISIBLE_ITEM_1_SEED                       |                                                                                                              |
| 276   | PLAYER_VISIBLE_ITEM_1_PAD                        |                                                                                                              |
| 277   | PLAYER_VISIBLE_ITEM_2_CREATOR                    |                                                                                                              |
| 279   | PLAYER_VISIBLE_ITEM_2_0                          | Item ID equipped on neck slot                                                                                |
| 292   | PLAYER_VISIBLE_ITEM_2_PROPERTIES                 |                                                                                                              |
| 293   | PLAYER_VISIBLE_ITEM_2_SEED                       |                                                                                                              |
| 294   | PLAYER_VISIBLE_ITEM_2_PAD                        |                                                                                                              |
| 295   | PLAYER_VISIBLE_ITEM_3_CREATOR                    |                                                                                                              |
| 297   | PLAYER_VISIBLE_ITEM_3_0                          | Item ID equipped on shoulder slot                                                                            |
| 310   | PLAYER_VISIBLE_ITEM_3_PROPERTIES                 |                                                                                                              |
| 311   | PLAYER_VISIBLE_ITEM_3_SEED                       |                                                                                                              |
| 312   | PLAYER_VISIBLE_ITEM_3_PAD                        |                                                                                                              |
| 313   | PLAYER_VISIBLE_ITEM_4_CREATOR                    |                                                                                                              |
| 315   | PLAYER_VISIBLE_ITEM_4_0                          | Item ID equipped on shirt slot                                                                               |
| 328   | PLAYER_VISIBLE_ITEM_4_PROPERTIES                 |                                                                                                              |
| 329   | PLAYER_VISIBLE_ITEM_4_SEED                       |                                                                                                              |
| 330   | PLAYER_VISIBLE_ITEM_4_PAD                        |                                                                                                              |
| 331   | PLAYER_VISIBLE_ITEM_5_CREATOR                    |                                                                                                              |
| 333   | PLAYER_VISIBLE_ITEM_5_0                          | Item ID equipped on chest slot                                                                               |
| 346   | PLAYER_VISIBLE_ITEM_5_PROPERTIES                 |                                                                                                              |
| 347   | PLAYER_VISIBLE_ITEM_5_SEED                       |                                                                                                              |
| 348   | PLAYER_VISIBLE_ITEM_5_PAD                        |                                                                                                              |
| 349   | PLAYER_VISIBLE_ITEM_6_CREATOR                    |                                                                                                              |
| 351   | PLAYER_VISIBLE_ITEM_6_0                          | Item ID equipped on belt slot                                                                                |
| 364   | PLAYER_VISIBLE_ITEM_6_PROPERTIES                 |                                                                                                              |
| 365   | PLAYER_VISIBLE_ITEM_6_SEED                       |                                                                                                              |
| 366   | PLAYER_VISIBLE_ITEM_6_PAD                        |                                                                                                              |
| 367   | PLAYER_VISIBLE_ITEM_7_CREATOR                    |                                                                                                              |
| 369   | PLAYER_VISIBLE_ITEM_7_0                          | Item ID equipped on legs slot                                                                                |
| 382   | PLAYER_VISIBLE_ITEM_7_PROPERTIES                 |                                                                                                              |
| 383   | PLAYER_VISIBLE_ITEM_7_SEED                       |                                                                                                              |
| 384   | PLAYER_VISIBLE_ITEM_7_PAD                        |                                                                                                              |
| 385   | PLAYER_VISIBLE_ITEM_8_CREATOR                    |                                                                                                              |
| 387   | PLAYER_VISIBLE_ITEM_8_0                          | Item ID equipped on feet slot                                                                                |
| 400   | PLAYER_VISIBLE_ITEM_8_PROPERTIES                 |                                                                                                              |
| 401   | PLAYER_VISIBLE_ITEM_8_SEED                       |                                                                                                              |
| 402   | PLAYER_VISIBLE_ITEM_8_PAD                        |                                                                                                              |
| 403   | PLAYER_VISIBLE_ITEM_9_CREATOR                    |                                                                                                              |
| 405   | PLAYER_VISIBLE_ITEM_9_0                          | Item ID equipped on wrist slot                                                                               |
| 418   | PLAYER_VISIBLE_ITEM_9_PROPERTIES                 |                                                                                                              |
| 419   | PLAYER_VISIBLE_ITEM_9_SEED                       |                                                                                                              |
| 420   | PLAYER_VISIBLE_ITEM_9_PAD                        |                                                                                                              |
| 421   | PLAYER_VISIBLE_ITEM_10_CREATOR                   |                                                                                                              |
| 423   | PLAYER_VISIBLE_ITEM_10_0                         | Item ID equipped on gloves slot                                                                              |
| 436   | PLAYER_VISIBLE_ITEM_10_PROPERTIES                |                                                                                                              |
| 437   | PLAYER_VISIBLE_ITEM_10_SEED                      |                                                                                                              |
| 438   | PLAYER_VISIBLE_ITEM_10_PAD                       |                                                                                                              |
| 439   | PLAYER_VISIBLE_ITEM_11_CREATOR                   |                                                                                                              |
| 441   | PLAYER_VISIBLE_ITEM_11_0                         | Item ID equipped on finger 1 slot                                                                            |
| 454   | PLAYER_VISIBLE_ITEM_11_PROPERTIES                |                                                                                                              |
| 455   | PLAYER_VISIBLE_ITEM_11_SEED                      |                                                                                                              |
| 456   | PLAYER_VISIBLE_ITEM_11_PAD                       |                                                                                                              |
| 457   | PLAYER_VISIBLE_ITEM_12_CREATOR                   |                                                                                                              |
| 459   | PLAYER_VISIBLE_ITEM_12_0                         | Item ID equipped on finger 2 slot                                                                            |
| 472   | PLAYER_VISIBLE_ITEM_12_PROPERTIES                |                                                                                                              |
| 473   | PLAYER_VISIBLE_ITEM_12_SEED                      |                                                                                                              |
| 474   | PLAYER_VISIBLE_ITEM_12_PAD                       |                                                                                                              |
| 475   | PLAYER_VISIBLE_ITEM_13_CREATOR                   |                                                                                                              |
| 477   | PLAYER_VISIBLE_ITEM_13_0                         | Item ID equipped on trinket 1 slot                                                                           |
| 490   | PLAYER_VISIBLE_ITEM_13_PROPERTIES                |                                                                                                              |
| 491   | PLAYER_VISIBLE_ITEM_13_SEED                      |                                                                                                              |
| 492   | PLAYER_VISIBLE_ITEM_13_PAD                       |                                                                                                              |
| 493   | PLAYER_VISIBLE_ITEM_14_CREATOR                   |                                                                                                              |
| 495   | PLAYER_VISIBLE_ITEM_14_0                         | Item ID equipped on trinket 2 slot                                                                           |
| 508   | PLAYER_VISIBLE_ITEM_14_PROPERTIES                |                                                                                                              |
| 509   | PLAYER_VISIBLE_ITEM_14_SEED                      |                                                                                                              |
| 510   | PLAYER_VISIBLE_ITEM_14_PAD                       |                                                                                                              |
| 511   | PLAYER_VISIBLE_ITEM_15_CREATOR                   |                                                                                                              |
| 513   | PLAYER_VISIBLE_ITEM_15_0                         | Item ID equipped on back slot                                                                                |
| 526   | PLAYER_VISIBLE_ITEM_15_PROPERTIES                |                                                                                                              |
| 527   | PLAYER_VISIBLE_ITEM_15_SEED                      |                                                                                                              |
| 528   | PLAYER_VISIBLE_ITEM_15_PAD                       |                                                                                                              |
| 529   | PLAYER_VISIBLE_ITEM_16_CREATOR                   |                                                                                                              |
| 531   | PLAYER_VISIBLE_ITEM_16_0                         | Item ID equipped on main hand slot                                                                           |
| 544   | PLAYER_VISIBLE_ITEM_16_PROPERTIES                |                                                                                                              |
| 545   | PLAYER_VISIBLE_ITEM_16_SEED                      |                                                                                                              |
| 546   | PLAYER_VISIBLE_ITEM_16_PAD                       |                                                                                                              |
| 547   | PLAYER_VISIBLE_ITEM_17_CREATOR                   |                                                                                                              |
| 549   | PLAYER_VISIBLE_ITEM_17_0                         | Item ID equipped on off hand slot                                                                            |
| 562   | PLAYER_VISIBLE_ITEM_17_PROPERTIES                |                                                                                                              |
| 563   | PLAYER_VISIBLE_ITEM_17_SEED                      |                                                                                                              |
| 564   | PLAYER_VISIBLE_ITEM_17_PAD                       |                                                                                                              |
| 565   | PLAYER_VISIBLE_ITEM_18_CREATOR                   |                                                                                                              |
| 567   | PLAYER_VISIBLE_ITEM_18_0                         | Item ID equipped on ranged slot                                                                              |
| 580   | PLAYER_VISIBLE_ITEM_18_PROPERTIES                |                                                                                                              |
| 581   | PLAYER_VISIBLE_ITEM_18_SEED                      |                                                                                                              |
| 582   | PLAYER_VISIBLE_ITEM_18_PAD                       |                                                                                                              |
| 583   | PLAYER_VISIBLE_ITEM_19_CREATOR                   |                                                                                                              |
| 585   | PLAYER_VISIBLE_ITEM_19_0                         | Item ID equipped on tabard                                                                                   |
| 598   | PLAYER_VISIBLE_ITEM_19_PROPERTIES                |                                                                                                              |
| 599   | PLAYER_VISIBLE_ITEM_19_SEED                      |                                                                                                              |
| 600   | PLAYER_VISIBLE_ITEM_19_PAD                       |                                                                                                              |
| 601   | PLAYER_CHOSEN_TITLE                              |                                                                                                              |
| 602   | PLAYER_FIELD_PAD_0                               |                                                                                                              |
| 603   | PLAYER_FIELD_INV_SLOT_HEAD                       |                                                                                                              |
| 649   | PLAYER_FIELD_PACK_SLOT_1                         |                                                                                                              |
| 681   | PLAYER_FIELD_BANK_SLOT_1                         |                                                                                                              |
| 737   | PLAYER_FIELD_BANKBAG_SLOT_1                      |                                                                                                              |
| 751   | PLAYER_FIELD_VENDORBUYBACK_SLOT_1                |                                                                                                              |
| 775   | PLAYER_FIELD_KEYRING_SLOT_1                      |                                                                                                              |
| 839   | PLAYER_FIELD_VANITYPET_SLOT_1                    |                                                                                                              |
| 875   | PLAYER_FIELD_CURRENCYTOKEN_SLOT_1                |                                                                                                              |
| 939   | PLAYER_FIELD_QUESTBAG_SLOT_1                     |                                                                                                              |
| 1003  | PLAYER_FARSIGHT                                  |                                                                                                              |
| 1005  | PLAYER__FIELD_KNOWN_TITLES                       |                                                                                                              |
| 1007  | PLAYER__FIELD_KNOWN_TITLES1                      |                                                                                                              |
| 1009  | PLAYER_FIELD_KNOWN_CURRENCIES                    |                                                                                                              |
| 1011  | PLAYER_XP                                        |                                                                                                              |
| 1012  | PLAYER_NEXT_LEVEL_XP                             |                                                                                                              |
| 1013  | PLAYER_SKILL_INFO_1_1                            |                                                                                                              |
| 1397  | PLAYER_CHARACTER_POINTS1                         |                                                                                                              |
| 1398  | PLAYER_CHARACTER_POINTS2                         |                                                                                                              |
| 1399  | PLAYER_TRACK_CREATURES                           |                                                                                                              |
| 1400  | PLAYER_TRACK_RESOURCES                           |                                                                                                              |
| 1401  | PLAYER_BLOCK_PERCENTAGE                          |                                                                                                              |
| 1402  | PLAYER_DODGE_PERCENTAGE                          |                                                                                                              |
| 1403  | PLAYER_PARRY_PERCENTAGE                          |                                                                                                              |
| 1404  | PLAYER_EXPERTISE                                 |                                                                                                              |
| 1405  | PLAYER_OFFHAND_EXPERTISE                         |                                                                                                              |
| 1406  | PLAYER_CRIT_PERCENTAGE                           |                                                                                                              |
| 1407  | PLAYER_RANGED_CRIT_PERCENTAGE                    |                                                                                                              |
| 1408  | PLAYER_OFFHAND_CRIT_PERCENTAGE                   |                                                                                                              |
| 1409  | PLAYER_SPELL_CRIT_PERCENTAGE1                    |                                                                                                              |
| 1416  | PLAYER_SHIELD_BLOCK                              |                                                                                                              |
| 1417  | PLAYER_SHIELD_BLOCK_CRIT_PERCENTAGE              |                                                                                                              |
| 1418  | PLAYER_EXPLORED_ZONES_1                          |                                                                                                              |
| 1546  | PLAYER_REST_STATE_EXPERIENCE                     |                                                                                                              |
| 1547  | PLAYER_FIELD_COINAGE                             | Money the player currently has (in copper).                                                                  |
| 1548  | PLAYER_FIELD_MOD_DAMAGE_DONE_POS                 |                                                                                                              |
| 1555  | PLAYER_FIELD_MOD_DAMAGE_DONE_NEG                 |                                                                                                              |
| 1562  | PLAYER_FIELD_MOD_DAMAGE_DONE_PCT                 |                                                                                                              |
| 1569  | PLAYER_FIELD_MOD_HEALING_DONE_POS                |                                                                                                              |
| 1570  | PLAYER_FIELD_MOD_TARGET_RESISTANCE               |                                                                                                              |
| 1571  | PLAYER_FIELD_MOD_TARGET_PHYSICAL_RESISTANCE      |                                                                                                              |
| 1572  | PLAYER_FIELD_BYTES                               |                                                                                                              |
| 1573  | PLAYER_AMMO_ID                                   |                                                                                                              |
| 1574  | PLAYER_SELF_RES_SPELL                            |                                                                                                              |
| 1575  | PLAYER_FIELD_PVP_MEDALS                          |                                                                                                              |
| 1576  | PLAYER_FIELD_BUYBACK_PRICE_1                     |                                                                                                              |
| 1588  | PLAYER_FIELD_BUYBACK_TIMESTAMP_1                 |                                                                                                              |
| 1600  | PLAYER_FIELD_KILLS                               |                                                                                                              |
| 1601  | PLAYER_FIELD_TODAY_CONTRIBUTION                  |                                                                                                              |
| 1602  | PLAYER_FIELD_YESTERDAY_CONTRIBUTION              |                                                                                                              |
| 1603  | PLAYER_FIELD_LIFETIME_HONORBALE_KILLS            |                                                                                                              |
| 1604  | PLAYER_FIELD_BYTES2                              |                                                                                                              |
| 1605  | PLAYER_FIELD_WATCHED_FACTION_INDEX               |                                                                                                              |
| 1606  | PLAYER_FIELD_COMBAT_RATING_1                     |                                                                                                              |
| 1631  | PLAYER_FIELD_ARENA_TEAM_INFO_1_1                 |                                                                                                              |
| 1649  | PLAYER_FIELD_HONOR_CURRENCY                      |                                                                                                              |
| 1650  | PLAYER_FIELD_ARENA_CURRENCY                      |                                                                                                              |
| 1651  | PLAYER_FIELD_MAX_LEVEL                           |                                                                                                              |
| 1652  | PLAYER_FIELD_DAILY_QUESTS_1                      |                                                                                                              |
| 1677  | PLAYER_RUNE_REGEN_1                              |                                                                                                              |
| 1681  | PLAYER_NO_REAGENT_COST_1                         |                                                                                                              |
| 1684  | PLAYER_FIELD_GLYPH_SLOTS_1                       |                                                                                                              |
| 1692  | PLAYER_FIELD_GLYPHS_1                            |                                                                                                              |
| 1700  | PLAYER_GLYPHS_ENABLED                            |                                                                                                              |

### Flags

#### standState

    PLAYER_STATE_NONE              = 0
    PLAYER_STATE_SIT               = 1
    PLAYER_STATE_SIT_CHAIR         = 2
    PLAYER_STATE_SLEEP             = 3
    PLAYER_STATE_SIT_LOW_CHAIR     = 4
    PLAYER_STATE_SIT_MEDIUM_CHAIR  = 5
    PLAYER_STATE_SIT_HIGH_CHAIR    = 6
    PLAYER_STATE_DEAD              = 7
    PLAYER_STATE_KNEEL             = 8
    PLAYER_STATE_FORM_ALL          = 0x00FF0000

#### standFlags

    PLAYER_STATE_FLAG_ALWAYS_STAND = 0x01             // byte 4
    PLAYER_STATE_FLAG_CREEP        = 0x02000000
    PLAYER_STATE_FLAG_UNTRACKABLE  = 0x04000000
    PLAYER_STATE_FLAG_ALL          = 0xFF000000

#### sheathState

    SHEATH_STATE_UNARMED  = 0 // non prepared weapon
    SHEATH_STATE_MELEE    = 1 // prepared melee weapon
    SHEATH_STATE_RANGED   = 2 // prepared ranged weapon

#### unitFlags

    UNIT_BYTE2_FLAG_PVP         = 0x01
    UNIT_BYTE2_FLAG_UNK1        = 0x02
    UNIT_BYTE2_FLAG_FFA_PVP     = 0x04
    UNIT_BYTE2_FLAG_SANCTUARY   = 0x08
    UNIT_BYTE2_FLAG_UNK4        = 0x10
    UNIT_BYTE2_FLAG_UNK5        = 0x20
    UNIT_BYTE2_FLAG_UNK6        = 0x40
    UNIT_BYTE2_FLAG_UNK7        = 0x80

#### unitRename

    UNIT_RENAME_NOT_ALLOWED = 0x02
    UNIT_RENAME_ALLOWED     = 0x03

#### shapeshiftForm

    FORM_NONE               = 0x00
    FORM_CAT                = 0x01
    FORM_TREE               = 0x02
    FORM_TRAVEL             = 0x03
    FORM_AQUA               = 0x04
    FORM_BEAR               = 0x05
    FORM_AMBIENT            = 0x06
    FORM_GHOUL              = 0x07
    FORM_DIREBEAR           = 0x08
    FORM_CREATUREBEAR       = 0x0E
    FORM_CREATURECAT        = 0x0F
    FORM_GHOSTWOLF          = 0x10
    FORM_BATTLESTANCE       = 0x11
    FORM_DEFENSIVESTANCE    = 0x12
    FORM_BERSERKERSTANCE    = 0x13
    FORM_TEST               = 0x14
    FORM_ZOMBIE             = 0x15
    FORM_METAMORPHOSIS      = 0x16
    FORM_FLIGHT_EPIC        = 0x1B
    FORM_SHADOW             = 0x1C
    FORM_FLIGHT             = 0x1D
    FORM_STEALTH            = 0x1E
    FORM_MOONKIN            = 0x1F
    FORM_SPIRITOFREDEMPTION = 0x20

#### restState

    rested = 0x01
    normal = 0x02

### 2.4.1 Character Data Table

**This table was last updated for 2.4.1 values.**

| Index | Value Name                                  | Comments                                                                           |
| ----- | ------------------------------------------- | ---------------------------------------------------------------------------------- |
| 0     | OBJECT_FIELD_GUID                           | Character GUID (full GUID includes both index 0 and index 1 as 64bit number)       |
| 2     | OBJECT_FIELD_TYPE                           |                                                                                    |
| 3     | OBJECT_FIELD_ENTRY                          |                                                                                    |
| 4     | OBJECT_FIELD_SCALE_X                        | Size of how model appears in-game (float value)                                    |
| 5     | OBJECT_FIELD_PADDING                        |                                                                                    |
| 6     | UNIT_FIELD_CHARM                            |                                                                                    |
| 8     | UNIT_FIELD_SUMMON                           |                                                                                    |
| 10    | UNIT_FIELD_CHARMEDBY                        |                                                                                    |
| 12    | UNIT_FIELD_SUMMONEDBY                       |                                                                                    |
| 14    | UNIT_FIELD_CREATEDBY                        |                                                                                    |
| 16    | UNIT_FIELD_TARGET                           |                                                                                    |
| 18    | UNIT_FIELD_PERSUADED                        |                                                                                    |
| 20    | UNIT_FIELD_CHANNEL_OBJECT                   |                                                                                    |
| 22    | UNIT_FIELD_HEALTH                           | Current health                                                                     |
| 23    | UNIT_FIELD_POWER1                           | Current mana                                                                       |
| 24    | UNIT_FIELD_POWER2                           | Current rage                                                                       |
| 25    | UNIT_FIELD_POWER3                           | Current focus                                                                      |
| 26    | UNIT_FIELD_POWER4                           | Current energy                                                                     |
| 27    | UNIT_FIELD_POWER5                           | Current happiness                                                                  |
| 28    | UNIT_FIELD_MAXHEALTH                        | Max health                                                                         |
| 29    | UNIT_FIELD_MAXPOWER1                        | Max mana                                                                           |
| 30    | UNIT_FIELD_MAXPOWER2                        | Max rage                                                                           |
| 31    | UNIT_FIELD_MAXPOWER3                        | Max focus                                                                          |
| 32    | UNIT_FIELD_MAXPOWER4                        | Max energy                                                                         |
| 33    | UNIT_FIELD_MAXPOWER5                        | Max happiness                                                                      |
| 34    | UNIT_FIELD_LEVEL                            | Character level                                                                    |
| 35    | UNIT_FIELD_FACTIONTEMPLATE                  | Currently used faction template ID ([FactionTemplate.dbc](FactionTemplate.dbc))    |
| 36    | UNIT_FIELD_BYTES_0                          | (class_ << 8) &#124; (gender << 16) &#124; (powertype << 24)                       |
| 37    | UNIT_VIRTUAL_ITEM_SLOT_DISPLAY              |                                                                                    |
| 40    | UNIT_VIRTUAL_ITEM_INFO                      |                                                                                    |
| 46    | UNIT_FIELD_FLAGS                            |                                                                                    |
| 47    | UNIT_FIELD_FLAGS_2                          |                                                                                    |
| 48    | UNIT_FIELD_AURA                             |                                                                                    |
| 104   | UNIT_FIELD_AURAFLAGS                        |                                                                                    |
| 118   | UNIT_FIELD_AURALEVELS                       |                                                                                    |
| 132   | UNIT_FIELD_AURAAPPLICATIONS                 |                                                                                    |
| 146   | UNIT_FIELD_AURASTATE                        |                                                                                    |
| 147   | UNIT_FIELD_BASEATTACKTIME                   |                                                                                    |
| 148   | UNIT_FIELD_OFFHANDATTACKTIME                |                                                                                    |
| 149   | UNIT_FIELD_RANGEDATTACKTIME                 |                                                                                    |
| 150   | UNIT_FIELD_BOUNDINGRADIUS                   |                                                                                    |
| 151   | UNIT_FIELD_COMBATREACH                      |                                                                                    |
| 152   | UNIT_FIELD_DISPLAYID                        | Current model ID (can be different from regular if character is morphed, etc)      |
| 153   | UNIT_FIELD_NATIVEDISPLAYID                  | The native model ID. Model always reverts to this number when player is demorphed. |
| 154   | UNIT_FIELD_MOUNTDISPLAYID                   |                                                                                    |
| 155   | UNIT_FIELD_MINDAMAGE                        |                                                                                    |
| 156   | UNIT_FIELD_MAXDAMAGE                        |                                                                                    |
| 157   | UNIT_FIELD_MINOFFHANDDAMAGE                 |                                                                                    |
| 158   | UNIT_FIELD_MAXOFFHANDDAMAGE                 |                                                                                    |
| 159   | UNIT_FIELD_BYTES_1                          |                                                                                    |
| 160   | UNIT_FIELD_PETNUMBER                        |                                                                                    |
| 161   | UNIT_FIELD_PET_NAME_TIMESTAMP               |                                                                                    |
| 162   | UNIT_FIELD_PETEXPERIENCE                    |                                                                                    |
| 163   | UNIT_FIELD_PETNEXTLEVELEXP                  |                                                                                    |
| 164   | UNIT_DYNAMIC_FLAGS                          |                                                                                    |
| 165   | UNIT_CHANNEL_SPELL                          |                                                                                    |
| 166   | UNIT_MOD_CAST_SPEED                         |                                                                                    |
| 167   | UNIT_CREATED_BY_SPELL                       |                                                                                    |
| 168   | UNIT_NPC_FLAGS                              |                                                                                    |
| 169   | UNIT_NPC_EMOTESTATE                         |                                                                                    |
| 170   | UNIT_TRAINING_POINTS                        |                                                                                    |
| 171   | UNIT_FIELD_STAT0                            | Base strength (before any item bonuses)                                            |
| 172   | UNIT_FIELD_STAT1                            | Base agility                                                                       |
| 173   | UNIT_FIELD_STAT2                            | Base stamina                                                                       |
| 174   | UNIT_FIELD_STAT3                            | Base intellect                                                                     |
| 175   | UNIT_FIELD_STAT4                            | Base spirit                                                                        |
| 176   | UNIT_FIELD_POSSTAT0                         |                                                                                    |
| 177   | UNIT_FIELD_POSSTAT1                         |                                                                                    |
| 178   | UNIT_FIELD_POSSTAT2                         |                                                                                    |
| 179   | UNIT_FIELD_POSSTAT3                         |                                                                                    |
| 180   | UNIT_FIELD_POSSTAT4                         |                                                                                    |
| 181   | UNIT_FIELD_NEGSTAT0                         |                                                                                    |
| 182   | UNIT_FIELD_NEGSTAT1                         |                                                                                    |
| 183   | UNIT_FIELD_NEGSTAT2                         |                                                                                    |
| 184   | UNIT_FIELD_NEGSTAT3                         |                                                                                    |
| 185   | UNIT_FIELD_NEGSTAT4                         |                                                                                    |
| 186   | UNIT_FIELD_RESISTANCES                      | Base armor (before any item bonuses)                                               |
| 187   |                                             | Base holy resistance                                                               |
| 188   |                                             | Base fire resistance                                                               |
| 189   |                                             | Base nature resistance                                                             |
| 190   |                                             | Base frost resistance                                                              |
| 191   |                                             | Base shadow resistance                                                             |
| 192   |                                             | Base arcane resistance                                                             |
| 193   | UNIT_FIELD_RESISTANCEBUFFMODSPOSITIVE       |                                                                                    |
| 200   | UNIT_FIELD_RESISTANCEBUFFMODSNEGATIVE       |                                                                                    |
| 207   | UNIT_FIELD_BASE_MANA                        |                                                                                    |
| 208   | UNIT_FIELD_BASE_HEALTH                      |                                                                                    |
| 209   | UNIT_FIELD_BYTES_2                          |                                                                                    |
| 210   | UNIT_FIELD_ATTACK_POWER                     |                                                                                    |
| 211   | UNIT_FIELD_ATTACK_POWER_MODS                |                                                                                    |
| 212   | UNIT_FIELD_ATTACK_POWER_MULTIPLIER          |                                                                                    |
| 213   | UNIT_FIELD_RANGED_ATTACK_POWER              |                                                                                    |
| 214   | UNIT_FIELD_RANGED_ATTACK_POWER_MODS         |                                                                                    |
| 215   | UNIT_FIELD_RANGED_ATTACK_POWER_MULTIPLIER   |                                                                                    |
| 216   | UNIT_FIELD_MINRANGEDDAMAGE                  |                                                                                    |
| 217   | UNIT_FIELD_MAXRANGEDDAMAGE                  |                                                                                    |
| 218   | UNIT_FIELD_POWER_COST_MODIFIER              |                                                                                    |
| 225   | UNIT_FIELD_POWER_COST_MULTIPLIER            |                                                                                    |
| 232   | UNIT_FIELD_MAXHEALTHMODIFIER                |                                                                                    |
| 233   | UNIT_FIELD_PADDING                          |                                                                                    |
| 234   | PLAYER_DUEL_ARBITER                         |                                                                                    |
| 236   | PLAYER_FLAGS                                |                                                                                    |
| 237   | PLAYER_GUILDID                              | guild.guildid]])                                                                   |
| 238   | PLAYER_GUILDRANK                            | guild_rank.rid]])                                                                  |
| 239   | PLAYER_BYTES                                | (face << 8) &#124; (hairStyle << 16) &#124; (hairColor << 24))                     |
| 240   | PLAYER_BYTES_2                              | (0x00 << 8) &#124; (0x00 << 16) &#124; (0x02 << 24)))                              |
| 241   | PLAYER_BYTES_3                              | gender                                                                             |
| 242   | PLAYER_DUEL_TEAM                            |                                                                                    |
| 243   | PLAYER_GUILD_TIMESTAMP                      |                                                                                    |
| 244   | PLAYER_QUEST_LOG_1_1                        |                                                                                    |
| 245   | PLAYER_QUEST_LOG_1_2                        |                                                                                    |
| 246   | PLAYER_QUEST_LOG_1_3                        |                                                                                    |
| 247   | PLAYER_QUEST_LOG_1_4                        |                                                                                    |
| 248   | PLAYER_QUEST_LOG_2_1                        |                                                                                    |
| 249   | PLAYER_QUEST_LOG_2_2                        |                                                                                    |
| 250   | PLAYER_QUEST_LOG_2_3                        |                                                                                    |
| 251   | PLAYER_QUEST_LOG_2_4                        |                                                                                    |
| 252   | PLAYER_QUEST_LOG_3_1                        |                                                                                    |
| 253   | PLAYER_QUEST_LOG_3_2                        |                                                                                    |
| 254   | PLAYER_QUEST_LOG_3_3                        |                                                                                    |
| 255   | PLAYER_QUEST_LOG_3_4                        |                                                                                    |
| 256   | PLAYER_QUEST_LOG_4_1                        |                                                                                    |
| 257   | PLAYER_QUEST_LOG_4_2                        |                                                                                    |
| 258   | PLAYER_QUEST_LOG_4_3                        |                                                                                    |
| 259   | PLAYER_QUEST_LOG_4_4                        |                                                                                    |
| 260   | PLAYER_QUEST_LOG_5_1                        |                                                                                    |
| 261   | PLAYER_QUEST_LOG_5_2                        |                                                                                    |
| 262   | PLAYER_QUEST_LOG_5_3                        |                                                                                    |
| 263   | PLAYER_QUEST_LOG_5_4                        |                                                                                    |
| 264   | PLAYER_QUEST_LOG_6_1                        |                                                                                    |
| 265   | PLAYER_QUEST_LOG_6_2                        |                                                                                    |
| 266   | PLAYER_QUEST_LOG_6_3                        |                                                                                    |
| 267   | PLAYER_QUEST_LOG_6_4                        |                                                                                    |
| 268   | PLAYER_QUEST_LOG_7_1                        |                                                                                    |
| 269   | PLAYER_QUEST_LOG_7_2                        |                                                                                    |
| 270   | PLAYER_QUEST_LOG_7_3                        |                                                                                    |
| 271   | PLAYER_QUEST_LOG_7_4                        |                                                                                    |
| 272   | PLAYER_QUEST_LOG_8_1                        |                                                                                    |
| 273   | PLAYER_QUEST_LOG_8_2                        |                                                                                    |
| 274   | PLAYER_QUEST_LOG_8_3                        |                                                                                    |
| 275   | PLAYER_QUEST_LOG_8_4                        |                                                                                    |
| 276   | PLAYER_QUEST_LOG_9_1                        |                                                                                    |
| 277   | PLAYER_QUEST_LOG_9_2                        |                                                                                    |
| 278   | PLAYER_QUEST_LOG_9_3                        |                                                                                    |
| 279   | PLAYER_QUEST_LOG_9_4                        |                                                                                    |
| 280   | PLAYER_QUEST_LOG_10_1                       |                                                                                    |
| 281   | PLAYER_QUEST_LOG_10_2                       |                                                                                    |
| 282   | PLAYER_QUEST_LOG_10_3                       |                                                                                    |
| 283   | PLAYER_QUEST_LOG_10_4                       |                                                                                    |
| 284   | PLAYER_QUEST_LOG_11_1                       |                                                                                    |
| 285   | PLAYER_QUEST_LOG_11_2                       |                                                                                    |
| 286   | PLAYER_QUEST_LOG_11_3                       |                                                                                    |
| 287   | PLAYER_QUEST_LOG_11_4                       |                                                                                    |
| 288   | PLAYER_QUEST_LOG_12_1                       |                                                                                    |
| 289   | PLAYER_QUEST_LOG_12_2                       |                                                                                    |
| 290   | PLAYER_QUEST_LOG_12_3                       |                                                                                    |
| 291   | PLAYER_QUEST_LOG_12_4                       |                                                                                    |
| 292   | PLAYER_QUEST_LOG_13_1                       |                                                                                    |
| 293   | PLAYER_QUEST_LOG_13_2                       |                                                                                    |
| 294   | PLAYER_QUEST_LOG_13_3                       |                                                                                    |
| 295   | PLAYER_QUEST_LOG_13_4                       |                                                                                    |
| 296   | PLAYER_QUEST_LOG_14_1                       |                                                                                    |
| 297   | PLAYER_QUEST_LOG_14_2                       |                                                                                    |
| 298   | PLAYER_QUEST_LOG_14_3                       |                                                                                    |
| 299   | PLAYER_QUEST_LOG_14_4                       |                                                                                    |
| 300   | PLAYER_QUEST_LOG_15_1                       |                                                                                    |
| 301   | PLAYER_QUEST_LOG_15_2                       |                                                                                    |
| 302   | PLAYER_QUEST_LOG_15_3                       |                                                                                    |
| 303   | PLAYER_QUEST_LOG_15_4                       |                                                                                    |
| 304   | PLAYER_QUEST_LOG_16_1                       |                                                                                    |
| 305   | PLAYER_QUEST_LOG_16_2                       |                                                                                    |
| 306   | PLAYER_QUEST_LOG_16_3                       |                                                                                    |
| 307   | PLAYER_QUEST_LOG_16_4                       |                                                                                    |
| 308   | PLAYER_QUEST_LOG_17_1                       |                                                                                    |
| 309   | PLAYER_QUEST_LOG_17_2                       |                                                                                    |
| 310   | PLAYER_QUEST_LOG_17_3                       |                                                                                    |
| 311   | PLAYER_QUEST_LOG_17_4                       |                                                                                    |
| 312   | PLAYER_QUEST_LOG_18_1                       |                                                                                    |
| 313   | PLAYER_QUEST_LOG_18_2                       |                                                                                    |
| 314   | PLAYER_QUEST_LOG_18_3                       |                                                                                    |
| 315   | PLAYER_QUEST_LOG_18_4                       |                                                                                    |
| 316   | PLAYER_QUEST_LOG_19_1                       |                                                                                    |
| 317   | PLAYER_QUEST_LOG_19_2                       |                                                                                    |
| 318   | PLAYER_QUEST_LOG_19_3                       |                                                                                    |
| 319   | PLAYER_QUEST_LOG_19_4                       |                                                                                    |
| 320   | PLAYER_QUEST_LOG_20_1                       |                                                                                    |
| 321   | PLAYER_QUEST_LOG_20_2                       |                                                                                    |
| 322   | PLAYER_QUEST_LOG_20_3                       |                                                                                    |
| 323   | PLAYER_QUEST_LOG_20_4                       |                                                                                    |
| 324   | PLAYER_QUEST_LOG_21_1                       |                                                                                    |
| 325   | PLAYER_QUEST_LOG_21_2                       |                                                                                    |
| 326   | PLAYER_QUEST_LOG_21_3                       |                                                                                    |
| 327   | PLAYER_QUEST_LOG_21_4                       |                                                                                    |
| 328   | PLAYER_QUEST_LOG_22_1                       |                                                                                    |
| 329   | PLAYER_QUEST_LOG_22_2                       |                                                                                    |
| 330   | PLAYER_QUEST_LOG_22_3                       |                                                                                    |
| 331   | PLAYER_QUEST_LOG_22_4                       |                                                                                    |
| 332   | PLAYER_QUEST_LOG_23_1                       |                                                                                    |
| 333   | PLAYER_QUEST_LOG_23_2                       |                                                                                    |
| 334   | PLAYER_QUEST_LOG_23_3                       |                                                                                    |
| 335   | PLAYER_QUEST_LOG_23_4                       |                                                                                    |
| 336   | PLAYER_QUEST_LOG_24_1                       |                                                                                    |
| 337   | PLAYER_QUEST_LOG_24_2                       |                                                                                    |
| 338   | PLAYER_QUEST_LOG_24_3                       |                                                                                    |
| 339   | PLAYER_QUEST_LOG_24_4                       |                                                                                    |
| 340   | PLAYER_QUEST_LOG_25_1                       |                                                                                    |
| 341   | PLAYER_QUEST_LOG_25_2                       |                                                                                    |
| 342   | PLAYER_QUEST_LOG_25_3                       |                                                                                    |
| 343   | PLAYER_QUEST_LOG_25_4                       |                                                                                    |
| 344   | PLAYER_VISIBLE_ITEM_1_CREATOR               |                                                                                    |
| 346   | PLAYER_VISIBLE_ITEM_1_0                     | Item ID equipped on head slot                                                      |
| 358   | PLAYER_VISIBLE_ITEM_1_PROPERTIES            |                                                                                    |
| 359   | PLAYER_VISIBLE_ITEM_1_PAD                   |                                                                                    |
| 360   | PLAYER_VISIBLE_ITEM_2_CREATOR               |                                                                                    |
| 362   | PLAYER_VISIBLE_ITEM_2_0                     | Item ID equipped on neck slot                                                      |
| 374   | PLAYER_VISIBLE_ITEM_2_PROPERTIES            |                                                                                    |
| 375   | PLAYER_VISIBLE_ITEM_2_PAD                   |                                                                                    |
| 376   | PLAYER_VISIBLE_ITEM_3_CREATOR               |                                                                                    |
| 378   | PLAYER_VISIBLE_ITEM_3_0                     | Item ID equipped on shoulder slot                                                  |
| 390   | PLAYER_VISIBLE_ITEM_3_PROPERTIES            |                                                                                    |
| 391   | PLAYER_VISIBLE_ITEM_3_PAD                   |                                                                                    |
| 392   | PLAYER_VISIBLE_ITEM_4_CREATOR               |                                                                                    |
| 394   | PLAYER_VISIBLE_ITEM_4_0                     | Item ID equipped on shirt slot                                                     |
| 406   | PLAYER_VISIBLE_ITEM_4_PROPERTIES            |                                                                                    |
| 407   | PLAYER_VISIBLE_ITEM_4_PAD                   |                                                                                    |
| 408   | PLAYER_VISIBLE_ITEM_5_CREATOR               |                                                                                    |
| 410   | PLAYER_VISIBLE_ITEM_5_0                     | Item ID equipped on chest slot                                                     |
| 422   | PLAYER_VISIBLE_ITEM_5_PROPERTIES            |                                                                                    |
| 423   | PLAYER_VISIBLE_ITEM_5_PAD                   |                                                                                    |
| 424   | PLAYER_VISIBLE_ITEM_6_CREATOR               |                                                                                    |
| 426   | PLAYER_VISIBLE_ITEM_6_0                     | Item ID equipped on belt slot                                                      |
| 438   | PLAYER_VISIBLE_ITEM_6_PROPERTIES            |                                                                                    |
| 439   | PLAYER_VISIBLE_ITEM_6_PAD                   |                                                                                    |
| 440   | PLAYER_VISIBLE_ITEM_7_CREATOR               |                                                                                    |
| 442   | PLAYER_VISIBLE_ITEM_7_0                     | Item ID equipped on legs slot                                                      |
| 454   | PLAYER_VISIBLE_ITEM_7_PROPERTIES            |                                                                                    |
| 455   | PLAYER_VISIBLE_ITEM_7_PAD                   |                                                                                    |
| 456   | PLAYER_VISIBLE_ITEM_8_CREATOR               |                                                                                    |
| 458   | PLAYER_VISIBLE_ITEM_8_0                     | Item ID equipped on feet slot                                                      |
| 470   | PLAYER_VISIBLE_ITEM_8_PROPERTIES            |                                                                                    |
| 471   | PLAYER_VISIBLE_ITEM_8_PAD                   |                                                                                    |
| 472   | PLAYER_VISIBLE_ITEM_9_CREATOR               |                                                                                    |
| 474   | PLAYER_VISIBLE_ITEM_9_0                     | Item ID equipped on wrist slot                                                     |
| 486   | PLAYER_VISIBLE_ITEM_9_PROPERTIES            |                                                                                    |
| 487   | PLAYER_VISIBLE_ITEM_9_PAD                   |                                                                                    |
| 488   | PLAYER_VISIBLE_ITEM_10_CREATOR              |                                                                                    |
| 490   | PLAYER_VISIBLE_ITEM_10_0                    | Item ID equipped on gloves slot                                                    |
| 502   | PLAYER_VISIBLE_ITEM_10_PROPERTIES           |                                                                                    |
| 503   | PLAYER_VISIBLE_ITEM_10_PAD                  |                                                                                    |
| 504   | PLAYER_VISIBLE_ITEM_11_CREATOR              |                                                                                    |
| 506   | PLAYER_VISIBLE_ITEM_11_0                    | Item ID equipped on finger 1 slot                                                  |
| 518   | PLAYER_VISIBLE_ITEM_11_PROPERTIES           |                                                                                    |
| 519   | PLAYER_VISIBLE_ITEM_11_PAD                  |                                                                                    |
| 520   | PLAYER_VISIBLE_ITEM_12_CREATOR              |                                                                                    |
| 522   | PLAYER_VISIBLE_ITEM_12_0                    | Item ID equipped on finger 2 slot                                                  |
| 534   | PLAYER_VISIBLE_ITEM_12_PROPERTIES           |                                                                                    |
| 535   | PLAYER_VISIBLE_ITEM_12_PAD                  |                                                                                    |
| 536   | PLAYER_VISIBLE_ITEM_13_CREATOR              |                                                                                    |
| 538   | PLAYER_VISIBLE_ITEM_13_0                    | Item ID equipped on trinket 1 slot                                                 |
| 550   | PLAYER_VISIBLE_ITEM_13_PROPERTIES           |                                                                                    |
| 551   | PLAYER_VISIBLE_ITEM_13_PAD                  |                                                                                    |
| 552   | PLAYER_VISIBLE_ITEM_14_CREATOR              |                                                                                    |
| 554   | PLAYER_VISIBLE_ITEM_14_0                    | Item ID equipped on trinket 2 slot                                                 |
| 566   | PLAYER_VISIBLE_ITEM_14_PROPERTIES           |                                                                                    |
| 567   | PLAYER_VISIBLE_ITEM_14_PAD                  |                                                                                    |
| 568   | PLAYER_VISIBLE_ITEM_15_CREATOR              |                                                                                    |
| 570   | PLAYER_VISIBLE_ITEM_15_0                    | Item ID equipped on back slot                                                      |
| 582   | PLAYER_VISIBLE_ITEM_15_PROPERTIES           |                                                                                    |
| 583   | PLAYER_VISIBLE_ITEM_15_PAD                  |                                                                                    |
| 584   | PLAYER_VISIBLE_ITEM_16_CREATOR              |                                                                                    |
| 586   | PLAYER_VISIBLE_ITEM_16_0                    | Item ID equipped on main hand slot                                                 |
| 598   | PLAYER_VISIBLE_ITEM_16_PROPERTIES           |                                                                                    |
| 599   | PLAYER_VISIBLE_ITEM_16_PAD                  |                                                                                    |
| 600   | PLAYER_VISIBLE_ITEM_17_CREATOR              |                                                                                    |
| 602   | PLAYER_VISIBLE_ITEM_17_0                    | Item ID equipped on off hand slot                                                  |
| 614   | PLAYER_VISIBLE_ITEM_17_PROPERTIES           |                                                                                    |
| 615   | PLAYER_VISIBLE_ITEM_17_PAD                  |                                                                                    |
| 616   | PLAYER_VISIBLE_ITEM_18_CREATOR              |                                                                                    |
| 618   | PLAYER_VISIBLE_ITEM_18_0                    | Item ID equipped on ranged slot                                                    |
| 630   | PLAYER_VISIBLE_ITEM_18_PROPERTIES           |                                                                                    |
| 631   | PLAYER_VISIBLE_ITEM_18_PAD                  |                                                                                    |
| 632   | PLAYER_VISIBLE_ITEM_19_CREATOR              |                                                                                    |
| 634   | PLAYER_VISIBLE_ITEM_19_0                    | Item ID equipped on tabard                                                         |
| 646   | PLAYER_VISIBLE_ITEM_19_PROPERTIES           |                                                                                    |
| 647   | PLAYER_VISIBLE_ITEM_19_PAD                  |                                                                                    |
| 648   | PLAYER_CHOSEN_TITLE                         |                                                                                    |
| 649   | PLAYER_FIELD_PAD_0                          |                                                                                    |
| 650   | PLAYER_FIELD_INV_SLOT_HEAD                  |                                                                                    |
| 696   | PLAYER_FIELD_PACK_SLOT_1                    |                                                                                    |
| 728   | PLAYER_FIELD_BANK_SLOT_1                    |                                                                                    |
| 784   | PLAYER_FIELD_BANKBAG_SLOT_1                 |                                                                                    |
| 798   | PLAYER_FIELD_VENDORBUYBACK_SLOT_1           |                                                                                    |
| 822   | PLAYER_FIELD_KEYRING_SLOT_1                 |                                                                                    |
| 886   | PLAYER_FIELD_VANITYPET_SLOT_1               |                                                                                    |
| 922   | PLAYER_FARSIGHT                             |                                                                                    |
| 924   | PLAYER__FIELD_KNOWN_TITLES                  |                                                                                    |
| 926   | PLAYER_XP                                   | Current XP                                                                         |
| 927   | PLAYER_NEXT_LEVEL_XP                        | XP needed to level up                                                              |
| 928   | PLAYER_SKILL_INFO_1_1                       |                                                                                    |
| 1312  | PLAYER_CHARACTER_POINTS1                    | Number of unused talent points                                                     |
| 1313  | PLAYER_CHARACTER_POINTS2                    | Number of free primary professions                                                 |
| 1314  | PLAYER_TRACK_CREATURES                      |                                                                                    |
| 1315  | PLAYER_TRACK_RESOURCES                      |                                                                                    |
| 1316  | PLAYER_BLOCK_PERCENTAGE                     |                                                                                    |
| 1317  | PLAYER_DODGE_PERCENTAGE                     |                                                                                    |
| 1318  | PLAYER_PARRY_PERCENTAGE                     |                                                                                    |
| 1319  | PLAYER_EXPERTISE                            |                                                                                    |
| 1320  | PLAYER_OFFHAND_EXPERTISE                    |                                                                                    |
| 1321  | PLAYER_CRIT_PERCENTAGE                      |                                                                                    |
| 1322  | PLAYER_RANGED_CRIT_PERCENTAGE               |                                                                                    |
| 1323  | PLAYER_OFFHAND_CRIT_PERCENTAGE              |                                                                                    |
| 1324  | PLAYER_SPELL_CRIT_PERCENTAGE1               |                                                                                    |
| 1331  | PLAYER_SHIELD_BLOCK                         |                                                                                    |
| 1332  | PLAYER_EXPLORED_ZONES_1                     |                                                                                    |
| 1396  | PLAYER_REST_STATE_EXPERIENCE                |                                                                                    |
| 1397  | PLAYER_FIELD_COINAGE                        | Character money (in copper)                                                        |
| 1398  | PLAYER_FIELD_MOD_DAMAGE_DONE_POS            |                                                                                    |
| 1405  | PLAYER_FIELD_MOD_DAMAGE_DONE_NEG            |                                                                                    |
| 1412  | PLAYER_FIELD_MOD_DAMAGE_DONE_PCT            |                                                                                    |
| 1419  | PLAYER_FIELD_MOD_HEALING_DONE_POS           |                                                                                    |
| 1420  | PLAYER_FIELD_MOD_TARGET_RESISTANCE          |                                                                                    |
| 1421  | PLAYER_FIELD_MOD_TARGET_PHYSICAL_RESISTANCE |                                                                                    |
| 1422  | PLAYER_FIELD_BYTES                          |                                                                                    |
| 1423  | PLAYER_AMMO_ID                              |                                                                                    |
| 1424  | PLAYER_SELF_RES_SPELL                       |                                                                                    |
| 1425  | PLAYER_FIELD_PVP_MEDALS                     |                                                                                    |
| 1426  | PLAYER_FIELD_BUYBACK_PRICE_1                |                                                                                    |
| 1438  | PLAYER_FIELD_BUYBACK_TIMESTAMP_1            |                                                                                    |
| 1450  | PLAYER_FIELD_KILLS                          |                                                                                    |
| 1451  | PLAYER_FIELD_TODAY_CONTRIBUTION             |                                                                                    |
| 1452  | PLAYER_FIELD_YESTERDAY_CONTRIBUTION         |                                                                                    |
| 1453  | PLAYER_FIELD_LIFETIME_HONORBALE_KILLS       |                                                                                    |
| 1454  | PLAYER_FIELD_BYTES2                         |                                                                                    |
| 1455  | PLAYER_FIELD_WATCHED_FACTION_INDEX          |                                                                                    |
| 1456  | PLAYER_FIELD_COMBAT_RATING_1                |                                                                                    |
| 1456  | PLAYER_FIELD_ALL_WEAPONS_SKILL_RATING       |                                                                                    |
| 1457  | PLAYER_FIELD_DEFENCE_RATING                 |                                                                                    |
| 1458  | PLAYER_FIELD_DODGE_RATING                   |                                                                                    |
| 1459  | PLAYER_FIELD_PARRY_RATING                   |                                                                                    |
| 1460  | PLAYER_FIELD_BLOCK_RATING                   |                                                                                    |
| 1461  | PLAYER_FIELD_MELEE_HIT_RATING               |                                                                                    |
| 1462  | PLAYER_FIELD_RANGED_HIT_RATING              |                                                                                    |
| 1463  | PLAYER_FIELD_SPELL_HIT_RATING               |                                                                                    |
| 1464  | PLAYER_FIELD_MELEE_CRIT_RATING              |                                                                                    |
| 1465  | PLAYER_FIELD_RANGED_CRIT_RATING             |                                                                                    |
| 1472  | PLAYER_FIELD_SPELL_CRIT_RATING              |                                                                                    |
| 1473  | PLAYER_FIELD_HIT_TAKEN_MELEE_RATING         |                                                                                    |
| 1474  | PLAYER_FIELD_HIT_TAKEN_RANGED_RATING        |                                                                                    |
| 1475  | PLAYER_FIELD_HIT_TAKEN_SPELL_RATING         |                                                                                    |
| 1476  | PLAYER_FIELD_CRIT_TAKEN_MELEE_RATING        |                                                                                    |
| 1477  | PLAYER_FIELD_CRIT_TAKEN_RANGED_RATING       |                                                                                    |
| 1478  | PLAYER_FIELD_CRIT_TAKEN_SPELL_RATING        |                                                                                    |
| 1479  | PLAYER_FIELD_MELEE_HASTE_RATING             |                                                                                    |
| 1480  | PLAYER_FIELD_RANGED_HASTE_RATING            |                                                                                    |
| 1481  | PLAYER_FIELD_SPELL_HASTE_RATING             |                                                                                    |
| 1488  | PLAYER_FIELD_MELEE_WEAPON_SKILL_RATING      |                                                                                    |
| 1489  | PLAYER_FIELD_OFFHAND_WEAPON_SKILL_RATING    |                                                                                    |
| 1490  | PLAYER_FIELD_RANGED_WEAPON_SKILL_RATING     |                                                                                    |
| 1491  | PLAYER_FIELD_EXPERTISE_RATING               |                                                                                    |
| 1480  | PLAYER_FIELD_ARENA_TEAM_INFO_1_1            |                                                                                    |
| 1480  | PLAYER_FIELD_ARENA_TEAM_ID_2v2              |                                                                                    |
| 1486  | PLAYER_FIELD_ARENA_TEAM_ID_3v3              |                                                                                    |
| 1498  | PLAYER_FIELD_ARENA_TEAM_ID_5v5              |                                                                                    |
| 1498  | PLAYER_FIELD_HONOR_CURRENCY                 | Character total honor points                                                       |
| 1499  | PLAYER_FIELD_ARENA_CURRENCY                 | Character total arena points                                                       |
| 1500  | PLAYER_FIELD_MOD_MANA_REGEN                 |                                                                                    |
| 1501  | PLAYER_FIELD_MOD_MANA_REGEN_INTERRUPT       |                                                                                    |
| 1502  | PLAYER_FIELD_MAX_LEVEL                      |                                                                                    |
| 1503  | PLAYER_FIELD_DAILY_QUESTS_1                 |                                                                                    |
