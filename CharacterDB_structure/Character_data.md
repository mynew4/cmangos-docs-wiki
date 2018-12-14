The following is a table containing indices and what values they contain for [character.data](character#data). The source of this data is UpdateFields.h

The .getvalue and .setvalue commands deal with the indices in this table. To modify any of the values in this table in real time, use the .setvalue command with the correct index (eg. .setvalue 4 2 0 sets the target's size to 2.00 (notice that it is a float, hence the 0 at the end)).

All objects in the game (game objects, creatures, and players) share the OBJECT*\* fields while only creatures and players share the UNIT*\* fields while only players use the PLAYER\_\* fields.

If you want to use direct SQL to extract a single value from this rather large blob, the syntax to use is this:

    SELECT CAST(SUBSTRING_INDEX(SUBSTRING_INDEX(`data`, ' ', <index + 1>), ' ', -1) AS UNSIGNED) AS `fieldName` FROM `characters`;

Just replace <index + 1> with the index in this table and add one to it.
The reason why you are adding one is because of how the nested SUBSTRING\_INDEX syntax works. Let's analyze the function calls. Working from the inside out, the first function called is `` SUBSTRING_INDEX(`data`, ' ', <index + 1>) ``. The SUBSTRING\_INDEX function creates a substring from the big data blob after <index + 1> spaces. Notice that if we used just <index>, the substring would be everything up to the value we want **but not including it**. The second function call is `SUBSTRING_INDEX(<substring from inner function>, ' ', -1)`. This function call uses -1 as the count, meaning that it will substring from the end to the front. Since it is a count of one, it will create a substring that is exactly the value we want because the value we want is sandwiched between the end of the string and a space. The final function call `CAST(<substring> AS UNSIGNED)` casts the final string into an unsigned integer. This is because the data blob contains only numbers and if we cast the string into an integer, we can use integer operations on it (say if we use it in a WHERE clause to compare to another integer).

An example of the syntax in use is the following query where we are making a list of characters and their levels who have more than 1000 gold.

    SELECT `guid`, `name`, CAST(SUBSTRING_INDEX(SUBSTRING_INDEX(`data`, ' ', 35), ' ', -1) AS UNSIGNED) AS `level` FROM `characters` 
       WHERE CAST(SUBSTRING_INDEX(SUBSTRING_INDEX(`data`, ' ', 1398), ' ', -1) AS UNSIGNED) > 10000000;

If you want to edit the value of one of these fields, the query to do that is the following but don't forget to backup your table first:

    UPDATE `characters` SET `data`=CONCAT(CAST(SUBSTRING_INDEX(`data`, ' ', <index>) AS CHAR), ' ', <value>, ' ', 
       CAST(SUBSTRING_INDEX(`data`, ' ', <-(max index - index) - 1>)AS CHAR)) [WHERE ...]

Replace "<index>" with the index that you want to change (look at table below), "&lt;~~(max index~~ index) -1&gt;" with the negative of the subtraction of the last index (look at table) minus the index that you want to change and finally minus one. Finally replace "<value>" with the new value you want to put.

For example, to reset gold to zero for all characters with level higher than 70, you can use the following query:

    UPDATE `characters` SET `data`=CONCAT(CAST(SUBSTRING_INDEX(`data`, ' ', 1397) AS CHAR), ' ', 0, ' ',
    CAST(SUBSTRING_INDEX(`data`, ' ', -131) AS CHAR)) WHERE CAST(SUBSTRING_INDEX(SUBSTRING_INDEX
    (`data`, ' ', 35), ' ', -1) AS UNSIGNED) > 70; 

Again, don't forget to backup first!!

### 3.3.5 Character Data Table

**This table was last updated for 3.3.5 values.**

<table style="width:100%;">
<colgroup>
<col width="5%" />
<col width="38%" />
<col width="56%" />
</colgroup>
<thead>
<tr class="header">
<th>Index</th>
<th>Value Name</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>OBJECT_FIELD_GUID</td>
<td>Character GUID (full GUID includes both index 0 and index 1 as 64bit number)</td>
</tr>
<tr class="even">
<td>2</td>
<td>OBJECT_FIELD_TYPE</td>
<td></td>
</tr>
<tr class="odd">
<td>3</td>
<td>OBJECT_FIELD_ENTRY</td>
<td></td>
</tr>
<tr class="even">
<td>4</td>
<td>OBJECT_FIELD_SCALE_X</td>
<td>Size of how model appears in-game (float value)</td>
</tr>
<tr class="odd">
<td>5</td>
<td>OBJECT_FIELD_PADDING</td>
<td></td>
</tr>
<tr class="even">
<td>6</td>
<td>UNIT_FIELD_CHARM</td>
<td></td>
</tr>
<tr class="odd">
<td>8</td>
<td>UNIT_FIELD_SUMMON</td>
<td></td>
</tr>
<tr class="even">
<td>10</td>
<td>UNIT_FIELD_CRITTER</td>
<td></td>
</tr>
<tr class="odd">
<td>12</td>
<td>UNIT_FIELD_CHARMEDBY</td>
<td></td>
</tr>
<tr class="even">
<td>14</td>
<td>UNIT_FIELD_SUMMONEDBY</td>
<td></td>
</tr>
<tr class="odd">
<td>16</td>
<td>UNIT_FIELD_CREATEDBY</td>
<td></td>
</tr>
<tr class="even">
<td>18</td>
<td>UNIT_FIELD_TARGET</td>
<td></td>
</tr>
<tr class="odd">
<td>20</td>
<td>UNIT_FIELD_CHANNEL_OBJECT</td>
<td></td>
</tr>
<tr class="even">
<td>22</td>
<td>UNIT_FIELD_CHANNEL_SPELL</td>
<td></td>
</tr>
<tr class="odd">
<td>23</td>
<td>UNIT_FIELD_BYTES_0</td>
<td>(gender &lt;&lt; 16)</td>
</tr>
<tr class="even">
<td>24</td>
<td>UNIT_FIELD_HEALTH</td>
<td>Current health</td>
</tr>
<tr class="odd">
<td>25</td>
<td>UNIT_FIELD_POWER1</td>
<td>Current mana</td>
</tr>
<tr class="even">
<td>26</td>
<td>UNIT_FIELD_POWER2</td>
<td>Current rage</td>
</tr>
<tr class="odd">
<td>27</td>
<td>UNIT_FIELD_POWER3</td>
<td>Current focus</td>
</tr>
<tr class="even">
<td>28</td>
<td>UNIT_FIELD_POWER4</td>
<td>Current energy</td>
</tr>
<tr class="odd">
<td>29</td>
<td>UNIT_FIELD_POWER5</td>
<td>Current happiness</td>
</tr>
<tr class="even">
<td>30</td>
<td>UNIT_FIELD_POWER6</td>
<td></td>
</tr>
<tr class="odd">
<td>31</td>
<td>UNIT_FIELD_POWER7</td>
<td></td>
</tr>
<tr class="even">
<td>32</td>
<td>UNIT_FIELD_MAXHEALTH</td>
<td>Max health</td>
</tr>
<tr class="odd">
<td>33</td>
<td>UNIT_FIELD_MAXPOWER1</td>
<td>Max mana</td>
</tr>
<tr class="even">
<td>34</td>
<td>UNIT_FIELD_MAXPOWER2</td>
<td>Max rage</td>
</tr>
<tr class="odd">
<td>35</td>
<td>UNIT_FIELD_MAXPOWER3</td>
<td>Max focus</td>
</tr>
<tr class="even">
<td>36</td>
<td>UNIT_FIELD_MAXPOWER4</td>
<td>Max energy</td>
</tr>
<tr class="odd">
<td>37</td>
<td>UNIT_FIELD_MAXPOWER5</td>
<td>Max happiness</td>
</tr>
<tr class="even">
<td>38</td>
<td>UNIT_FIELD_MAXPOWER6</td>
<td></td>
</tr>
<tr class="odd">
<td>39</td>
<td>UNIT_FIELD_MAXPOWER7</td>
<td></td>
</tr>
<tr class="even">
<td>40</td>
<td>UNIT_FIELD_POWER_REGEN_FLAT_MODIFIER</td>
<td></td>
</tr>
<tr class="odd">
<td>47</td>
<td>UNIT_FIELD_POWER_REGEN_INTERRUPTED_FLAT_MODIFIER</td>
<td></td>
</tr>
<tr class="even">
<td>54</td>
<td>UNIT_FIELD_LEVEL</td>
<td>Character level</td>
</tr>
<tr class="odd">
<td>55</td>
<td>UNIT_FIELD_FACTIONTEMPLATE</td>
<td>Currently used faction template ID (<a href="FactionTemplate.dbc" class="uri">FactionTemplate.dbc</a>)</td>
</tr>
<tr class="even">
<td>56</td>
<td>UNIT_VIRTUAL_ITEM_SLOT_ID</td>
<td></td>
</tr>
<tr class="odd">
<td>59</td>
<td>UNIT_FIELD_FLAGS</td>
<td></td>
</tr>
<tr class="even">
<td>60</td>
<td>UNIT_FIELD_FLAGS_2</td>
<td></td>
</tr>
<tr class="odd">
<td>61</td>
<td>UNIT_FIELD_AURASTATE</td>
<td></td>
</tr>
<tr class="even">
<td>62</td>
<td>UNIT_FIELD_BASEATTACKTIME</td>
<td></td>
</tr>
<tr class="odd">
<td>64</td>
<td>UNIT_FIELD_RANGEDATTACKTIME</td>
<td></td>
</tr>
<tr class="even">
<td>65</td>
<td>UNIT_FIELD_BOUNDINGRADIUS</td>
<td></td>
</tr>
<tr class="odd">
<td>66</td>
<td>UNIT_FIELD_COMBATREACH</td>
<td></td>
</tr>
<tr class="even">
<td>67</td>
<td>UNIT_FIELD_DISPLAYID</td>
<td>Current model ID (can be different from regular if character is morphed, etc)</td>
</tr>
<tr class="odd">
<td>68</td>
<td>UNIT_FIELD_NATIVEDISPLAYID</td>
<td>The native model ID. Model always reverts to this number when player is demorphed.</td>
</tr>
<tr class="even">
<td>69</td>
<td>UNIT_FIELD_MOUNTDISPLAYID</td>
<td>Units current mount display id.</td>
</tr>
<tr class="odd">
<td>70</td>
<td>UNIT_FIELD_MINDAMAGE</td>
<td></td>
</tr>
<tr class="even">
<td>71</td>
<td>UNIT_FIELD_MAXDAMAGE</td>
<td></td>
</tr>
<tr class="odd">
<td>72</td>
<td>UNIT_FIELD_MINOFFHANDDAMAGE</td>
<td></td>
</tr>
<tr class="even">
<td>73</td>
<td>UNIT_FIELD_MAXOFFHANDDAMAGE</td>
<td></td>
</tr>
<tr class="odd">
<td>74</td>
<td>UNIT_FIELD_BYTES_1</td>
<td>(stealthFlag &lt;&lt; 16)</td>
</tr>
</tbody>
</table>

**standState** - TODO: after this shift all by one

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

**standFlags**

    PLAYER_STATE_FLAG_ALWAYS_STAND = 0x01             // byte 4
    PLAYER_STATE_FLAG_CREEP        = 0x02000000
    PLAYER_STATE_FLAG_UNTRACKABLE  = 0x04000000
    PLAYER_STATE_FLAG_ALL          = 0xFF000000

| 74  | UNIT\_FIELD\_PETNUMBER                  |                                         |
|-----|-----------------------------------------|-----------------------------------------|
| 75  | UNIT\_FIELD\_PET\_NAME\_TIMESTAMP       |                                         |
| 76  | UNIT\_FIELD\_PETEXPERIENCE              |                                         |
| 77  | UNIT\_FIELD\_PETNEXTLEVELEXP            |                                         |
| 78  | UNIT\_DYNAMIC\_FLAGS                    |                                         |
| 79  | UNIT\_CHANNEL\_SPELL                    |                                         |
| 80  | UNIT\_MOD\_CAST\_SPEED                  | Units cast speed multiplier (float)     |
| 81  | UNIT\_CREATED\_BY\_SPELL                |                                         |
| 82  | UNIT\_NPC\_FLAGS                        | npc flag\]\]                            |
| 83  | UNIT\_NPC\_EMOTESTATE                   |                                         |
| 84  | UNIT\_FIELD\_STAT0                      | Base strength (before any item bonuses) |
| 85  | UNIT\_FIELD\_STAT1                      | Base agility                            |
| 86  | UNIT\_FIELD\_STAT2                      | Base stamina                            |
| 87  | UNIT\_FIELD\_STAT3                      | Base intellect                          |
| 88  | UNIT\_FIELD\_STAT4                      | Base spirit                             |
| 89  | UNIT\_FIELD\_POSSTAT0                   |                                         |
| 90  | UNIT\_FIELD\_POSSTAT1                   |                                         |
| 91  | UNIT\_FIELD\_POSSTAT2                   |                                         |
| 92  | UNIT\_FIELD\_POSSTAT3                   |                                         |
| 93  | UNIT\_FIELD\_POSSTAT4                   |                                         |
| 94  | UNIT\_FIELD\_NEGSTAT0                   |                                         |
| 95  | UNIT\_FIELD\_NEGSTAT1                   |                                         |
| 96  | UNIT\_FIELD\_NEGSTAT2                   |                                         |
| 97  | UNIT\_FIELD\_NEGSTAT3                   |                                         |
| 98  | UNIT\_FIELD\_NEGSTAT4                   |                                         |
| 99  | UNIT\_FIELD\_RESISTANCES                | Base armor (before any item bonuses)    |
| 100 |                                         | Base holy resistance                    |
| 101 |                                         | Base fire resistance                    |
| 102 |                                         | Base nature resistance                  |
| 103 |                                         | Base frost resistance                   |
| 104 |                                         | Base shadow resistance                  |
| 105 |                                         | Base arcane resistance                  |
| 106 | UNIT\_FIELD\_RESISTANCEBUFFMODSPOSITIVE |                                         |
| 113 | UNIT\_FIELD\_RESISTANCEBUFFMODSNEGATIVE |                                         |
| 120 | UNIT\_FIELD\_BASE\_MANA                 |                                         |
| 121 | UNIT\_FIELD\_BASE\_HEALTH               |                                         |
| 122 | UNIT\_FIELD\_BYTES\_2                   | (unitRename &lt;&lt; 16)                |

**sheathState**

    SHEATH_STATE_UNARMED  = 0 // non prepared weapon
    SHEATH_STATE_MELEE    = 1 // prepared melee weapon
    SHEATH_STATE_RANGED   = 2 // prepared ranged weapon

**unitFlags**

    UNIT_BYTE2_FLAG_PVP         = 0x01
    UNIT_BYTE2_FLAG_UNK1        = 0x02
    UNIT_BYTE2_FLAG_FFA_PVP     = 0x04
    UNIT_BYTE2_FLAG_SANCTUARY   = 0x08
    UNIT_BYTE2_FLAG_UNK4        = 0x10
    UNIT_BYTE2_FLAG_UNK5        = 0x20
    UNIT_BYTE2_FLAG_UNK6        = 0x40
    UNIT_BYTE2_FLAG_UNK7        = 0x80

**unitRename**

    UNIT_RENAME_NOT_ALLOWED = 0x02
    UNIT_RENAME_ALLOWED     = 0x03

**shapeshiftForm**

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

| 123 | UNIT\_FIELD\_ATTACK\_POWER                     |                                              |
|-----|------------------------------------------------|----------------------------------------------|
| 124 | UNIT\_FIELD\_ATTACK\_POWER\_MODS               |                                              |
| 125 | UNIT\_FIELD\_ATTACK\_POWER\_MULTIPLIER         |                                              |
| 126 | UNIT\_FIELD\_RANGED\_ATTACK\_POWER             |                                              |
| 127 | UNIT\_FIELD\_RANGED\_ATTACK\_POWER\_MODS       |                                              |
| 128 | UNIT\_FIELD\_RANGED\_ATTACK\_POWER\_MULTIPLIER |                                              |
| 129 | UNIT\_FIELD\_MINRANGEDDAMAGE                   |                                              |
| 130 | UNIT\_FIELD\_MAXRANGEDDAMAGE                   |                                              |
| 131 | UNIT\_FIELD\_POWER\_COST\_MODIFIER             |                                              |
| 138 | UNIT\_FIELD\_POWER\_COST\_MULTIPLIER           |                                              |
| 145 | UNIT\_FIELD\_MAXHEALTHMODIFIER                 |                                              |
| 146 | UNIT\_FIELD\_HOVERHEIGHT                       |                                              |
| 147 | UNIT\_FIELD\_PADDING                           |                                              |
| 148 | PLAYER\_DUEL\_ARBITER                          | GUID of the players duel flag (if in a duel) |
| 150 | PLAYER\_FLAGS                                  |                                              |
| 151 | PLAYER\_GUILDID                                | Id of guild the player is in (guild.guildid) |
| 152 | PLAYER\_GUILDRANK                              | The player's rank ID (guild\_rank.rid)       |
| 153 | PLAYER\_BYTES                                  | (hairStyle &lt;&lt; 16)                      |
| 154 | PLAYER\_BYTES\_2                               | (maxslot &lt;&lt; 16)                        |

**restState**

    rested = 0x01
    normal = 0x02

| 155  | PLAYER\_BYTES\_3                                 | gender, drunken state                       |
|------|--------------------------------------------------|---------------------------------------------|
| 156  | PLAYER\_DUEL\_TEAM                               |                                             |
| 157  | PLAYER\_GUILD\_TIMESTAMP                         |                                             |
| 158  | PLAYER\_QUEST\_LOG\_1\_1                         |                                             |
| 159  | PLAYER\_QUEST\_LOG\_1\_2                         |                                             |
| 160  | PLAYER\_QUEST\_LOG\_1\_3                         |                                             |
| 161  | PLAYER\_QUEST\_LOG\_1\_4                         |                                             |
| 162  | PLAYER\_QUEST\_LOG\_2\_1                         |                                             |
| 163  | PLAYER\_QUEST\_LOG\_2\_2                         |                                             |
| 164  | PLAYER\_QUEST\_LOG\_2\_3                         |                                             |
| 165  | PLAYER\_QUEST\_LOG\_2\_4                         |                                             |
| 166  | PLAYER\_QUEST\_LOG\_3\_1                         |                                             |
| 167  | PLAYER\_QUEST\_LOG\_3\_2                         |                                             |
| 168  | PLAYER\_QUEST\_LOG\_3\_3                         |                                             |
| 169  | PLAYER\_QUEST\_LOG\_3\_4                         |                                             |
| 170  | PLAYER\_QUEST\_LOG\_4\_1                         |                                             |
| 171  | PLAYER\_QUEST\_LOG\_4\_2                         |                                             |
| 172  | PLAYER\_QUEST\_LOG\_4\_3                         |                                             |
| 173  | PLAYER\_QUEST\_LOG\_4\_4                         |                                             |
| 174  | PLAYER\_QUEST\_LOG\_5\_1                         |                                             |
| 175  | PLAYER\_QUEST\_LOG\_5\_2                         |                                             |
| 176  | PLAYER\_QUEST\_LOG\_5\_3                         |                                             |
| 177  | PLAYER\_QUEST\_LOG\_5\_4                         |                                             |
| 178  | PLAYER\_QUEST\_LOG\_6\_1                         |                                             |
| 179  | PLAYER\_QUEST\_LOG\_6\_2                         |                                             |
| 180  | PLAYER\_QUEST\_LOG\_6\_3                         |                                             |
| 181  | PLAYER\_QUEST\_LOG\_6\_4                         |                                             |
| 182  | PLAYER\_QUEST\_LOG\_7\_1                         |                                             |
| 183  | PLAYER\_QUEST\_LOG\_7\_2                         |                                             |
| 184  | PLAYER\_QUEST\_LOG\_7\_3                         |                                             |
| 185  | PLAYER\_QUEST\_LOG\_7\_4                         |                                             |
| 186  | PLAYER\_QUEST\_LOG\_8\_1                         |                                             |
| 187  | PLAYER\_QUEST\_LOG\_8\_2                         |                                             |
| 188  | PLAYER\_QUEST\_LOG\_8\_3                         |                                             |
| 189  | PLAYER\_QUEST\_LOG\_8\_4                         |                                             |
| 190  | PLAYER\_QUEST\_LOG\_9\_1                         |                                             |
| 191  | PLAYER\_QUEST\_LOG\_9\_2                         |                                             |
| 192  | PLAYER\_QUEST\_LOG\_9\_3                         |                                             |
| 193  | PLAYER\_QUEST\_LOG\_9\_4                         |                                             |
| 194  | PLAYER\_QUEST\_LOG\_10\_1                        |                                             |
| 195  | PLAYER\_QUEST\_LOG\_10\_2                        |                                             |
| 196  | PLAYER\_QUEST\_LOG\_10\_3                        |                                             |
| 197  | PLAYER\_QUEST\_LOG\_10\_4                        |                                             |
| 198  | PLAYER\_QUEST\_LOG\_11\_1                        |                                             |
| 199  | PLAYER\_QUEST\_LOG\_11\_2                        |                                             |
| 200  | PLAYER\_QUEST\_LOG\_11\_3                        |                                             |
| 201  | PLAYER\_QUEST\_LOG\_11\_4                        |                                             |
| 202  | PLAYER\_QUEST\_LOG\_12\_1                        |                                             |
| 203  | PLAYER\_QUEST\_LOG\_12\_2                        |                                             |
| 204  | PLAYER\_QUEST\_LOG\_12\_3                        |                                             |
| 205  | PLAYER\_QUEST\_LOG\_12\_4                        |                                             |
| 206  | PLAYER\_QUEST\_LOG\_13\_1                        |                                             |
| 207  | PLAYER\_QUEST\_LOG\_13\_2                        |                                             |
| 208  | PLAYER\_QUEST\_LOG\_13\_3                        |                                             |
| 209  | PLAYER\_QUEST\_LOG\_13\_4                        |                                             |
| 210  | PLAYER\_QUEST\_LOG\_14\_1                        |                                             |
| 211  | PLAYER\_QUEST\_LOG\_14\_2                        |                                             |
| 212  | PLAYER\_QUEST\_LOG\_14\_3                        |                                             |
| 213  | PLAYER\_QUEST\_LOG\_14\_4                        |                                             |
| 214  | PLAYER\_QUEST\_LOG\_15\_1                        |                                             |
| 215  | PLAYER\_QUEST\_LOG\_15\_2                        |                                             |
| 216  | PLAYER\_QUEST\_LOG\_15\_3                        |                                             |
| 217  | PLAYER\_QUEST\_LOG\_15\_4                        |                                             |
| 218  | PLAYER\_QUEST\_LOG\_16\_1                        |                                             |
| 219  | PLAYER\_QUEST\_LOG\_16\_2                        |                                             |
| 220  | PLAYER\_QUEST\_LOG\_16\_3                        |                                             |
| 221  | PLAYER\_QUEST\_LOG\_16\_4                        |                                             |
| 222  | PLAYER\_QUEST\_LOG\_17\_1                        |                                             |
| 223  | PLAYER\_QUEST\_LOG\_17\_2                        |                                             |
| 224  | PLAYER\_QUEST\_LOG\_17\_3                        |                                             |
| 225  | PLAYER\_QUEST\_LOG\_17\_4                        |                                             |
| 226  | PLAYER\_QUEST\_LOG\_18\_1                        |                                             |
| 227  | PLAYER\_QUEST\_LOG\_18\_2                        |                                             |
| 228  | PLAYER\_QUEST\_LOG\_18\_3                        |                                             |
| 229  | PLAYER\_QUEST\_LOG\_18\_4                        |                                             |
| 230  | PLAYER\_QUEST\_LOG\_19\_1                        |                                             |
| 231  | PLAYER\_QUEST\_LOG\_19\_2                        |                                             |
| 232  | PLAYER\_QUEST\_LOG\_19\_3                        |                                             |
| 233  | PLAYER\_QUEST\_LOG\_19\_4                        |                                             |
| 234  | PLAYER\_QUEST\_LOG\_20\_1                        |                                             |
| 235  | PLAYER\_QUEST\_LOG\_20\_2                        |                                             |
| 236  | PLAYER\_QUEST\_LOG\_20\_3                        |                                             |
| 237  | PLAYER\_QUEST\_LOG\_20\_4                        |                                             |
| 238  | PLAYER\_QUEST\_LOG\_21\_1                        |                                             |
| 239  | PLAYER\_QUEST\_LOG\_21\_2                        |                                             |
| 240  | PLAYER\_QUEST\_LOG\_21\_3                        |                                             |
| 241  | PLAYER\_QUEST\_LOG\_21\_4                        |                                             |
| 242  | PLAYER\_QUEST\_LOG\_22\_1                        |                                             |
| 243  | PLAYER\_QUEST\_LOG\_22\_2                        |                                             |
| 244  | PLAYER\_QUEST\_LOG\_22\_3                        |                                             |
| 245  | PLAYER\_QUEST\_LOG\_22\_4                        |                                             |
| 246  | PLAYER\_QUEST\_LOG\_23\_1                        |                                             |
| 247  | PLAYER\_QUEST\_LOG\_23\_2                        |                                             |
| 248  | PLAYER\_QUEST\_LOG\_23\_3                        |                                             |
| 249  | PLAYER\_QUEST\_LOG\_23\_4                        |                                             |
| 250  | PLAYER\_QUEST\_LOG\_24\_1                        |                                             |
| 251  | PLAYER\_QUEST\_LOG\_24\_2                        |                                             |
| 252  | PLAYER\_QUEST\_LOG\_24\_3                        |                                             |
| 253  | PLAYER\_QUEST\_LOG\_24\_4                        |                                             |
| 254  | PLAYER\_QUEST\_LOG\_25\_1                        |                                             |
| 255  | PLAYER\_QUEST\_LOG\_25\_2                        |                                             |
| 256  | PLAYER\_QUEST\_LOG\_25\_3                        |                                             |
| 257  | PLAYER\_QUEST\_LOG\_25\_4                        |                                             |
| 258  | PLAYER\_VISIBLE\_ITEM\_1\_CREATOR                |                                             |
| 260  | PLAYER\_VISIBLE\_ITEM\_1\_0                      | Item ID equipped on head slot               |
| 273  | PLAYER\_VISIBLE\_ITEM\_1\_PROPERTIES             |                                             |
| 274  | PLAYER\_VISIBLE\_ITEM\_1\_SEED                   |                                             |
| 275  | PLAYER\_VISIBLE\_ITEM\_1\_PAD                    |                                             |
| 276  | PLAYER\_VISIBLE\_ITEM\_2\_CREATOR                |                                             |
| 278  | PLAYER\_VISIBLE\_ITEM\_2\_0                      | Item ID equipped on neck slot               |
| 291  | PLAYER\_VISIBLE\_ITEM\_2\_PROPERTIES             |                                             |
| 292  | PLAYER\_VISIBLE\_ITEM\_2\_SEED                   |                                             |
| 293  | PLAYER\_VISIBLE\_ITEM\_2\_PAD                    |                                             |
| 294  | PLAYER\_VISIBLE\_ITEM\_3\_CREATOR                |                                             |
| 296  | PLAYER\_VISIBLE\_ITEM\_3\_0                      | Item ID equipped on shoulder slot           |
| 309  | PLAYER\_VISIBLE\_ITEM\_3\_PROPERTIES             |                                             |
| 310  | PLAYER\_VISIBLE\_ITEM\_3\_SEED                   |                                             |
| 311  | PLAYER\_VISIBLE\_ITEM\_3\_PAD                    |                                             |
| 312  | PLAYER\_VISIBLE\_ITEM\_4\_CREATOR                |                                             |
| 314  | PLAYER\_VISIBLE\_ITEM\_4\_0                      | Item ID equipped on shirt slot              |
| 327  | PLAYER\_VISIBLE\_ITEM\_4\_PROPERTIES             |                                             |
| 328  | PLAYER\_VISIBLE\_ITEM\_4\_SEED                   |                                             |
| 329  | PLAYER\_VISIBLE\_ITEM\_4\_PAD                    |                                             |
| 330  | PLAYER\_VISIBLE\_ITEM\_5\_CREATOR                |                                             |
| 332  | PLAYER\_VISIBLE\_ITEM\_5\_0                      | Item ID equipped on chest slot              |
| 345  | PLAYER\_VISIBLE\_ITEM\_5\_PROPERTIES             |                                             |
| 346  | PLAYER\_VISIBLE\_ITEM\_5\_SEED                   |                                             |
| 347  | PLAYER\_VISIBLE\_ITEM\_5\_PAD                    |                                             |
| 348  | PLAYER\_VISIBLE\_ITEM\_6\_CREATOR                |                                             |
| 350  | PLAYER\_VISIBLE\_ITEM\_6\_0                      | Item ID equipped on belt slot               |
| 363  | PLAYER\_VISIBLE\_ITEM\_6\_PROPERTIES             |                                             |
| 364  | PLAYER\_VISIBLE\_ITEM\_6\_SEED                   |                                             |
| 365  | PLAYER\_VISIBLE\_ITEM\_6\_PAD                    |                                             |
| 366  | PLAYER\_VISIBLE\_ITEM\_7\_CREATOR                |                                             |
| 368  | PLAYER\_VISIBLE\_ITEM\_7\_0                      | Item ID equipped on legs slot               |
| 381  | PLAYER\_VISIBLE\_ITEM\_7\_PROPERTIES             |                                             |
| 382  | PLAYER\_VISIBLE\_ITEM\_7\_SEED                   |                                             |
| 383  | PLAYER\_VISIBLE\_ITEM\_7\_PAD                    |                                             |
| 384  | PLAYER\_VISIBLE\_ITEM\_8\_CREATOR                |                                             |
| 386  | PLAYER\_VISIBLE\_ITEM\_8\_0                      | Item ID equipped on feet slot               |
| 399  | PLAYER\_VISIBLE\_ITEM\_8\_PROPERTIES             |                                             |
| 400  | PLAYER\_VISIBLE\_ITEM\_8\_SEED                   |                                             |
| 401  | PLAYER\_VISIBLE\_ITEM\_8\_PAD                    |                                             |
| 402  | PLAYER\_VISIBLE\_ITEM\_9\_CREATOR                |                                             |
| 404  | PLAYER\_VISIBLE\_ITEM\_9\_0                      | Item ID equipped on wrist slot              |
| 417  | PLAYER\_VISIBLE\_ITEM\_9\_PROPERTIES             |                                             |
| 418  | PLAYER\_VISIBLE\_ITEM\_9\_SEED                   |                                             |
| 419  | PLAYER\_VISIBLE\_ITEM\_9\_PAD                    |                                             |
| 420  | PLAYER\_VISIBLE\_ITEM\_10\_CREATOR               |                                             |
| 422  | PLAYER\_VISIBLE\_ITEM\_10\_0                     | Item ID equipped on gloves slot             |
| 435  | PLAYER\_VISIBLE\_ITEM\_10\_PROPERTIES            |                                             |
| 436  | PLAYER\_VISIBLE\_ITEM\_10\_SEED                  |                                             |
| 437  | PLAYER\_VISIBLE\_ITEM\_10\_PAD                   |                                             |
| 438  | PLAYER\_VISIBLE\_ITEM\_11\_CREATOR               |                                             |
| 440  | PLAYER\_VISIBLE\_ITEM\_11\_0                     | Item ID equipped on finger 1 slot           |
| 453  | PLAYER\_VISIBLE\_ITEM\_11\_PROPERTIES            |                                             |
| 454  | PLAYER\_VISIBLE\_ITEM\_11\_SEED                  |                                             |
| 455  | PLAYER\_VISIBLE\_ITEM\_11\_PAD                   |                                             |
| 456  | PLAYER\_VISIBLE\_ITEM\_12\_CREATOR               |                                             |
| 458  | PLAYER\_VISIBLE\_ITEM\_12\_0                     | Item ID equipped on finger 2 slot           |
| 471  | PLAYER\_VISIBLE\_ITEM\_12\_PROPERTIES            |                                             |
| 472  | PLAYER\_VISIBLE\_ITEM\_12\_SEED                  |                                             |
| 473  | PLAYER\_VISIBLE\_ITEM\_12\_PAD                   |                                             |
| 474  | PLAYER\_VISIBLE\_ITEM\_13\_CREATOR               |                                             |
| 476  | PLAYER\_VISIBLE\_ITEM\_13\_0                     | Item ID equipped on trinket 1 slot          |
| 489  | PLAYER\_VISIBLE\_ITEM\_13\_PROPERTIES            |                                             |
| 490  | PLAYER\_VISIBLE\_ITEM\_13\_SEED                  |                                             |
| 491  | PLAYER\_VISIBLE\_ITEM\_13\_PAD                   |                                             |
| 492  | PLAYER\_VISIBLE\_ITEM\_14\_CREATOR               |                                             |
| 494  | PLAYER\_VISIBLE\_ITEM\_14\_0                     | Item ID equipped on trinket 2 slot          |
| 507  | PLAYER\_VISIBLE\_ITEM\_14\_PROPERTIES            |                                             |
| 508  | PLAYER\_VISIBLE\_ITEM\_14\_SEED                  |                                             |
| 509  | PLAYER\_VISIBLE\_ITEM\_14\_PAD                   |                                             |
| 510  | PLAYER\_VISIBLE\_ITEM\_15\_CREATOR               |                                             |
| 512  | PLAYER\_VISIBLE\_ITEM\_15\_0                     | Item ID equipped on back slot               |
| 525  | PLAYER\_VISIBLE\_ITEM\_15\_PROPERTIES            |                                             |
| 526  | PLAYER\_VISIBLE\_ITEM\_15\_SEED                  |                                             |
| 527  | PLAYER\_VISIBLE\_ITEM\_15\_PAD                   |                                             |
| 528  | PLAYER\_VISIBLE\_ITEM\_16\_CREATOR               |                                             |
| 530  | PLAYER\_VISIBLE\_ITEM\_16\_0                     | Item ID equipped on main hand slot          |
| 543  | PLAYER\_VISIBLE\_ITEM\_16\_PROPERTIES            |                                             |
| 544  | PLAYER\_VISIBLE\_ITEM\_16\_SEED                  |                                             |
| 545  | PLAYER\_VISIBLE\_ITEM\_16\_PAD                   |                                             |
| 546  | PLAYER\_VISIBLE\_ITEM\_17\_CREATOR               |                                             |
| 548  | PLAYER\_VISIBLE\_ITEM\_17\_0                     | Item ID equipped on off hand slot           |
| 561  | PLAYER\_VISIBLE\_ITEM\_17\_PROPERTIES            |                                             |
| 562  | PLAYER\_VISIBLE\_ITEM\_17\_SEED                  |                                             |
| 563  | PLAYER\_VISIBLE\_ITEM\_17\_PAD                   |                                             |
| 564  | PLAYER\_VISIBLE\_ITEM\_18\_CREATOR               |                                             |
| 566  | PLAYER\_VISIBLE\_ITEM\_18\_0                     | Item ID equipped on ranged slot             |
| 579  | PLAYER\_VISIBLE\_ITEM\_18\_PROPERTIES            |                                             |
| 580  | PLAYER\_VISIBLE\_ITEM\_18\_SEED                  |                                             |
| 581  | PLAYER\_VISIBLE\_ITEM\_18\_PAD                   |                                             |
| 582  | PLAYER\_VISIBLE\_ITEM\_19\_CREATOR               |                                             |
| 584  | PLAYER\_VISIBLE\_ITEM\_19\_0                     | Item ID equipped on tabard                  |
| 597  | PLAYER\_VISIBLE\_ITEM\_19\_PROPERTIES            |                                             |
| 598  | PLAYER\_VISIBLE\_ITEM\_19\_SEED                  |                                             |
| 599  | PLAYER\_VISIBLE\_ITEM\_19\_PAD                   |                                             |
| 600  | PLAYER\_CHOSEN\_TITLE                            |                                             |
| 601  | PLAYER\_FIELD\_PAD\_0                            |                                             |
| 602  | PLAYER\_FIELD\_INV\_SLOT\_HEAD                   |                                             |
| 648  | PLAYER\_FIELD\_PACK\_SLOT\_1                     |                                             |
| 680  | PLAYER\_FIELD\_BANK\_SLOT\_1                     |                                             |
| 736  | PLAYER\_FIELD\_BANKBAG\_SLOT\_1                  |                                             |
| 750  | PLAYER\_FIELD\_VENDORBUYBACK\_SLOT\_1            |                                             |
| 774  | PLAYER\_FIELD\_KEYRING\_SLOT\_1                  |                                             |
| 838  | PLAYER\_FIELD\_VANITYPET\_SLOT\_1                |                                             |
| 874  | PLAYER\_FIELD\_CURRENCYTOKEN\_SLOT\_1            |                                             |
| 938  | PLAYER\_FIELD\_QUESTBAG\_SLOT\_1                 |                                             |
| 1002 | PLAYER\_FARSIGHT                                 |                                             |
| 1004 | PLAYER\_\_FIELD\_KNOWN\_TITLES                   |                                             |
| 1006 | PLAYER\_\_FIELD\_KNOWN\_TITLES1                  |                                             |
| 1008 | PLAYER\_FIELD\_KNOWN\_CURRENCIES                 |                                             |
| 1010 | PLAYER\_XP                                       |                                             |
| 1011 | PLAYER\_NEXT\_LEVEL\_XP                          |                                             |
| 1012 | PLAYER\_SKILL\_INFO\_1\_1                        |                                             |
| 1396 | PLAYER\_CHARACTER\_POINTS1                       |                                             |
| 1397 | PLAYER\_CHARACTER\_POINTS2                       |                                             |
| 1398 | PLAYER\_TRACK\_CREATURES                         |                                             |
| 1399 | PLAYER\_TRACK\_RESOURCES                         |                                             |
| 1400 | PLAYER\_BLOCK\_PERCENTAGE                        |                                             |
| 1401 | PLAYER\_DODGE\_PERCENTAGE                        |                                             |
| 1402 | PLAYER\_PARRY\_PERCENTAGE                        |                                             |
| 1403 | PLAYER\_EXPERTISE                                |                                             |
| 1404 | PLAYER\_OFFHAND\_EXPERTISE                       |                                             |
| 1405 | PLAYER\_CRIT\_PERCENTAGE                         |                                             |
| 1406 | PLAYER\_RANGED\_CRIT\_PERCENTAGE                 |                                             |
| 1407 | PLAYER\_OFFHAND\_CRIT\_PERCENTAGE                |                                             |
| 1408 | PLAYER\_SPELL\_CRIT\_PERCENTAGE1                 |                                             |
| 1415 | PLAYER\_SHIELD\_BLOCK                            |                                             |
| 1416 | PLAYER\_SHIELD\_BLOCK\_CRIT\_PERCENTAGE          |                                             |
| 1417 | PLAYER\_EXPLORED\_ZONES\_1                       |                                             |
| 1545 | PLAYER\_REST\_STATE\_EXPERIENCE                  |                                             |
| 1546 | PLAYER\_FIELD\_COINAGE                           | Money the player currently has (in copper). |
| 1547 | PLAYER\_FIELD\_MOD\_DAMAGE\_DONE\_POS            |                                             |
| 1554 | PLAYER\_FIELD\_MOD\_DAMAGE\_DONE\_NEG            |                                             |
| 1561 | PLAYER\_FIELD\_MOD\_DAMAGE\_DONE\_PCT            |                                             |
| 1568 | PLAYER\_FIELD\_MOD\_HEALING\_DONE\_POS           |                                             |
| 1569 | PLAYER\_FIELD\_MOD\_TARGET\_RESISTANCE           |                                             |
| 1570 | PLAYER\_FIELD\_MOD\_TARGET\_PHYSICAL\_RESISTANCE |                                             |
| 1571 | PLAYER\_FIELD\_BYTES                             |                                             |
| 1572 | PLAYER\_AMMO\_ID                                 |                                             |
| 1573 | PLAYER\_SELF\_RES\_SPELL                         |                                             |
| 1574 | PLAYER\_FIELD\_PVP\_MEDALS                       |                                             |
| 1575 | PLAYER\_FIELD\_BUYBACK\_PRICE\_1                 |                                             |
| 1587 | PLAYER\_FIELD\_BUYBACK\_TIMESTAMP\_1             |                                             |
| 1599 | PLAYER\_FIELD\_KILLS                             |                                             |
| 1600 | PLAYER\_FIELD\_TODAY\_CONTRIBUTION               |                                             |
| 1601 | PLAYER\_FIELD\_YESTERDAY\_CONTRIBUTION           |                                             |
| 1602 | PLAYER\_FIELD\_LIFETIME\_HONORBALE\_KILLS        |                                             |
| 1603 | PLAYER\_FIELD\_BYTES2                            |                                             |
| 1604 | PLAYER\_FIELD\_WATCHED\_FACTION\_INDEX           |                                             |
| 1605 | PLAYER\_FIELD\_COMBAT\_RATING\_1                 |                                             |
| 1630 | PLAYER\_FIELD\_ARENA\_TEAM\_INFO\_1\_1           |                                             |
| 1648 | PLAYER\_FIELD\_HONOR\_CURRENCY                   |                                             |
| 1649 | PLAYER\_FIELD\_ARENA\_CURRENCY                   |                                             |
| 1650 | PLAYER\_FIELD\_MAX\_LEVEL                        |                                             |
| 1651 | PLAYER\_FIELD\_DAILY\_QUESTS\_1                  |                                             |
| 1676 | PLAYER\_RUNE\_REGEN\_1                           |                                             |
| 1680 | PLAYER\_NO\_REAGENT\_COST\_1                     |                                             |
| 1683 | PLAYER\_FIELD\_GLYPH\_SLOTS\_1                   |                                             |
| 1691 | PLAYER\_FIELD\_GLYPHS\_1                         |                                             |
| 1699 | PLAYER\_GLYPHS\_ENABLED                          |                                             |

### 2.4.1 Character Data Table

**This table was last updated for 2.4.1 values.**

<table>
<colgroup>
<col width="5%" />
<col width="35%" />
<col width="59%" />
</colgroup>
<thead>
<tr class="header">
<th>Index</th>
<th>Value Name</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>OBJECT_FIELD_GUID</td>
<td>Character GUID (full GUID includes both index 0 and index 1 as 64bit number)</td>
</tr>
<tr class="even">
<td>2</td>
<td>OBJECT_FIELD_TYPE</td>
<td></td>
</tr>
<tr class="odd">
<td>3</td>
<td>OBJECT_FIELD_ENTRY</td>
<td></td>
</tr>
<tr class="even">
<td>4</td>
<td>OBJECT_FIELD_SCALE_X</td>
<td>Size of how model appears in-game (float value)</td>
</tr>
<tr class="odd">
<td>5</td>
<td>OBJECT_FIELD_PADDING</td>
<td></td>
</tr>
<tr class="even">
<td>6</td>
<td>UNIT_FIELD_CHARM</td>
<td></td>
</tr>
<tr class="odd">
<td>8</td>
<td>UNIT_FIELD_SUMMON</td>
<td></td>
</tr>
<tr class="even">
<td>10</td>
<td>UNIT_FIELD_CHARMEDBY</td>
<td></td>
</tr>
<tr class="odd">
<td>12</td>
<td>UNIT_FIELD_SUMMONEDBY</td>
<td></td>
</tr>
<tr class="even">
<td>14</td>
<td>UNIT_FIELD_CREATEDBY</td>
<td></td>
</tr>
<tr class="odd">
<td>16</td>
<td>UNIT_FIELD_TARGET</td>
<td></td>
</tr>
<tr class="even">
<td>18</td>
<td>UNIT_FIELD_PERSUADED</td>
<td></td>
</tr>
<tr class="odd">
<td>20</td>
<td>UNIT_FIELD_CHANNEL_OBJECT</td>
<td></td>
</tr>
<tr class="even">
<td>22</td>
<td>UNIT_FIELD_HEALTH</td>
<td>Current health</td>
</tr>
<tr class="odd">
<td>23</td>
<td>UNIT_FIELD_POWER1</td>
<td>Current mana</td>
</tr>
<tr class="even">
<td>24</td>
<td>UNIT_FIELD_POWER2</td>
<td>Current rage</td>
</tr>
<tr class="odd">
<td>25</td>
<td>UNIT_FIELD_POWER3</td>
<td>Current focus</td>
</tr>
<tr class="even">
<td>26</td>
<td>UNIT_FIELD_POWER4</td>
<td>Current energy</td>
</tr>
<tr class="odd">
<td>27</td>
<td>UNIT_FIELD_POWER5</td>
<td>Current happiness</td>
</tr>
<tr class="even">
<td>28</td>
<td>UNIT_FIELD_MAXHEALTH</td>
<td>Max health</td>
</tr>
<tr class="odd">
<td>29</td>
<td>UNIT_FIELD_MAXPOWER1</td>
<td>Max mana</td>
</tr>
<tr class="even">
<td>30</td>
<td>UNIT_FIELD_MAXPOWER2</td>
<td>Max rage</td>
</tr>
<tr class="odd">
<td>31</td>
<td>UNIT_FIELD_MAXPOWER3</td>
<td>Max focus</td>
</tr>
<tr class="even">
<td>32</td>
<td>UNIT_FIELD_MAXPOWER4</td>
<td>Max energy</td>
</tr>
<tr class="odd">
<td>33</td>
<td>UNIT_FIELD_MAXPOWER5</td>
<td>Max happiness</td>
</tr>
<tr class="even">
<td>34</td>
<td>UNIT_FIELD_LEVEL</td>
<td>Character level</td>
</tr>
<tr class="odd">
<td>35</td>
<td>UNIT_FIELD_FACTIONTEMPLATE</td>
<td>Currently used faction template ID (<a href="FactionTemplate.dbc" class="uri">FactionTemplate.dbc</a>)</td>
</tr>
<tr class="even">
<td>36</td>
<td>UNIT_FIELD_BYTES_0</td>
<td>(class_ &lt;&lt; 8)</td>
</tr>
<tr class="odd">
<td>37</td>
<td>UNIT_VIRTUAL_ITEM_SLOT_DISPLAY</td>
<td></td>
</tr>
<tr class="even">
<td>40</td>
<td>UNIT_VIRTUAL_ITEM_INFO</td>
<td></td>
</tr>
<tr class="odd">
<td>46</td>
<td>UNIT_FIELD_FLAGS</td>
<td></td>
</tr>
<tr class="even">
<td>47</td>
<td>UNIT_FIELD_FLAGS_2</td>
<td></td>
</tr>
<tr class="odd">
<td>48</td>
<td>UNIT_FIELD_AURA</td>
<td></td>
</tr>
<tr class="even">
<td>104</td>
<td>UNIT_FIELD_AURAFLAGS</td>
<td></td>
</tr>
<tr class="odd">
<td>118</td>
<td>UNIT_FIELD_AURALEVELS</td>
<td></td>
</tr>
<tr class="even">
<td>132</td>
<td>UNIT_FIELD_AURAAPPLICATIONS</td>
<td></td>
</tr>
<tr class="odd">
<td>146</td>
<td>UNIT_FIELD_AURASTATE</td>
<td></td>
</tr>
<tr class="even">
<td>147</td>
<td>UNIT_FIELD_BASEATTACKTIME</td>
<td></td>
</tr>
<tr class="odd">
<td>148</td>
<td>UNIT_FIELD_OFFHANDATTACKTIME</td>
<td></td>
</tr>
<tr class="even">
<td>149</td>
<td>UNIT_FIELD_RANGEDATTACKTIME</td>
<td></td>
</tr>
<tr class="odd">
<td>150</td>
<td>UNIT_FIELD_BOUNDINGRADIUS</td>
<td></td>
</tr>
<tr class="even">
<td>151</td>
<td>UNIT_FIELD_COMBATREACH</td>
<td></td>
</tr>
<tr class="odd">
<td>152</td>
<td>UNIT_FIELD_DISPLAYID</td>
<td>Current model ID (can be different from regular if character is morphed, etc)</td>
</tr>
<tr class="even">
<td>153</td>
<td>UNIT_FIELD_NATIVEDISPLAYID</td>
<td>The native model ID. Model always reverts to this number when player is demorphed.</td>
</tr>
<tr class="odd">
<td>154</td>
<td>UNIT_FIELD_MOUNTDISPLAYID</td>
<td></td>
</tr>
<tr class="even">
<td>155</td>
<td>UNIT_FIELD_MINDAMAGE</td>
<td></td>
</tr>
<tr class="odd">
<td>156</td>
<td>UNIT_FIELD_MAXDAMAGE</td>
<td></td>
</tr>
<tr class="even">
<td>157</td>
<td>UNIT_FIELD_MINOFFHANDDAMAGE</td>
<td></td>
</tr>
<tr class="odd">
<td>158</td>
<td>UNIT_FIELD_MAXOFFHANDDAMAGE</td>
<td></td>
</tr>
<tr class="even">
<td>159</td>
<td>UNIT_FIELD_BYTES_1</td>
<td></td>
</tr>
<tr class="odd">
<td>160</td>
<td>UNIT_FIELD_PETNUMBER</td>
<td></td>
</tr>
<tr class="even">
<td>161</td>
<td>UNIT_FIELD_PET_NAME_TIMESTAMP</td>
<td></td>
</tr>
<tr class="odd">
<td>162</td>
<td>UNIT_FIELD_PETEXPERIENCE</td>
<td></td>
</tr>
<tr class="even">
<td>163</td>
<td>UNIT_FIELD_PETNEXTLEVELEXP</td>
<td></td>
</tr>
<tr class="odd">
<td>164</td>
<td>UNIT_DYNAMIC_FLAGS</td>
<td></td>
</tr>
<tr class="even">
<td>165</td>
<td>UNIT_CHANNEL_SPELL</td>
<td></td>
</tr>
<tr class="odd">
<td>166</td>
<td>UNIT_MOD_CAST_SPEED</td>
<td></td>
</tr>
<tr class="even">
<td>167</td>
<td>UNIT_CREATED_BY_SPELL</td>
<td></td>
</tr>
<tr class="odd">
<td>168</td>
<td>UNIT_NPC_FLAGS</td>
<td></td>
</tr>
<tr class="even">
<td>169</td>
<td>UNIT_NPC_EMOTESTATE</td>
<td></td>
</tr>
<tr class="odd">
<td>170</td>
<td>UNIT_TRAINING_POINTS</td>
<td></td>
</tr>
<tr class="even">
<td>171</td>
<td>UNIT_FIELD_STAT0</td>
<td>Base strength (before any item bonuses)</td>
</tr>
<tr class="odd">
<td>172</td>
<td>UNIT_FIELD_STAT1</td>
<td>Base agility</td>
</tr>
<tr class="even">
<td>173</td>
<td>UNIT_FIELD_STAT2</td>
<td>Base stamina</td>
</tr>
<tr class="odd">
<td>174</td>
<td>UNIT_FIELD_STAT3</td>
<td>Base intellect</td>
</tr>
<tr class="even">
<td>175</td>
<td>UNIT_FIELD_STAT4</td>
<td>Base spirit</td>
</tr>
<tr class="odd">
<td>176</td>
<td>UNIT_FIELD_POSSTAT0</td>
<td></td>
</tr>
<tr class="even">
<td>177</td>
<td>UNIT_FIELD_POSSTAT1</td>
<td></td>
</tr>
<tr class="odd">
<td>178</td>
<td>UNIT_FIELD_POSSTAT2</td>
<td></td>
</tr>
<tr class="even">
<td>179</td>
<td>UNIT_FIELD_POSSTAT3</td>
<td></td>
</tr>
<tr class="odd">
<td>180</td>
<td>UNIT_FIELD_POSSTAT4</td>
<td></td>
</tr>
<tr class="even">
<td>181</td>
<td>UNIT_FIELD_NEGSTAT0</td>
<td></td>
</tr>
<tr class="odd">
<td>182</td>
<td>UNIT_FIELD_NEGSTAT1</td>
<td></td>
</tr>
<tr class="even">
<td>183</td>
<td>UNIT_FIELD_NEGSTAT2</td>
<td></td>
</tr>
<tr class="odd">
<td>184</td>
<td>UNIT_FIELD_NEGSTAT3</td>
<td></td>
</tr>
<tr class="even">
<td>185</td>
<td>UNIT_FIELD_NEGSTAT4</td>
<td></td>
</tr>
<tr class="odd">
<td>186</td>
<td>UNIT_FIELD_RESISTANCES</td>
<td>Base armor (before any item bonuses)</td>
</tr>
<tr class="even">
<td>187</td>
<td></td>
<td>Base holy resistance</td>
</tr>
<tr class="odd">
<td>188</td>
<td></td>
<td>Base fire resistance</td>
</tr>
<tr class="even">
<td>189</td>
<td></td>
<td>Base nature resistance</td>
</tr>
<tr class="odd">
<td>190</td>
<td></td>
<td>Base frost resistance</td>
</tr>
<tr class="even">
<td>191</td>
<td></td>
<td>Base shadow resistance</td>
</tr>
<tr class="odd">
<td>192</td>
<td></td>
<td>Base arcane resistance</td>
</tr>
<tr class="even">
<td>193</td>
<td>UNIT_FIELD_RESISTANCEBUFFMODSPOSITIVE</td>
<td></td>
</tr>
<tr class="odd">
<td>200</td>
<td>UNIT_FIELD_RESISTANCEBUFFMODSNEGATIVE</td>
<td></td>
</tr>
<tr class="even">
<td>207</td>
<td>UNIT_FIELD_BASE_MANA</td>
<td></td>
</tr>
<tr class="odd">
<td>208</td>
<td>UNIT_FIELD_BASE_HEALTH</td>
<td></td>
</tr>
<tr class="even">
<td>209</td>
<td>UNIT_FIELD_BYTES_2</td>
<td></td>
</tr>
<tr class="odd">
<td>210</td>
<td>UNIT_FIELD_ATTACK_POWER</td>
<td></td>
</tr>
<tr class="even">
<td>211</td>
<td>UNIT_FIELD_ATTACK_POWER_MODS</td>
<td></td>
</tr>
<tr class="odd">
<td>212</td>
<td>UNIT_FIELD_ATTACK_POWER_MULTIPLIER</td>
<td></td>
</tr>
<tr class="even">
<td>213</td>
<td>UNIT_FIELD_RANGED_ATTACK_POWER</td>
<td></td>
</tr>
<tr class="odd">
<td>214</td>
<td>UNIT_FIELD_RANGED_ATTACK_POWER_MODS</td>
<td></td>
</tr>
<tr class="even">
<td>215</td>
<td>UNIT_FIELD_RANGED_ATTACK_POWER_MULTIPLIER</td>
<td></td>
</tr>
<tr class="odd">
<td>216</td>
<td>UNIT_FIELD_MINRANGEDDAMAGE</td>
<td></td>
</tr>
<tr class="even">
<td>217</td>
<td>UNIT_FIELD_MAXRANGEDDAMAGE</td>
<td></td>
</tr>
<tr class="odd">
<td>218</td>
<td>UNIT_FIELD_POWER_COST_MODIFIER</td>
<td></td>
</tr>
<tr class="even">
<td>225</td>
<td>UNIT_FIELD_POWER_COST_MULTIPLIER</td>
<td></td>
</tr>
<tr class="odd">
<td>232</td>
<td>UNIT_FIELD_MAXHEALTHMODIFIER</td>
<td></td>
</tr>
<tr class="even">
<td>233</td>
<td>UNIT_FIELD_PADDING</td>
<td></td>
</tr>
<tr class="odd">
<td>234</td>
<td>PLAYER_DUEL_ARBITER</td>
<td></td>
</tr>
<tr class="even">
<td>236</td>
<td>PLAYER_FLAGS</td>
<td></td>
</tr>
<tr class="odd">
<td>237</td>
<td>PLAYER_GUILDID</td>
<td>guild.guildid]])</td>
</tr>
<tr class="even">
<td>238</td>
<td>PLAYER_GUILDRANK</td>
<td>guild_rank.rid]])</td>
</tr>
<tr class="odd">
<td>239</td>
<td>PLAYER_BYTES</td>
<td>(face &lt;&lt; 8)</td>
</tr>
<tr class="even">
<td>240</td>
<td>PLAYER_BYTES_2</td>
<td>(0x00 &lt;&lt; 8)</td>
</tr>
<tr class="odd">
<td>241</td>
<td>PLAYER_BYTES_3</td>
<td>gender</td>
</tr>
<tr class="even">
<td>242</td>
<td>PLAYER_DUEL_TEAM</td>
<td></td>
</tr>
<tr class="odd">
<td>243</td>
<td>PLAYER_GUILD_TIMESTAMP</td>
<td></td>
</tr>
<tr class="even">
<td>244</td>
<td>PLAYER_QUEST_LOG_1_1</td>
<td></td>
</tr>
<tr class="odd">
<td>245</td>
<td>PLAYER_QUEST_LOG_1_2</td>
<td></td>
</tr>
<tr class="even">
<td>246</td>
<td>PLAYER_QUEST_LOG_1_3</td>
<td></td>
</tr>
<tr class="odd">
<td>247</td>
<td>PLAYER_QUEST_LOG_1_4</td>
<td></td>
</tr>
<tr class="even">
<td>248</td>
<td>PLAYER_QUEST_LOG_2_1</td>
<td></td>
</tr>
<tr class="odd">
<td>249</td>
<td>PLAYER_QUEST_LOG_2_2</td>
<td></td>
</tr>
<tr class="even">
<td>250</td>
<td>PLAYER_QUEST_LOG_2_3</td>
<td></td>
</tr>
<tr class="odd">
<td>251</td>
<td>PLAYER_QUEST_LOG_2_4</td>
<td></td>
</tr>
<tr class="even">
<td>252</td>
<td>PLAYER_QUEST_LOG_3_1</td>
<td></td>
</tr>
<tr class="odd">
<td>253</td>
<td>PLAYER_QUEST_LOG_3_2</td>
<td></td>
</tr>
<tr class="even">
<td>254</td>
<td>PLAYER_QUEST_LOG_3_3</td>
<td></td>
</tr>
<tr class="odd">
<td>255</td>
<td>PLAYER_QUEST_LOG_3_4</td>
<td></td>
</tr>
<tr class="even">
<td>256</td>
<td>PLAYER_QUEST_LOG_4_1</td>
<td></td>
</tr>
<tr class="odd">
<td>257</td>
<td>PLAYER_QUEST_LOG_4_2</td>
<td></td>
</tr>
<tr class="even">
<td>258</td>
<td>PLAYER_QUEST_LOG_4_3</td>
<td></td>
</tr>
<tr class="odd">
<td>259</td>
<td>PLAYER_QUEST_LOG_4_4</td>
<td></td>
</tr>
<tr class="even">
<td>260</td>
<td>PLAYER_QUEST_LOG_5_1</td>
<td></td>
</tr>
<tr class="odd">
<td>261</td>
<td>PLAYER_QUEST_LOG_5_2</td>
<td></td>
</tr>
<tr class="even">
<td>262</td>
<td>PLAYER_QUEST_LOG_5_3</td>
<td></td>
</tr>
<tr class="odd">
<td>263</td>
<td>PLAYER_QUEST_LOG_5_4</td>
<td></td>
</tr>
<tr class="even">
<td>264</td>
<td>PLAYER_QUEST_LOG_6_1</td>
<td></td>
</tr>
<tr class="odd">
<td>265</td>
<td>PLAYER_QUEST_LOG_6_2</td>
<td></td>
</tr>
<tr class="even">
<td>266</td>
<td>PLAYER_QUEST_LOG_6_3</td>
<td></td>
</tr>
<tr class="odd">
<td>267</td>
<td>PLAYER_QUEST_LOG_6_4</td>
<td></td>
</tr>
<tr class="even">
<td>268</td>
<td>PLAYER_QUEST_LOG_7_1</td>
<td></td>
</tr>
<tr class="odd">
<td>269</td>
<td>PLAYER_QUEST_LOG_7_2</td>
<td></td>
</tr>
<tr class="even">
<td>270</td>
<td>PLAYER_QUEST_LOG_7_3</td>
<td></td>
</tr>
<tr class="odd">
<td>271</td>
<td>PLAYER_QUEST_LOG_7_4</td>
<td></td>
</tr>
<tr class="even">
<td>272</td>
<td>PLAYER_QUEST_LOG_8_1</td>
<td></td>
</tr>
<tr class="odd">
<td>273</td>
<td>PLAYER_QUEST_LOG_8_2</td>
<td></td>
</tr>
<tr class="even">
<td>274</td>
<td>PLAYER_QUEST_LOG_8_3</td>
<td></td>
</tr>
<tr class="odd">
<td>275</td>
<td>PLAYER_QUEST_LOG_8_4</td>
<td></td>
</tr>
<tr class="even">
<td>276</td>
<td>PLAYER_QUEST_LOG_9_1</td>
<td></td>
</tr>
<tr class="odd">
<td>277</td>
<td>PLAYER_QUEST_LOG_9_2</td>
<td></td>
</tr>
<tr class="even">
<td>278</td>
<td>PLAYER_QUEST_LOG_9_3</td>
<td></td>
</tr>
<tr class="odd">
<td>279</td>
<td>PLAYER_QUEST_LOG_9_4</td>
<td></td>
</tr>
<tr class="even">
<td>280</td>
<td>PLAYER_QUEST_LOG_10_1</td>
<td></td>
</tr>
<tr class="odd">
<td>281</td>
<td>PLAYER_QUEST_LOG_10_2</td>
<td></td>
</tr>
<tr class="even">
<td>282</td>
<td>PLAYER_QUEST_LOG_10_3</td>
<td></td>
</tr>
<tr class="odd">
<td>283</td>
<td>PLAYER_QUEST_LOG_10_4</td>
<td></td>
</tr>
<tr class="even">
<td>284</td>
<td>PLAYER_QUEST_LOG_11_1</td>
<td></td>
</tr>
<tr class="odd">
<td>285</td>
<td>PLAYER_QUEST_LOG_11_2</td>
<td></td>
</tr>
<tr class="even">
<td>286</td>
<td>PLAYER_QUEST_LOG_11_3</td>
<td></td>
</tr>
<tr class="odd">
<td>287</td>
<td>PLAYER_QUEST_LOG_11_4</td>
<td></td>
</tr>
<tr class="even">
<td>288</td>
<td>PLAYER_QUEST_LOG_12_1</td>
<td></td>
</tr>
<tr class="odd">
<td>289</td>
<td>PLAYER_QUEST_LOG_12_2</td>
<td></td>
</tr>
<tr class="even">
<td>290</td>
<td>PLAYER_QUEST_LOG_12_3</td>
<td></td>
</tr>
<tr class="odd">
<td>291</td>
<td>PLAYER_QUEST_LOG_12_4</td>
<td></td>
</tr>
<tr class="even">
<td>292</td>
<td>PLAYER_QUEST_LOG_13_1</td>
<td></td>
</tr>
<tr class="odd">
<td>293</td>
<td>PLAYER_QUEST_LOG_13_2</td>
<td></td>
</tr>
<tr class="even">
<td>294</td>
<td>PLAYER_QUEST_LOG_13_3</td>
<td></td>
</tr>
<tr class="odd">
<td>295</td>
<td>PLAYER_QUEST_LOG_13_4</td>
<td></td>
</tr>
<tr class="even">
<td>296</td>
<td>PLAYER_QUEST_LOG_14_1</td>
<td></td>
</tr>
<tr class="odd">
<td>297</td>
<td>PLAYER_QUEST_LOG_14_2</td>
<td></td>
</tr>
<tr class="even">
<td>298</td>
<td>PLAYER_QUEST_LOG_14_3</td>
<td></td>
</tr>
<tr class="odd">
<td>299</td>
<td>PLAYER_QUEST_LOG_14_4</td>
<td></td>
</tr>
<tr class="even">
<td>300</td>
<td>PLAYER_QUEST_LOG_15_1</td>
<td></td>
</tr>
<tr class="odd">
<td>301</td>
<td>PLAYER_QUEST_LOG_15_2</td>
<td></td>
</tr>
<tr class="even">
<td>302</td>
<td>PLAYER_QUEST_LOG_15_3</td>
<td></td>
</tr>
<tr class="odd">
<td>303</td>
<td>PLAYER_QUEST_LOG_15_4</td>
<td></td>
</tr>
<tr class="even">
<td>304</td>
<td>PLAYER_QUEST_LOG_16_1</td>
<td></td>
</tr>
<tr class="odd">
<td>305</td>
<td>PLAYER_QUEST_LOG_16_2</td>
<td></td>
</tr>
<tr class="even">
<td>306</td>
<td>PLAYER_QUEST_LOG_16_3</td>
<td></td>
</tr>
<tr class="odd">
<td>307</td>
<td>PLAYER_QUEST_LOG_16_4</td>
<td></td>
</tr>
<tr class="even">
<td>308</td>
<td>PLAYER_QUEST_LOG_17_1</td>
<td></td>
</tr>
<tr class="odd">
<td>309</td>
<td>PLAYER_QUEST_LOG_17_2</td>
<td></td>
</tr>
<tr class="even">
<td>310</td>
<td>PLAYER_QUEST_LOG_17_3</td>
<td></td>
</tr>
<tr class="odd">
<td>311</td>
<td>PLAYER_QUEST_LOG_17_4</td>
<td></td>
</tr>
<tr class="even">
<td>312</td>
<td>PLAYER_QUEST_LOG_18_1</td>
<td></td>
</tr>
<tr class="odd">
<td>313</td>
<td>PLAYER_QUEST_LOG_18_2</td>
<td></td>
</tr>
<tr class="even">
<td>314</td>
<td>PLAYER_QUEST_LOG_18_3</td>
<td></td>
</tr>
<tr class="odd">
<td>315</td>
<td>PLAYER_QUEST_LOG_18_4</td>
<td></td>
</tr>
<tr class="even">
<td>316</td>
<td>PLAYER_QUEST_LOG_19_1</td>
<td></td>
</tr>
<tr class="odd">
<td>317</td>
<td>PLAYER_QUEST_LOG_19_2</td>
<td></td>
</tr>
<tr class="even">
<td>318</td>
<td>PLAYER_QUEST_LOG_19_3</td>
<td></td>
</tr>
<tr class="odd">
<td>319</td>
<td>PLAYER_QUEST_LOG_19_4</td>
<td></td>
</tr>
<tr class="even">
<td>320</td>
<td>PLAYER_QUEST_LOG_20_1</td>
<td></td>
</tr>
<tr class="odd">
<td>321</td>
<td>PLAYER_QUEST_LOG_20_2</td>
<td></td>
</tr>
<tr class="even">
<td>322</td>
<td>PLAYER_QUEST_LOG_20_3</td>
<td></td>
</tr>
<tr class="odd">
<td>323</td>
<td>PLAYER_QUEST_LOG_20_4</td>
<td></td>
</tr>
<tr class="even">
<td>324</td>
<td>PLAYER_QUEST_LOG_21_1</td>
<td></td>
</tr>
<tr class="odd">
<td>325</td>
<td>PLAYER_QUEST_LOG_21_2</td>
<td></td>
</tr>
<tr class="even">
<td>326</td>
<td>PLAYER_QUEST_LOG_21_3</td>
<td></td>
</tr>
<tr class="odd">
<td>327</td>
<td>PLAYER_QUEST_LOG_21_4</td>
<td></td>
</tr>
<tr class="even">
<td>328</td>
<td>PLAYER_QUEST_LOG_22_1</td>
<td></td>
</tr>
<tr class="odd">
<td>329</td>
<td>PLAYER_QUEST_LOG_22_2</td>
<td></td>
</tr>
<tr class="even">
<td>330</td>
<td>PLAYER_QUEST_LOG_22_3</td>
<td></td>
</tr>
<tr class="odd">
<td>331</td>
<td>PLAYER_QUEST_LOG_22_4</td>
<td></td>
</tr>
<tr class="even">
<td>332</td>
<td>PLAYER_QUEST_LOG_23_1</td>
<td></td>
</tr>
<tr class="odd">
<td>333</td>
<td>PLAYER_QUEST_LOG_23_2</td>
<td></td>
</tr>
<tr class="even">
<td>334</td>
<td>PLAYER_QUEST_LOG_23_3</td>
<td></td>
</tr>
<tr class="odd">
<td>335</td>
<td>PLAYER_QUEST_LOG_23_4</td>
<td></td>
</tr>
<tr class="even">
<td>336</td>
<td>PLAYER_QUEST_LOG_24_1</td>
<td></td>
</tr>
<tr class="odd">
<td>337</td>
<td>PLAYER_QUEST_LOG_24_2</td>
<td></td>
</tr>
<tr class="even">
<td>338</td>
<td>PLAYER_QUEST_LOG_24_3</td>
<td></td>
</tr>
<tr class="odd">
<td>339</td>
<td>PLAYER_QUEST_LOG_24_4</td>
<td></td>
</tr>
<tr class="even">
<td>340</td>
<td>PLAYER_QUEST_LOG_25_1</td>
<td></td>
</tr>
<tr class="odd">
<td>341</td>
<td>PLAYER_QUEST_LOG_25_2</td>
<td></td>
</tr>
<tr class="even">
<td>342</td>
<td>PLAYER_QUEST_LOG_25_3</td>
<td></td>
</tr>
<tr class="odd">
<td>343</td>
<td>PLAYER_QUEST_LOG_25_4</td>
<td></td>
</tr>
<tr class="even">
<td>344</td>
<td>PLAYER_VISIBLE_ITEM_1_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>346</td>
<td>PLAYER_VISIBLE_ITEM_1_0</td>
<td>Item ID equipped on head slot</td>
</tr>
<tr class="even">
<td>358</td>
<td>PLAYER_VISIBLE_ITEM_1_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>359</td>
<td>PLAYER_VISIBLE_ITEM_1_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>360</td>
<td>PLAYER_VISIBLE_ITEM_2_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>362</td>
<td>PLAYER_VISIBLE_ITEM_2_0</td>
<td>Item ID equipped on neck slot</td>
</tr>
<tr class="even">
<td>374</td>
<td>PLAYER_VISIBLE_ITEM_2_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>375</td>
<td>PLAYER_VISIBLE_ITEM_2_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>376</td>
<td>PLAYER_VISIBLE_ITEM_3_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>378</td>
<td>PLAYER_VISIBLE_ITEM_3_0</td>
<td>Item ID equipped on shoulder slot</td>
</tr>
<tr class="even">
<td>390</td>
<td>PLAYER_VISIBLE_ITEM_3_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>391</td>
<td>PLAYER_VISIBLE_ITEM_3_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>392</td>
<td>PLAYER_VISIBLE_ITEM_4_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>394</td>
<td>PLAYER_VISIBLE_ITEM_4_0</td>
<td>Item ID equipped on shirt slot</td>
</tr>
<tr class="even">
<td>406</td>
<td>PLAYER_VISIBLE_ITEM_4_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>407</td>
<td>PLAYER_VISIBLE_ITEM_4_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>408</td>
<td>PLAYER_VISIBLE_ITEM_5_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>410</td>
<td>PLAYER_VISIBLE_ITEM_5_0</td>
<td>Item ID equipped on chest slot</td>
</tr>
<tr class="even">
<td>422</td>
<td>PLAYER_VISIBLE_ITEM_5_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>423</td>
<td>PLAYER_VISIBLE_ITEM_5_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>424</td>
<td>PLAYER_VISIBLE_ITEM_6_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>426</td>
<td>PLAYER_VISIBLE_ITEM_6_0</td>
<td>Item ID equipped on belt slot</td>
</tr>
<tr class="even">
<td>438</td>
<td>PLAYER_VISIBLE_ITEM_6_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>439</td>
<td>PLAYER_VISIBLE_ITEM_6_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>440</td>
<td>PLAYER_VISIBLE_ITEM_7_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>442</td>
<td>PLAYER_VISIBLE_ITEM_7_0</td>
<td>Item ID equipped on legs slot</td>
</tr>
<tr class="even">
<td>454</td>
<td>PLAYER_VISIBLE_ITEM_7_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>455</td>
<td>PLAYER_VISIBLE_ITEM_7_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>456</td>
<td>PLAYER_VISIBLE_ITEM_8_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>458</td>
<td>PLAYER_VISIBLE_ITEM_8_0</td>
<td>Item ID equipped on feet slot</td>
</tr>
<tr class="even">
<td>470</td>
<td>PLAYER_VISIBLE_ITEM_8_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>471</td>
<td>PLAYER_VISIBLE_ITEM_8_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>472</td>
<td>PLAYER_VISIBLE_ITEM_9_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>474</td>
<td>PLAYER_VISIBLE_ITEM_9_0</td>
<td>Item ID equipped on wrist slot</td>
</tr>
<tr class="even">
<td>486</td>
<td>PLAYER_VISIBLE_ITEM_9_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>487</td>
<td>PLAYER_VISIBLE_ITEM_9_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>488</td>
<td>PLAYER_VISIBLE_ITEM_10_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>490</td>
<td>PLAYER_VISIBLE_ITEM_10_0</td>
<td>Item ID equipped on gloves slot</td>
</tr>
<tr class="even">
<td>502</td>
<td>PLAYER_VISIBLE_ITEM_10_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>503</td>
<td>PLAYER_VISIBLE_ITEM_10_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>504</td>
<td>PLAYER_VISIBLE_ITEM_11_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>506</td>
<td>PLAYER_VISIBLE_ITEM_11_0</td>
<td>Item ID equipped on finger 1 slot</td>
</tr>
<tr class="even">
<td>518</td>
<td>PLAYER_VISIBLE_ITEM_11_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>519</td>
<td>PLAYER_VISIBLE_ITEM_11_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>520</td>
<td>PLAYER_VISIBLE_ITEM_12_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>522</td>
<td>PLAYER_VISIBLE_ITEM_12_0</td>
<td>Item ID equipped on finger 2 slot</td>
</tr>
<tr class="even">
<td>534</td>
<td>PLAYER_VISIBLE_ITEM_12_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>535</td>
<td>PLAYER_VISIBLE_ITEM_12_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>536</td>
<td>PLAYER_VISIBLE_ITEM_13_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>538</td>
<td>PLAYER_VISIBLE_ITEM_13_0</td>
<td>Item ID equipped on trinket 1 slot</td>
</tr>
<tr class="even">
<td>550</td>
<td>PLAYER_VISIBLE_ITEM_13_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>551</td>
<td>PLAYER_VISIBLE_ITEM_13_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>552</td>
<td>PLAYER_VISIBLE_ITEM_14_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>554</td>
<td>PLAYER_VISIBLE_ITEM_14_0</td>
<td>Item ID equipped on trinket 2 slot</td>
</tr>
<tr class="even">
<td>566</td>
<td>PLAYER_VISIBLE_ITEM_14_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>567</td>
<td>PLAYER_VISIBLE_ITEM_14_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>568</td>
<td>PLAYER_VISIBLE_ITEM_15_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>570</td>
<td>PLAYER_VISIBLE_ITEM_15_0</td>
<td>Item ID equipped on back slot</td>
</tr>
<tr class="even">
<td>582</td>
<td>PLAYER_VISIBLE_ITEM_15_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>583</td>
<td>PLAYER_VISIBLE_ITEM_15_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>584</td>
<td>PLAYER_VISIBLE_ITEM_16_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>586</td>
<td>PLAYER_VISIBLE_ITEM_16_0</td>
<td>Item ID equipped on main hand slot</td>
</tr>
<tr class="even">
<td>598</td>
<td>PLAYER_VISIBLE_ITEM_16_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>599</td>
<td>PLAYER_VISIBLE_ITEM_16_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>600</td>
<td>PLAYER_VISIBLE_ITEM_17_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>602</td>
<td>PLAYER_VISIBLE_ITEM_17_0</td>
<td>Item ID equipped on off hand slot</td>
</tr>
<tr class="even">
<td>614</td>
<td>PLAYER_VISIBLE_ITEM_17_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>615</td>
<td>PLAYER_VISIBLE_ITEM_17_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>616</td>
<td>PLAYER_VISIBLE_ITEM_18_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>618</td>
<td>PLAYER_VISIBLE_ITEM_18_0</td>
<td>Item ID equipped on ranged slot</td>
</tr>
<tr class="even">
<td>630</td>
<td>PLAYER_VISIBLE_ITEM_18_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>631</td>
<td>PLAYER_VISIBLE_ITEM_18_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>632</td>
<td>PLAYER_VISIBLE_ITEM_19_CREATOR</td>
<td></td>
</tr>
<tr class="odd">
<td>634</td>
<td>PLAYER_VISIBLE_ITEM_19_0</td>
<td>Item ID equipped on tabard</td>
</tr>
<tr class="even">
<td>646</td>
<td>PLAYER_VISIBLE_ITEM_19_PROPERTIES</td>
<td></td>
</tr>
<tr class="odd">
<td>647</td>
<td>PLAYER_VISIBLE_ITEM_19_PAD</td>
<td></td>
</tr>
<tr class="even">
<td>648</td>
<td>PLAYER_CHOSEN_TITLE</td>
<td></td>
</tr>
<tr class="odd">
<td>649</td>
<td>PLAYER_FIELD_PAD_0</td>
<td></td>
</tr>
<tr class="even">
<td>650</td>
<td>PLAYER_FIELD_INV_SLOT_HEAD</td>
<td></td>
</tr>
<tr class="odd">
<td>696</td>
<td>PLAYER_FIELD_PACK_SLOT_1</td>
<td></td>
</tr>
<tr class="even">
<td>728</td>
<td>PLAYER_FIELD_BANK_SLOT_1</td>
<td></td>
</tr>
<tr class="odd">
<td>784</td>
<td>PLAYER_FIELD_BANKBAG_SLOT_1</td>
<td></td>
</tr>
<tr class="even">
<td>798</td>
<td>PLAYER_FIELD_VENDORBUYBACK_SLOT_1</td>
<td></td>
</tr>
<tr class="odd">
<td>822</td>
<td>PLAYER_FIELD_KEYRING_SLOT_1</td>
<td></td>
</tr>
<tr class="even">
<td>886</td>
<td>PLAYER_FIELD_VANITYPET_SLOT_1</td>
<td></td>
</tr>
<tr class="odd">
<td>922</td>
<td>PLAYER_FARSIGHT</td>
<td></td>
</tr>
<tr class="even">
<td>924</td>
<td>PLAYER__FIELD_KNOWN_TITLES</td>
<td></td>
</tr>
<tr class="odd">
<td>926</td>
<td>PLAYER_XP</td>
<td>Current XP</td>
</tr>
<tr class="even">
<td>927</td>
<td>PLAYER_NEXT_LEVEL_XP</td>
<td>XP needed to level up</td>
</tr>
<tr class="odd">
<td>928</td>
<td>PLAYER_SKILL_INFO_1_1</td>
<td></td>
</tr>
<tr class="even">
<td>1312</td>
<td>PLAYER_CHARACTER_POINTS1</td>
<td>Number of unused talent points</td>
</tr>
<tr class="odd">
<td>1313</td>
<td>PLAYER_CHARACTER_POINTS2</td>
<td>Number of free primary professions</td>
</tr>
<tr class="even">
<td>1314</td>
<td>PLAYER_TRACK_CREATURES</td>
<td></td>
</tr>
<tr class="odd">
<td>1315</td>
<td>PLAYER_TRACK_RESOURCES</td>
<td></td>
</tr>
<tr class="even">
<td>1316</td>
<td>PLAYER_BLOCK_PERCENTAGE</td>
<td></td>
</tr>
<tr class="odd">
<td>1317</td>
<td>PLAYER_DODGE_PERCENTAGE</td>
<td></td>
</tr>
<tr class="even">
<td>1318</td>
<td>PLAYER_PARRY_PERCENTAGE</td>
<td></td>
</tr>
<tr class="odd">
<td>1319</td>
<td>PLAYER_EXPERTISE</td>
<td></td>
</tr>
<tr class="even">
<td>1320</td>
<td>PLAYER_OFFHAND_EXPERTISE</td>
<td></td>
</tr>
<tr class="odd">
<td>1321</td>
<td>PLAYER_CRIT_PERCENTAGE</td>
<td></td>
</tr>
<tr class="even">
<td>1322</td>
<td>PLAYER_RANGED_CRIT_PERCENTAGE</td>
<td></td>
</tr>
<tr class="odd">
<td>1323</td>
<td>PLAYER_OFFHAND_CRIT_PERCENTAGE</td>
<td></td>
</tr>
<tr class="even">
<td>1324</td>
<td>PLAYER_SPELL_CRIT_PERCENTAGE1</td>
<td></td>
</tr>
<tr class="odd">
<td>1331</td>
<td>PLAYER_SHIELD_BLOCK</td>
<td></td>
</tr>
<tr class="even">
<td>1332</td>
<td>PLAYER_EXPLORED_ZONES_1</td>
<td></td>
</tr>
<tr class="odd">
<td>1396</td>
<td>PLAYER_REST_STATE_EXPERIENCE</td>
<td></td>
</tr>
<tr class="even">
<td>1397</td>
<td>PLAYER_FIELD_COINAGE</td>
<td>Character money (in copper)</td>
</tr>
<tr class="odd">
<td>1398</td>
<td>PLAYER_FIELD_MOD_DAMAGE_DONE_POS</td>
<td></td>
</tr>
<tr class="even">
<td>1405</td>
<td>PLAYER_FIELD_MOD_DAMAGE_DONE_NEG</td>
<td></td>
</tr>
<tr class="odd">
<td>1412</td>
<td>PLAYER_FIELD_MOD_DAMAGE_DONE_PCT</td>
<td></td>
</tr>
<tr class="even">
<td>1419</td>
<td>PLAYER_FIELD_MOD_HEALING_DONE_POS</td>
<td></td>
</tr>
<tr class="odd">
<td>1420</td>
<td>PLAYER_FIELD_MOD_TARGET_RESISTANCE</td>
<td></td>
</tr>
<tr class="even">
<td>1421</td>
<td>PLAYER_FIELD_MOD_TARGET_PHYSICAL_RESISTANCE</td>
<td></td>
</tr>
<tr class="odd">
<td>1422</td>
<td>PLAYER_FIELD_BYTES</td>
<td></td>
</tr>
<tr class="even">
<td>1423</td>
<td>PLAYER_AMMO_ID</td>
<td></td>
</tr>
<tr class="odd">
<td>1424</td>
<td>PLAYER_SELF_RES_SPELL</td>
<td></td>
</tr>
<tr class="even">
<td>1425</td>
<td>PLAYER_FIELD_PVP_MEDALS</td>
<td></td>
</tr>
<tr class="odd">
<td>1426</td>
<td>PLAYER_FIELD_BUYBACK_PRICE_1</td>
<td></td>
</tr>
<tr class="even">
<td>1438</td>
<td>PLAYER_FIELD_BUYBACK_TIMESTAMP_1</td>
<td></td>
</tr>
<tr class="odd">
<td>1450</td>
<td>PLAYER_FIELD_KILLS</td>
<td></td>
</tr>
<tr class="even">
<td>1451</td>
<td>PLAYER_FIELD_TODAY_CONTRIBUTION</td>
<td></td>
</tr>
<tr class="odd">
<td>1452</td>
<td>PLAYER_FIELD_YESTERDAY_CONTRIBUTION</td>
<td></td>
</tr>
<tr class="even">
<td>1453</td>
<td>PLAYER_FIELD_LIFETIME_HONORBALE_KILLS</td>
<td></td>
</tr>
<tr class="odd">
<td>1454</td>
<td>PLAYER_FIELD_BYTES2</td>
<td></td>
</tr>
<tr class="even">
<td>1455</td>
<td>PLAYER_FIELD_WATCHED_FACTION_INDEX</td>
<td></td>
</tr>
<tr class="odd">
<td>1456</td>
<td>PLAYER_FIELD_COMBAT_RATING_1</td>
<td></td>
</tr>
<tr class="even">
<td>1456</td>
<td>PLAYER_FIELD_ALL_WEAPONS_SKILL_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1457</td>
<td>PLAYER_FIELD_DEFENCE_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1458</td>
<td>PLAYER_FIELD_DODGE_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1459</td>
<td>PLAYER_FIELD_PARRY_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1460</td>
<td>PLAYER_FIELD_BLOCK_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1461</td>
<td>PLAYER_FIELD_MELEE_HIT_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1462</td>
<td>PLAYER_FIELD_RANGED_HIT_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1463</td>
<td>PLAYER_FIELD_SPELL_HIT_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1464</td>
<td>PLAYER_FIELD_MELEE_CRIT_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1465</td>
<td>PLAYER_FIELD_RANGED_CRIT_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1472</td>
<td>PLAYER_FIELD_SPELL_CRIT_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1473</td>
<td>PLAYER_FIELD_HIT_TAKEN_MELEE_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1474</td>
<td>PLAYER_FIELD_HIT_TAKEN_RANGED_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1475</td>
<td>PLAYER_FIELD_HIT_TAKEN_SPELL_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1476</td>
<td>PLAYER_FIELD_CRIT_TAKEN_MELEE_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1477</td>
<td>PLAYER_FIELD_CRIT_TAKEN_RANGED_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1478</td>
<td>PLAYER_FIELD_CRIT_TAKEN_SPELL_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1479</td>
<td>PLAYER_FIELD_MELEE_HASTE_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1480</td>
<td>PLAYER_FIELD_RANGED_HASTE_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1481</td>
<td>PLAYER_FIELD_SPELL_HASTE_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1488</td>
<td>PLAYER_FIELD_MELEE_WEAPON_SKILL_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1489</td>
<td>PLAYER_FIELD_OFFHAND_WEAPON_SKILL_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1490</td>
<td>PLAYER_FIELD_RANGED_WEAPON_SKILL_RATING</td>
<td></td>
</tr>
<tr class="odd">
<td>1491</td>
<td>PLAYER_FIELD_EXPERTISE_RATING</td>
<td></td>
</tr>
<tr class="even">
<td>1480</td>
<td>PLAYER_FIELD_ARENA_TEAM_INFO_1_1</td>
<td></td>
</tr>
<tr class="odd">
<td>1480</td>
<td>PLAYER_FIELD_ARENA_TEAM_ID_2v2</td>
<td></td>
</tr>
<tr class="even">
<td>1486</td>
<td>PLAYER_FIELD_ARENA_TEAM_ID_3v3</td>
<td></td>
</tr>
<tr class="odd">
<td>1498</td>
<td>PLAYER_FIELD_ARENA_TEAM_ID_5v5</td>
<td></td>
</tr>
<tr class="even">
<td>1498</td>
<td>PLAYER_FIELD_HONOR_CURRENCY</td>
<td>Character total honor points</td>
</tr>
<tr class="odd">
<td>1499</td>
<td>PLAYER_FIELD_ARENA_CURRENCY</td>
<td>Character total arena points</td>
</tr>
<tr class="even">
<td>1500</td>
<td>PLAYER_FIELD_MOD_MANA_REGEN</td>
<td></td>
</tr>
<tr class="odd">
<td>1501</td>
<td>PLAYER_FIELD_MOD_MANA_REGEN_INTERRUPT</td>
<td></td>
</tr>
<tr class="even">
<td>1502</td>
<td>PLAYER_FIELD_MAX_LEVEL</td>
<td></td>
</tr>
<tr class="odd">
<td>1503</td>
<td>PLAYER_FIELD_DAILY_QUESTS_1</td>
<td></td>
</tr>
</tbody>
</table>


