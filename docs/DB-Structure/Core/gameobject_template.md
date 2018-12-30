Back to [world database](mangosdb_struct) list of tables.

The \`gameobject\_template\` table
----------------------------------

Contains template off all world's objects

### Structure

| **Field**                                            | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry](gameobject_template#entry)                   | int(10) unsigned      | NO       | PRI     | 0           |           |
| [type](gameobject_template#type)                     | int(10) unsigned      | NO       |         | 0           |           |
| [displayId](gameobject_template#displayid)           | int(10) unsigned      | NO       |         | 0           |           |
| [name](gameobject_template#name)                     | char(100)             | NO       | MUL     | 0           |           |
| [IconName](gameobject_template#IconName)             | varchar               | NO       |         |             |           |
| [castBarCaption](gameobject_template#castbarcaption) | varchar(100)          | NO       |         |             |           |
| [faction](gameobject_template#faction)               | int(4) unsigned       | NO       |         | 0           |           |
| [flags](gameobject_template#flags)                   | int(4) unsigned       | NO       |         | 0           |           |
| [ExtraFlags](gameobject_template#ExtraFlags)         | int(11) unsigned      | NO       |         | 0           |           |
| [size](gameobject_template#size)                     | float                 | NO       |         | 1           |           |
| [data0](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data1](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data2](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data3](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data4](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data5](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data6](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data7](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data8](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data9](gameobject_template#data0-23)                | int(10) unsigned      | NO       |         | 0           |           |
| [data10](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data11](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data12](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data13](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data14](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data15](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data16](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data17](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data18](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data19](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data20](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data21](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data22](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [data23](gameobject_template#data0-23)               | int(10) unsigned      | NO       |         | 0           |           |
| [CustomData1](gameobject_template#CustomData1)       | int(11) unsigned      | NO       |         | 0           |           |
| [mingold](gameobject_template#mingold)               | mediumint(8) unsigned | NO       |         | 0           |           |
| [maxgold](gameobject_template#maxgold)               | mediumint(8) unsigned | NO       |         | 0           |           |
| [ScriptName](gameobject_template#scriptname)         | char(100)             | NO       |         |             |           |

### Description of the fields

#### entry

Id of the gameobject template

#### type

GAMEOBJECT\_TYPE\_DOOR = 0
GAMEOBJECT\_TYPE\_BUTTON = 1
GAMEOBJECT\_TYPE\_QUESTGIVER = 2
GAMEOBJECT\_TYPE\_CHEST = 3
GAMEOBJECT\_TYPE\_BINDER = 4
GAMEOBJECT\_TYPE\_GENERIC = 5
GAMEOBJECT\_TYPE\_TRAP = 6
GAMEOBJECT\_TYPE\_CHAIR = 7
GAMEOBJECT\_TYPE\_SPELL\_FOCUS = 8
GAMEOBJECT\_TYPE\_TEXT = 9
GAMEOBJECT\_TYPE\_GOOBER = 10
GAMEOBJECT\_TYPE\_TRANSPORT = 11
GAMEOBJECT\_TYPE\_AREADAMAGE = 12
GAMEOBJECT\_TYPE\_CAMERA = 13
GAMEOBJECT\_TYPE\_MAP\_OBJECT = 14
GAMEOBJECT\_TYPE\_MO\_TRANSPORT = 15
GAMEOBJECT\_TYPE\_DUEL\_ARBITER = 16
GAMEOBJECT\_TYPE\_FISHINGNODE = 17
GAMEOBJECT\_TYPE\_RITUAL = 18
GAMEOBJECT\_TYPE\_MAILBOX = 19
GAMEOBJECT\_TYPE\_AUCTIONHOUSE = 20
GAMEOBJECT\_TYPE\_GUARDPOST = 21
GAMEOBJECT\_TYPE\_SPELLCASTER = 22
GAMEOBJECT\_TYPE\_MEETINGSTONE = 23
GAMEOBJECT\_TYPE\_FLAGSTAND = 24
GAMEOBJECT\_TYPE\_FISHINGHOLE = 25
GAMEOBJECT\_TYPE\_FLAGDROP = 26
GAMEOBJECT\_TYPE\_MINI\_GAME = 27
GAMEOBJECT\_TYPE\_LOTTERY\_KIOSK = 28
GAMEOBJECT\_TYPE\_CAPTURE\_POINT = 29
GAMEOBJECT\_TYPE\_AURA\_GENERATOR = 30
GAMEOBJECT\_TYPE\_DUNGEON\_DIFFICULTY = 31
GAMEOBJECT\_TYPE\_BARBER\_CHAIR = 32
GAMEOBJECT\_TYPE\_DESTRUCTIBLE\_BUILDING = 33
GAMEOBJECT\_TYPE\_GUILD\_BANK = 34

#### displayId

Graphic model id sent to the client from GameObjectDisplayInfo.dbc.

#### name

Object's name

#### IconName

#### castBarCaption

Shows unique text in the object's casting bar when the object is used.

#### faction

Object's faction, if any. See [FactionTemplate.dbc](FactionTemplate.dbc)

#### flags

-   1 = in use (can't interact with the object)
-   2 = Makes chests/doors locked (requiring a key, spell, event to open)
-   4 = Untargetable
-   8 = Transport (Object can transport (elevator, boat, car))
-   16 = Player cant interact with the object.
-   32 = No despawn (never despawn, typically for doors, they just change state)
-   64 = Triggered (typically, summoned objects. Triggered by spell or other events)

NOTE: All chests that contain only quest loots need to have flag 4 set as the core will only allow players who have the quest in their questlog to loot them.

#### ExtraFlags

-   1 = GAMEOBJECT\_EXTRA\_FLAG\_CUSTOM\_ANIM\_ON\_USE (// GO that plays custom animation on usage)

#### size

Object's size must be set because graphic models can be resample.

#### data0-23

The content of the data fields depends on the [gameobject type](#type)

-   **GAMEOBJECT\_TYPE\_DOOR = 0**
    -   data0: startOpen (Boolean flag)
    -   data1: open (LockId from [Lock.dbc](Lock.dbc))
    -   data2: autoClose (65536 \* seconds(sniff value)) (e.g. open after 5 min = 300 \* 65536 = 19660800)
    -   data3: noDamageImmune (Boolean flag)
    -   data4: openTextID (Unknown Text ID)
    -   data5: closeTextID (Unknown Text ID)

<!-- -->
-   **GAMEOBJECT\_TYPE\_BUTTON = 1**
    -   data0: startOpen (State)
    -   data1: open (LockId from [Lock.dbc](Lock.dbc))
    -   data2: autoClose (65536 \* seconds(sniff value))
    -   data3: linkedTrap ([gameobject\_template.entry](gameobject_template#entry) (Spawned GO type 6))
    -   data4: noDamageImmune (Boolean flag)
    -   data5: large? (Boolean flag)
    -   data6: openTextID (Unknown Text ID)
    -   data7: closeTextID (Unknown Text ID)
    -   data8: losOK (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_QUESTGIVER = 2**
    -   data0: open (LockId from Lock.dbc)
    -   data1: questList (unknown ID)
    -   data2: pageMaterial ([PageTextMaterial.dbc](PageTextMaterial.dbc))
    -   data3: gossipID (unknown ID)
    -   data4: customAnim (unknown value from 1 to 4)
    -   data5: noDamageImmune (Boolean flag)
    -   data6: openTextID (Unknown Text ID)
    -   data7: losOK (Boolean flag)
    -   data8: allowMounted (Boolean flag)
    -   data9: large? (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_CHEST = 3**
    -   data0: open (LockId from Lock.dbc)
    -   data1: chestLoot ([gameobject\_loot\_template.entry](Loot_template#entry)) **This field is obtained from WDB data and is not to be changed**
    -   data2: chestRestockTime (time in seconds)
    -   data3: consumable (State: Boolean flag)
    -   data4: minRestock (Min successful loot attempts for Mining, Herbalism etc)
    -   data5: maxRestock (Max successful loot attempts for Mining, Herbalism etc)
    -   data6: lootedEvent ([dbscripts\_on\_event](DBScripts))
    -   data7: linkedTrap ([gameobject\_template.entry](gameobject_template#entry) (Spawned GO type 6))
    -   data8: questID ([quest\_template.entry](quest_template#entry) of completed quest)
    -   data9: level (minimal level required to open this gameobject)
    -   data10: losOK (Boolean flag)
    -   data11: leaveLoot (Boolean flag)
    -   data12: notInCombat (Boolean flag)
    -   data13: log loot (Boolean flag)
    -   data14: openTextID (Unknown ID)
    -   data15: use group loot rules (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_BINDER = 4**

Object type not used

-   **GAMEOBJECT\_TYPE\_GENERIC = 5**
    -   data0: floatingTooltip (Boolean flag)
    -   data1: highlight (Boolean flag)
    -   data2: serverOnly? (Always 0)
    -   data3: large? (Boolean flag)
    -   data4: floatOnWater (Boolean flag)
    -   data5: questID (Required active [quest\_template.entry](quest_template#entry) to work)

<!-- -->
-   **GAMEOBJECT\_TYPE\_TRAP = 6**
    -   data0: open (LockId from Lock.dbc)
    -   data1: level (npc equivalent level for casted spell)
    -   data2: diameter (so radius\*2)
    -   data3: spell (Spell Id from spell.dbc)
    -   data4: charges (0 or 1)
    -   data5: cooldown (time in seconds)
    -   data6: autoClose (unknown)
    -   data7: startDelay? (time in seconds)
    -   data8: serverOnly? (always 0)
    -   data9: stealthed (Boolean flag)
    -   data10: large? (Boolean flag)
    -   data11: stealthAffected (Boolean flag)
    -   data12: openTextID (Unknown ID)

<!-- -->
-   **GAMEOBJECT\_TYPE\_CHAIR = 7**
    -   data0: chairslots (number of players that can sit down on it)
    -   data1: chairorientation? (number of usable side?)

<!-- -->
-   **GAMEOBJECT\_TYPE\_SPELL\_FOCUS = 8**
    -   data0: spellFocusType (from SpellFocusObject.dbc)
    -   data1: diameter (so radius\*2)
    -   data2: linkedTrap ([gameobject\_template.entry](gameobject_template#entry) (Spawned GO type 6))
    -   data3: serverOnly? (1: Visible to GM only, 0: Visible to all players)
    -   data4: questID (Required active quest\_template.entry to work)
    -   data5: large? (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_TEXT = 9**
    -   data0: pageID ([page\_text.entry](page_text#entry))
    -   data1: language (from [Languages.dbc](Languages.dbc))
    -   data2: pageMaterial ([PageTextMaterial.dbc](PageTextMaterial.dbc))

<!-- -->
-   **GAMEOBJECT\_TYPE\_GOOBER = 10**
    -   data0: open (LockId from Lock.dbc)
    -   data1: questID (Required active [quest\_template.entry](quest_template#entry) to work)
    -   data2: eventID (The id of the [event](event_scripts) that the gameobject will activate)
    -   data3: autoClose (most be the same like doors (65536 \* seconds(sniff value))
    -   data4: customAnim (unknown)
    -   data5: consumable (Boolean flag controling if gameobject will despawn or not)
    -   data6: cooldown (time in seconds)
    -   data7: pageID ([page\_text.entry](page_text#entry))
    -   data8: language (from [Languages.dbc](Languages.dbc))
    -   data9: pageMaterial ([PageTextMaterial.dbc](PageTextMaterial.dbc))
    -   data10: spell (Spell Id from spell.dbc)
    -   data11: noDamageImmune (Boolean flag)
    -   data12: linkedTrap ([gameobject\_template.entry](gameobject_template#entry) (Spawned GO type 6))
    -   data13: large? (Boolean flag)
    -   data14: openTextID (Unknown ID)
    -   data15: closeTextID (Unknown ID)
    -   data16: losOK (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_TRANSPORT = 11**

No data data used, all are always 0

-   **GAMEOBJECT\_TYPE\_AREADAMAGE = 12**

Object type not used

-   **GAMEOBJECT\_TYPE\_CAMERA = 13**
    -   data0: open (LockId from Lock.dbc)
    -   data1: camera (Cinematic entry from CinematicCamera.dbc)

<!-- -->
-   **GAMEOBJECT\_TYPE\_MAPOBJECT = 14**

No data data used, all are always 0

-   **GAMEOBJECT\_TYPE\_MOTRANSPORT = 15**
    -   data0: taxiPathID (Id from TaxiPath.dbc)
    -   data1: moveSpeed
    -   data2: accelRate

<!-- -->
-   **GAMEOBJECT\_TYPE\_DUELFLAG = 16**

Only one Gameobject with this type (21680) and no data data

-   **GAMEOBJECT\_TYPE\_FISHINGNODE = 17**

Only one Gameobject with this type (35591) and no data data

-   **GAMEOBJECT\_TYPE\_RITUAL = 18**
    -   data0: casters?
    -   data1: spell (Spell Id from spell.dbc)
    -   data2: animSpell (Spell Id from spell.dbc)
    -   data3: ritualPersistent (Boolean flag)
    -   data4: casterTargetSpell (Spell Id from spell.dbc)
    -   data5: casterTargetSpellTargets (Boolean flag)
    -   data6: castersGrouped (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_MAILBOX = 19**

No data data used, all are always 0

-   **GAMEOBJECT\_TYPE\_AUCTIONHOUSE = 20**
    -   data0: actionHouseID (From AuctionHouse.dbc ?)

<!-- -->
-   **GAMEOBJECT\_TYPE\_GUARDPOST = 21**

Object type not used

-   **GAMEOBJECT\_TYPE\_SPELLCASTER = 22**
    -   data0: spell (Spell Id from spell.dbc)
    -   data1: charges
    -   data2: partyOnly (Boolean flag, need to be in group to use it)

<!-- -->
-   **GAMEOBJECT\_TYPE\_MEETINGSTONE = 23**
    -   data0: minLevel
    -   data1: maxLevel
    -   data2: areaID (From [AreaTable.dbc](AreaTable.dbc))

<!-- -->
-   **GAMEOBJECT\_TYPE\_FLAGSTAND = 24**
    -   data0: open (LockId from Lock.dbc)
    -   data1: pickupSpell (Spell Id from spell.dbc)
    -   data2: radius (distance)
    -   data3: returnAura (Spell Id from spell.dbc)
    -   data4: returnSpell (Spell Id from spell.dbc)
    -   data5: noDamageImmune (Boolean flag)
    -   data6: openTextID
    -   data7: losOK (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_FISHINGHOLE = 25**
    -   data0: radius (distance)
    -   data1: chestLoot ([gameobject\_loot\_template.entry](Loot_template#entry))
    -   data2: minRestock
    -   data3: maxRestock

<!-- -->
-   **GAMEOBJECT\_TYPE\_FLAGDROP = 26**
    -   data0: open (LockId from Lock.dbc)
    -   data1: eventID (Unknown Event ID)
    -   data2: pickupSpell (Spell Id from spell.dbc)
    -   data3: noDamageImmune (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_MINIGAME = 27**

Object type not used

Reused in core for CUSTOM\_TELEPORT

-   \*\*\*\* data0: [areatrigger\_teleport.id](areatrigger_teleport#id)

<!-- -->
-   **GAMEOBJECT\_TYPE\_LOTTERYKIOSK = 28**

Object type not used

-   **GAMEOBJECT\_TYPE\_CAPTUREPOINT = 29**
    -   data0: radius (Distance)
    -   data1: spell (Unknown ID, not a spell id in dbc file, maybe server only side spell)
    -   data2: worldState1
    -   data3: worldstate2
    -   data4: winEventID1 (Unknown Event ID)
    -   data5: winEventID2 (Unknown Event ID)
    -   data6: contestedEventID1 (Unknown Event ID)
    -   data7: contestedEventID2 (Unknown Event ID)
    -   data8: progressEventID1 (Unknown Event ID)
    -   data9: progressEventID2 (Unknown Event ID)
    -   data10: neutralEventID1 (Unknown Event ID)
    -   data11: neutralEventID2 (Unknown Event ID)
    -   data12: neutralPercent
    -   data13: worldstate3
    -   data14: minSuperiority
    -   data15: maxSuperiority
    -   data16: minTime (in seconds)
    -   data17: maxTime (in seconds)
    -   data18: large? (Boolean flag)

<!-- -->
-   **GAMEOBJECT\_TYPE\_AURA\_GENERATOR = 30**
    -   data0: startOpen (Boolean flag)
    -   data1: radius (Distance)
    -   data2: auraID1 (Spell Id from spell.dbc)
    -   data3: conditionID1 (Unknown ID)

<!-- -->
-   **GAMEOBJECT\_TYPE\_DUNGEONDIFFICULTY = 31**
    -   data0: mapID (From [Map.dbc](Map.dbc))
    -   data1: difficulty (0 or 1)

<!-- -->
-   **GAMEOBJECT\_TYPE\_BARBER\_CHAIR = 32**

Used for barber chairs.

-   **GAMEOBJECT\_TYPE\_DESTRUCTIBLE\_BUILDING = 33**

Object type not used

-   **GAMEOBJECT\_TYPE\_GUILD\_BANK = 34**

No data data used, all are always 0

#### CustomData1

#### mingold

Minimum possible gold that the GO holds when looted, in copper.

#### maxgold

Maximum possible gold that the GO holds when looted, in copper.

#### ScriptName

Name of the script this object uses if needed
