Back to [world database](mangosdb_struct) list of tables.

**This table is for [cmangos-classic](https://github.com/cmangos/mangos-classic) (1.12.x)**

**See also [creature\_template\_tbc](creature_template_tbc) (2.4.3)**
**See also [creature\_template](creature_template) (3.3.5a)**

The \`creature\_template\_classic\` table
-----------------------------------------

This table contains the description of creatures. Each spawned [creature](creature) is an instance of a creature\_template present in this table.

This means every [creature](creature) MUST be defined in this table.

### Structure

| **Field**                                                              | **Null** | **Type**              | **Key** | **Default** | **Extra** |
|------------------------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [Entry](creature_template_classic#entry)                               | NO       | mediumint(8) unsigned | PRI     | 0           |           |
| [Name](creature_template_classic#name)                                 | NO       | char(100)             |         | 0           |           |
| [SubName](creature_template_classic#subname)                           | YES      | char(100)             |         | Null        |           |
| [MinLevel](creature_template_classic#minlevel)                         | YES      | tinyint(3) unsigned   |         | 1           |           |
| [MaxLevel](creature_template_classic#maxlevel)                         | YES      | tinyint(3) unsigned   |         | 1           |           |
| [ModelId1](creature_template_classic#modelid1)                         | NO       | mediumint(8) unsigned |         | 0           |           |
| [ModelId2](creature_template_classic#modelid2)                         | NO       | mediumint(8) unsigned |         | 0           |           |
| [ModelId3](creature_template_classic#modelid3)                         | NO       | mediumint(8) unsigned |         | 0           |           |
| [ModelId4](creature_template_classic#modelid4)                         | NO       | mediumint(8) unsigned |         | 0           |           |
| [FactionAlliance](creature_template_classic#factionalliance)           | NO       | smallint(5) unsigned  |         | 0           |           |
| [FactionHorde](creature_template_classic#factionhorde)                 | NO       | smallint(5) unsigned  |         | 0           |           |
| [Scale](creature_template_classic#scale)                               | NO       | float                 |         | 0           |           |
| [Family](creature_template_classic#family)                             | YES      | tinyint(4)            |         | 0           |           |
| [CreatureType](creature_template_classic#creaturetype)                 | NO       | tinyint(3) unsigned   |         | 0           |           |
| [InhabitType](creature_template_classic#inhabittype)                   | NO       | tinyint(3) unsigned   |         | 3           |           |
| [RegenerateStats](creature_template_classic#regeneratestats)           | NO       | tinyint(3) unsigned   |         | 1           |           |
| [RacialLeader](creature_template_classic#racialleader)                 | NO       | tinyint(3) unsigned   |         | 0           |           |
| [NpcFlags](creature_template_classic#npcflags)                         | NO       | int(10) unsigned      |         | 0           |           |
| [UnitFlags](creature_template_classic#unitflags)                       | NO       | int(10) unsigned      |         | 0           |           |
| [DynamicFlags](creature_template_classic#dynamicflags)                 | NO       | int(10) unsigned      |         | 0           |           |
| [ExtraFlags](creature_template_classic#extraflags)                     | NO       | int(10) unsigned      |         | 0           |           |
| [CreatureTypeFlags](creature_template_classic#creaturetypeflags)       | YES      | int(10) unsigned      |         | 0           |           |
| [SpeedWalk](creature_template_classic#speedwalk)                       | YES      | float                 |         | 1           |           |
| [SpeedRun](creature_template_classic#speedrun)                         | YES      | float                 |         | 1.14286     |           |
| [UnitClass](creature_template_classic#unitclass)                       | NO       | int unsigned          |         | 0           |           |
| [Rank](creature_template_classic#rank)                                 | YES      | tinyint(3) unsigned   |         | 0           |           |
| [HealthMultiplier](creature_template_classic#healthmultiplier)         | NO       | float                 |         | 1.0         |           |
| [PowerMultiplier](creature_template_classic#manamultiplier)            | NO       | float                 |         | 1.0         |           |
| [DamageMultiplier](creature_template_classic#damagemultiplier)         | NO       | float                 |         | 1           |           |
| [DamageVariance](creature_template_classic#damagevariance)             | NO       | float                 |         | 1           |           |
| [ArmorMultiplier](creature_template_classic#armormultiplier)           | NO       | float                 |         | 1           |           |
| [ExperienceMultiplier](creature_template_classic#experiencemultiplier) | NO       | float                 |         | 1           |           |
| [MinLevelHealth](creature_template_classic#minlevelhealth)             | YES      | int(10) unsigned      |         | 0           |           |
| [MaxLevelHealth](creature_template_classic#maxlevelhealth)             | YES      | int(10) unsigned      |         | 0           |           |
| [MinLevelMana](creature_template_classic#minlevelmana)                 | YES      | int(10) unsigned      |         | 0           |           |
| [MaxLevelMana](creature_template_classic#maxlevelmana)                 | YES      | int(10) unsigned      |         | 0           |           |
| [MinMeleeDmg](creature_template_classic#minmeleedmg)                   | YES      | float                 |         | 0           |           |
| [MaxMeleeDmg](creature_template_classic#maxmeleedmg)                   | YES      | float                 |         | 0           |           |
| [MinRangedDmg](creature_template_classic#minrangeddmg)                 | NO       | float                 |         | 0           |           |
| [MaxRangedDmg](creature_template_classic#maxrangeddmg)                 | NO       | float                 |         | 0           |           |
| [Armor](creature_template_classic#armor)                               | NO       | mediumint(8) unsigned |         | 0           |           |
| [MeleeAttackPower](creature_template_classic#meleeattackpower)         | NO       | int(10) unsigned      |         | 0           |           |
| [RangedAttackPower](creature_template_classic#rangedattackpower)       | NO       | smallint(5) unsigned  |         | 0           |           |
| [MeleeBaseAttackTime](creature_template_classic#meleebaseattacktime)   | YES      | int(10) unsigned      |         | 0           |           |
| [RangedBaseAttackTime](creature_template_classic#rangedbaseattacktime) | YES      | int(10) unsigned      |         | 0           |           |
| [DamageSchool](creature_template_classic#damageschool)                 | NO       | tinyint(4)            |         | 0           |           |
| [MinLootGold](creature_template_classic#minlootgold)                   | NO       | mediumint(8) unsigned |         | 0           |           |
| [MaxLootGold](creature_template_classic#maxlootgold)                   | NO       | mediumint(8) unsigned |         | 0           |           |
| [LootId](creature_template_classic#lootid)                             | NO       | mediumint(8) unsigned |         | 0           |           |
| [PickpocketLootId](creature_template_classic#pickpocketlootid)         | NO       | mediumint(8) unsigned |         | 0           |           |
| [SkinningLootId](creature_template_classic#skinninglootid)             | NO       | mediumint(8) unsigned |         | 0           |           |
| [KillCredit1](creature_template_classic#killcredit1)                   | NO       | int(11) unsigned      |         | 0           |           |
| [KillCredit2](creature_template_classic#killcredit2)                   | NO       | int(11) unsigned      |         | 0           |           |
| [MechanicImmuneMask](creature_template_classic#mechanicimmunemask)     | NO       | int(10) unsigned      |         | 0           |           |
| [SchoolImmuneMask](creature_template_classic#schoolimmunemask)         | NO       | int(10) unsigned      |         | 0           |           |
| [ResistanceHoly](creature_template_classic#resistanceholy)             | NO       | int(10) unsigned      |         | 0           |           |
| [ResistanceFire](creature_template_classic#resistancefire)             | NO       | smallint(5)           |         | 0           |           |
| [ResistanceNature](creature_template_classic#resistancenature)         | NO       | smallint(5)           |         | 0           |           |
| [ResistanceFrost](creature_template_classic#resistancefrost)           | NO       | smallint(5)           |         | 0           |           |
| [ResistanceShadow](creature_template_classic#resistanceshadow)         | NO       | smallint(5)           |         | 0           |           |
| [ResistanceArcane](creature_template_classic#resistancearcane)         | NO       | smallint(5)           |         | 0           |           |
| [PetSpellDataId](creature_template_classic#petspelldataid)             | NO       | mediumint(8) unsigned |         | 0           |           |
| [MovementType](creature_template_classic#movementtype)                 | NO       | tinyint(3) unsigned   |         | 0           |           |
| [TrainerType](creature_template_classic#trainertype)                   | YES      | tinyint(4)            |         | 0           |           |
| [TrainerSpell](creature_template_classic#trainerspell)                 | YES      | mediumint(8) unsigned |         | 0           |           |
| [TrainerClass](creature_template_classic#trainerclass)                 | YES      | tinyint(3) unsigned   |         | 0           |           |
| [TrainerRace](creature_template_classic#trainerrace)                   | YES      | tinyint(3) unsigned   |         | 0           |           |
| [TrainerTemplateId](creature_template_classic#trainertemplateid)       | NO       | mediumint(8) unsigned |         | 0           |           |
| [VendorTemplateId](creature_template_classic#vendortemplateid)         | NO       | mediumint(8) unsigned |         | 0           |           |
| [GossipMenuId](creature_template_classic#gossipmenuid)                 | YES      | mediumint(8) unsigned |         | 0           |           |
| [EquipmentTemplateId](creature_template_classic#equipmenttemplateid)   | NO       | mediumint(8) unsigned |         | 0           |           |
| [Civilian](creature_template_classic#civilian)                         | YES      | tinyint(3) unsigned   |         | 0           |           |
| [AIName](creature_template_classic#ainame)                             | NO       | char(64)              |         |             |           |
| [ScriptName](creature_template_classic#scriptname)                     | NO       | char(64)              |         |             |           |

### Description of the fields

#### Entry

This is the Primary NPC Entry Number and is Also the Dungeon Normal Mode / Raid 10-Man Normal Mode Entry.

| DUNGEON\_DIFFICULTY\_NORMAL     |
|---------------------------------|
| RAID\_DIFFICULTY\_10MAN\_NORMAL |

#### Name

Base Name of the Creature.

#### SubName

The SubName of the Creature That Appears in `<>` Below the Creature's Name.

#### MinLevel

The Minimum Level of the Creature if the Creature Has a Level Range. For Creature That Are Single Level MinLevel=MaxLevel.

#### MaxLevel

The Maximum Level of the Creature if the Creature Has a Level Range. For Creature That Are Single Level MinLevel=MaxLevel.

#### ModelId1

Primary Graphical Model That The Client Applies On This Creature. This is a [Creature\_Model\_Info.Entry](Creature_Model_Info#Entry)

#### ModelId2

Optional Extra Graphical Model That The Client Applies On This Creature. This is a [Creature\_Model\_Info.Entry](Creature_Model_Info#Entry)

#### ModelId3

Optional Extra Graphical Model That The Client Applies On This Creature. This is a [Creature\_Model\_Info.Entry](Creature_Model_Info#Entry)

#### ModelId4

Optional Extra Graphical Model That The Client Applies On This Creature. This is a [Creature\_Model\_Info.Entry](Creature_Model_Info#Entry)

#### FactionAlliance

The Faction If The Creature Is On The Alliance Side. See [FactionTemplate.dbc.](FactionTemplate.dbc). Just Because More Than One Faction Has The Same Name, The Inter-Faction Relationships Can Be Different.

Note: This Field Also Controls The Creature Family Assistance Mechanic. Only Creatures With The Same Faction Will Assist Each Other.

#### FactionHorde

The Faction If The Creature Is On The Horde Side. See [FactionTemplate.dbc.](FactionTemplate.dbc). Just Because More Than One Faction Has The Same Name, The Inter-Faction Relationships Can Be Different.

Note: This Field Also Controls The Creature Family Assistance Mechanic. Only Creatures With The Same Faction Will Assist Each Other.

#### Scale

If This Is A Non-Zero Value, This Field Defines a Manual Over-Ride For The Size Of The Model That The Creature Appears In The Game. If Zero, The Creature Will Use The Default Model Size Taken From The DBC.

#### Family

This Defines The Family That This Creature Belongs To. This Is Only Used If [CreatureType](#CreatureType) Is 1 (Beast).

| ID  | ID  | Family       | Family         | ID  | Family       |
|-----|--------------|-----|----------------|-----|--------------|
| 1   | 15  | Wolf         | Doomguard      | 29  | Nether Ray   |
| 2   | 16  | Cat          | Scorpid        | 30  | Serpent      |
| 3   | 17  | Spider       | Turtle         | 31  | Moth         |
| 4   | 18  | Bear         | Imp            | 32  | Chimaera     |
| 5   | 19  | Boar         | Bat            | 33  | Devilsaur    |
| 6   | 20  | Crocolisk    | Hyena          | 34  | Ghoul        |
| 7   | 21  | Carrion Bird | Bird of Prey   | 35  | Silithid     |
| 8   | 22  | Crab         | Wind Serpent   | 36  | Worm         |
| 9   | 23  | Gorilla      | Remote Control | 37  | Rhino        |
| 10  | 24  | Raptor       | Felguard       | 38  | Wasp         |
| 11  | 25  | Tallstrider  | Dragonhawk     | 39  | Core Hound   |
| 12  | 26  | Felhunter    | Ravager        | 40  | Spirit Beast |
| 13  | 27  | Voidwalker   | Warp Stalker   |     |
| 14  | 28  | Succubus     | Sporebat       |     |

#### CreatureType

This Field Defines The Type Of Creature This NPC Is.

| ID  | Type           |
|-----|----------------|
| 0   | None           |
| 1   | Beast          |
| 2   | Dragonkin      |
| 3   | Demon          |
| 4   | Elemental      |
| 5   | Giant          |
| 6   | Undead         |
| 7   | Humanoid       |
| 8   | Critter        |
| 9   | Mechanical     |
| 10  | Not specified  |
| 11  | Totem          |
| 12  | Non-combat Pet |
| 13  | Gas Cloud      |

#### InhabitType

This Field Controls Where The Creature Can Move Into, Chase And Attack.
The NPC Is Limited To ONLY Movement On This:

| ID  | Type                                                     |
|-----|----------------------------------------------------------|
| 1   | Ground Movement Only                                     |
| 2   | Water Movement Only                                      |
| 3   | Both Ground And Water Movement                           |
| 4   | Always Flying                                            |
| 5   | Over Ground Always Flying                                |
| 6   | Over Water Always Flying                                 |
| 7   | Always Flying Over Anything (But can also walk and swim) |

#### RegenerateStats

This Field Controls If The Creature Should Regenerate It's Health/Stats When Out of Combat (Data Flag)

| Value | Description                                                    |
|-------|----------------------------------------------------------------|
| 0     | NPC Does NOT Regenerate Stats When Out Of Combat               |
| 1     | NPC DOES Regenerate Health When Out Of Combat                  |
| 2     | NPC DOES Regenerate Power (Mana) When Out Of Combat            |
| 3     | NPC DOES Regenerate Health AND Power (Mana) When Out Of Combat |

#### RacialLeader

This Field Is a Boolean Flag Indicating That The Creature Is a Racial Leader. Killing Racial Leaders Grants 100 Honor Points.

| Value | Description                |
|-------|----------------------------|
| 0     | NPC Is NOT a Racial Leader |
| 1     | NPC IS a Racial Leader     |

#### NpcFlags

This Field Is a Bitmask That Represents What NPC Flags The Creature Has Assigned To It. Each Bit Controls a Different Flag and to Combine Flags, You Can Add Each Flag That You Require, In Effect Activating The Respective Bits.

***Please note that the values below are valid for classic only! For tbc and wotlk, please check their respective wiki pages ([creature\_template\_tbc](creature_template_tbc) (for 2.4.3) [creature\_template](creature_template) (for 3.3.5a) )***

| Bit | Value     | Flag            | Comment                                                                          |
| --- | --------- | --------------- | -------------------------------------------------------------------------------- |
| 0   | 1         | Gossip          | If creature has more gossip options, add this flag to bring up a menu.           |
| 1   | 2         | Quest Giver     | Any creature giving or taking quests needs to have this flag.                    |
| 2   | 4         | Vendor          | Any creature selling items needs to have this flag.                              |
| 3   | 8         | Flight Master   | Any creature serving as fly master has this.                                     |
| 4   | 16        | Trainer         | Allows the creature to have a trainer list to teach spells                       |
| 5   | 32        | Spirit Healer   | Makes the creature invisible to alive characters and has the resurrect function. |
| 6   | 64        | Spirit Guide    |                                                                                  |
| 7   | 128       | Innkeeper       | Creatures with this flag can set hearthstone locations.                          |
| 8   | 256       | Banker          | Creatures with this flag can show the bank                                       |
| 9   | 512       | Petitioner      |                                                                                  |
| 10  | 1024      | Tabard Designer | Allows the designing of guild tabards.                                           |
| 11  | 2048      | Battlemaster    | Creatures with this flag port players to battlegrounds.                          |
| 12  | 4096      | Auctioneer      | Allows creature to display auction list.                                         |
| 13  | 8192      | Stable Master   | Has the option to stable pets for hunters.                                       |
| 14  | 16384     | Repairer        | Creatures with this flag can repair items.                                       |
|     | 536870912 | Outdoor PvP     | custom flag for outdoor pvp creatures                                            |

EXAMPLE:
So If You Want An NPC That Is a Quest Giver, a Vendor And Can Also Repair You Just Add The Specific Flags Together:

2 + 4 + 16384 = 16390.
NpcFlags = 16390

#### UnitFlags

This Field Allows The Manual Application Of Unit Flags To NPC. This Is a Bitmask Field And To Apply More Then One Flag, Just Add The Different Flags Together.

Some Known Possible Flags Are:

| Bit | Flag       | Name                          | Comments                                                                                                                                                                                                                                     |
| --- | ---------- | ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0   | 1          | UNIT_FLAG_UNK_0               | Movement checks disabled, likely paired with loss of client control packet.                                                                                                                                                                  |
| 1   | 2          | UNIT_FLAG_NON_ATTACKABLE      | not attackable                                                                                                                                                                                                                               |
| 2   | 4          | UNIT_FLAG_CLIENT_CONTROL_LOST | Generic unspecified loss of control initiated by server script, movement checks disabled, paired with loss of client control packet.                                                                                                         |
| 3   | 8          | UNIT_FLAG_PLAYER_CONTROLLED   | players, pets, totems, guardians, companions, charms, any units associated with players                                                                                                                                                      |
| 4   | 16         | UNIT_FLAG_PET_RENAME          |                                                                                                                                                                                                                                              |
| 5   | 32         | UNIT_FLAG_PET_ABANDON         |                                                                                                                                                                                                                                              |
| 6   | 64         | UNIT_FLAG_UNK_6               | Related to Movement? often paired with UNIT_FLAG_SWIMMING                                                                                                                                                                                    |
| 7   | 128        |                               |                                                                                                                                                                                                                                              |
| 8   | 256        | UNIT_FLAG_IMMUNE_TO_PLAYER    | Target is immune to players                                                                                                                                                                                                                  |
| 9   | 512        | UNIT_FLAG_IMMUNE_TO_NPC       | makes you unable to attack everything. Almost identical to our "civilian"-term. Will ignore it's surroundings and not engage in combat unless "called upon" or engaged by another unit.                                                      |
| 10  | 1024       |                               |                                                                                                                                                                                                                                              |
| 11  | 2048       |                               |                                                                                                                                                                                                                                              |
| 12  | 4096       | UNIT_FLAG_PVP                 | Allows item spells to be casted upon. changed in 3.0.3                                                                                                                                                                                       |
| 13  | 8192       | UNIT_FLAG_SILENCED            | silenced, 2.1.1                                                                                                                                                                                                                              |
| 14  | 16384      | UNIT_FLAG_PERSUADED           | persuaded, 2.0.8                                                                                                                                                                                                                             |
| 15  | 32768      | UNIT_FLAG_SWIMMING            | controls water swimming animation - TODO: confirm whether dynamic or static                                                                                                                                                                  |
| 16  | 65536      | UNIT_FLAG_UNK_16              | removes attackable icon, if on yourself, cannot assist self but can cast TARGET_SELF spells - added by SPELL_AURA_MOD_UNATTACKABLE                                                                                                           |
| 17  | 131072     | UNIT_FLAG_PACIFIED            | pacified, 3.0.3                                                                                                                                                                                                                              |
| 18  | 262144     | UNIT_FLAG_STUNNED             | stunned, 2.1.1 Unit is a subject to stun, turn and strafe movement disabled                                                                                                                                                                  |
| 19  | 524288     | UNIT_FLAG_IN_COMBAT           |                                                                                                                                                                                                                                              |
| 20  | 1048576    | UNIT_FLAG_TAXI_FLIGHT         | Unit is on taxi, paired with a duplicate loss of client control packet (likely a legacy serverside hack). Disables any spellcasts not allowed in taxi flight client-side.                                                                    |
| 21  | 2097152    |                               |                                                                                                                                                                                                                                              |
| 22  | 4194304    | UNIT_FLAG_CONFUSED            | Unit is a subject to confused movement, movement checks disabled, paired with loss of client control packet.                                                                                                                                 |
| 23  | 8388608    | UNIT_FLAG_FLEEING             | Unit is a subject to fleeing movement, movement checks disabled, paired with loss of client control packet.                                                                                                                                  |
| 24  | 16777216   | UNIT_FLAG_POSSESSED           | Unit is under remote control by another unit, movement checks disabled, paired with loss of client control packet. New master is allowed to use melee attack and can't select this unit via mouse in the world (as if it was own character). |
| 25  | 33554432   | UNIT_FLAG_NOT_SELECTABLE      | Can't be selected by mouse                                                                                                                                                                                                                   |
| 26  | 67108864   | UNIT_FLAG_SKINNABLE           |                                                                                                                                                                                                                                              |
| 27  | 134217728  | UNIT_FLAG_AURAS_VISIBLE       | magic detect                                                                                                                                                                                                                                 |
| 28  | 268435456  | UNIT_FLAG_UNK_28              |                                                                                                                                                                                                                                              |
| 29  | 536870912  | UNIT_FLAG_UNK_29              |                                                                                                                                                                                                                                              |
| 30  | 1073741824 | UNIT_FLAG_SHEATHE             |                                                                                                                                                                                                                                              |
| 31  | 2147483648 | UNIT_FLAG_UNK_31              | set skinnable icon and also changes color of portrait)(no affect in 2.4.3)                                                                                                                                                                   |

#### DynamicFlags

This Field Flags Controls The Visual Appearance Of The Creature. These Flag Values Can Be Added Together For Any Desired Combination.

Some Known Flag Values Are:

| Flag | Name                                   | Comments                                                                                     |
| ---- | -------------------------------------- | -------------------------------------------------------------------------------------------- |
| 0    | UNIT_DYNFLAG_NONE                      |                                                                                              |
| 1    | UNIT_DYNFLAG_LOOTABLE                  |                                                                                              |
| 2    | UNIT_DYNFLAG_TRACK_UNIT                |                                                                                              |
| 4    | UNIT_DYNFLAG_TAPPED                    | Lua_UnitIsTapped - Makes creatures name appear grey (good for simulating dead creatures) ??? |
| 8    | UNIT_DYNFLAG_TAPPED_BY_PLAYER          | Lua_UnitIsTappedByPlayer                                                                     |
| 16   | UNIT_DYNFLAG_SPECIALINFO               | Shows creatures basic stats (Health, damage, resistances, tamable).                          |
| 32   | UNIT_DYNFLAG_DEAD                      | Makes the creature appear dead (this DOES NOT make the creatures name grey)                  |
| 64   | UNIT_DYNFLAG_REFER_A_FRIEND            |                                                                                              |
| 128  | UNIT_DYNFLAG_TAPPED_BY_ALL_THREAT_LIST | Lua_UnitIsTappedByAllThreatList                                                              |

#### ExtraFlags

This Field Controls the Application Of Flags That Controls Certain NPC Specific Attributes.

| Bit     | Hex        | Name                                           | Description                                                                                                            |
| ------- | ---------- | ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| 1       | 0x00000001 | CREATURE_EXTRA_FLAG_INSTANCE_BIND              | creature kill bind instance with killer and killer's group                                                             |
| 2       | 0x00000002 | CREATURE_EXTRA_FLAG_NO_AGGRO_ON_SIGHT          | no aggro (ignore faction/reputation hostility)                                                                         |
| 4       | 0x00000004 | CREATURE_EXTRA_FLAG_NO_PARRY                   | creature can't parry                                                                                                   |
| 8       | 0x00000008 | CREATURE_EXTRA_FLAG_NO_PARRY_HASTEN            | creature can't counter-attack at parry                                                                                 |
| 16      | 0x00000010 | CREATURE_EXTRA_FLAG_NO_BLOCK                   | creature can't block                                                                                                   |
| 32      | 0x00000020 | CREATURE_EXTRA_FLAG_NO_CRUSH                   | creature can't do crush attacks                                                                                        |
| 64      | 0x00000040 | CREATURE_EXTRA_FLAG_NO_XP_AT_KILL              | creature kill not provide XP                                                                                           |
| 128     | 0x00000080 | CREATURE_EXTRA_FLAG_INVISIBLE                  | creature is always invisible for player (mostly trigger creatures)                                                     |
| 256     | 0x00000100 | CREATURE_EXTRA_FLAG_NOT_TAUNTABLE              | creature is immune to taunt auras and effect attack me                                                                 |
| 512     | 0x00000200 | CREATURE_EXTRA_FLAG_AGGRO_ZONE                 | creature sets itself in combat with zone on aggro                                                                      |
| 1024    | 0x00000400 | CREATURE_EXTRA_FLAG_GUARD                      | creature is a guard                                                                                                    |
| 2048    | 0x00000800 | CREATURE_EXTRA_FLAG_NO_CALL_ASSIST             | creature shouldn't call for assistance on aggro                                                                        |
| 4096    | 0x00001000 | CREATURE_EXTRA_FLAG_ACTIVE                     | creature is active object. Grid of this creature will be loaded and creature set as active                             |
| 8192    | 0x00002000 | CREATURE_EXTRA_FLAG_MMAP_FORCE_ENABLE          | creature is forced to use MMaps                                                                                        |
| 16384   | 0x00004000 | CREATURE_EXTRA_FLAG_MMAP_FORCE_DISABLE         | creature is forced to NOT use MMaps                                                                                    |
| 32768   | 0x00008000 | CREATURE_EXTRA_FLAG_WALK_IN_WATER              | creature is forced to walk in water even it can swim                                                                   |
| 65536   | 0x00010000 | CREATURE_EXTRA_FLAG_CIVILIAN                   | CreatureInfo->civilian substitute (for expansions as Civilian Colum was removed)                                       |
| 131072  | 0x00020000 | CREATURE_EXTRA_FLAG_NO_MELEE                   | creature can't melee                                                                                                   |
| 262144  | 0x00040000 | CREATURE_EXTRA_FLAG_FAR_VIEW                   | creature with far view                                                                                                 |
| 524288  | 0x00080000 | CREATURE_EXTRA_FLAG_FORCE_ATTACKING_CAPABILITY | SetForceAttackingCapability(true); for nonattackable, nontargetable creatures that should be able to attack nontheless |
| 1048576 | 0x00100000 | CREATURE_EXTRA_FLAG_IGNORE_USED_POSITION       | ignore creature when checking used positions around target                                                             |
| 2097152 | 0x00200000 | CREATURE_EXTRA_FLAG_COUNT_SPAWNS               | count creature spawns in Map*                                                                                          |
| 4194304 | 0x00400000 | CREATURE_EXTRA_FLAG_HASTE_SPELL_IMMUNITY       | immunity to COT or Mind Numbing Poison - very common in instances                                                      |

#### CreatureTypeFlags

This Field Controls If a Mob Is Mineable or Herbable. If Any Of These Flags Are Used Then The Loot Given When It Is Herb Picked / Mined Will Be Stored In The [Skinning\_Loot\_Template](Skinning_Loot_Template) Table. Aside From These Two Flags, This Field Has No Special Meaning Server-Side.

It will be send to the client in SMSG\_CREATURE\_QUERY\_RESPONSE

| Flag  | Name                               | Comments                                                                                                               |
| ----- | ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| 1     | CREATURE_TYPEFLAGS_TAMEABLE        | Makes the mob tameable (must also be a beast and have family set)                                                      |
| 2     | CREATURE_TYPEFLAGS_GHOST_VISIBLE   | Sets Creatures that can ALSO be seen when player is a ghost. Used in CanInteract function by client, can't be attacked |
| 4     | CREATURE_TYPEFLAGS_UNK3            | Sets "BOSS" flag for tooltips                                                                                          |
| 8     | CREATURE_TYPEFLAGS_UNK4            |                                                                                                                        |
| 16    | CREATURE_TYPEFLAGS_UNK5            | Controls something in client tooltip related to creature faction                                                       |
| 32    | CREATURE_TYPEFLAGS_UNK6            | Something related to Sound                                                                                             |
| 64    | CREATURE_TYPEFLAGS_UNK7            | Related to attackable / not attackable creatures with spells                                                           |
| 128   | CREATURE_TYPEFLAGS_INTERACT_DEAD   | has something to do with unit interaction / quest status requests                                                      |
| 136   | CREATURE_TYPEFLAGS_NON_PVP_PLAYER  |                                                                                                                        |
| 256   | CREATURE_TYPEFLAGS_HERBLOOT        | Makes Mob Corpse Herbable - Uses Skinning Loot Field                                                                   |
| 512   | CREATURE_TYPEFLAGS_MININGLOOT      | Makes Mob Corpse Mineable - Uses Skinning Loot Field                                                                   |
| 1024  | CREATURE_TYPEFLAGS_ANIMATION_UNK11 | no idea, but it used by client                                                                                         |
| 2048  | CREATURE_TYPEFLAGS_ANIMATION_UNK12 | related to possibility to cast spells while mounted                                                                    |
| 4096  | CREATURE_TYPEFLAGS_CAN_ASSIST      | Can aid any player or group in combat. Typically seen for escorting NPC's                                              |
| 8192  | CREATURE_TYPEFLAGS_UNK14           | checked from calls in Lua_PetHasActionBar                                                                              |
| 16384 | CREATURE_TYPEFLAGS_UNK15           | Lua_UnitGUID, client does guid_low &amp;= 0xFF000000 if this flag is set                                               |
| 32768 | CREATURE_TYPEFLAGS_ENGINEERLOOT    | Makes Mob Corpse Engineer Lootable - Uses Skinning Loot Field                                                          |

#### SpeedWalk

This Field Controls How Fast An NPC Moves When Walking. This Value Comes From Sniff Packet Data.
Note: This field should only be used as an override if the model's default SpeedWalk is not correct for the creature\_template.entry. ( [creature\_model\_info.SpeedWalk](creature_model_info#SpeedWalk) )

\`SpeedWalk\` = (sniffed value / 2.5)

(Default Value Is: 1)

#### SpeedRun

This Field Controls How Fast An NPC Moves When Running. This Value Comes From Sniff Packet Data.
Note: This field should only be used as an override if the model's default SpeedRun is not correct for the creature\_template.entry. ( [creature\_model\_info.SpeedRun](creature_model_info#SpeedRun) )

\`SpeedRun\` = (sniffed value / 7)

(Default Value Is: 1.14286)

#### UnitClass

The NPC Unit Class. This Field is a Critical Value That Dictates An NPC's Base Stats System.

An NPC's Unit Class Is A Corner Stone Value Used In [Creature\_Template\_Classlevelstats](Creature_Template_Classlevelstats) To Determine An NPC's Stats.

NPC Stats Refers To: (Health/Mana/Damage/Armor).

In WOTLK and CATA There Are 4 Possible NPC Classes Available For Creatures:
(Class: 1,2,4,8)

In Classic and TBC There Are 3 Possible NPC Classes Available For Creatures:
(Class: 1,2,8)

| ID             | Name |
|----------------|------|
| CLASS\_WARRIOR | 1    |
| CLASS\_PALADIN | 2    |
| CLASS\_ROGUE   | 4    |
| CLASS\_MAGE    | 8    |

This Value is Contained in Sniff Data: UNIT\_FIELD\_BYTES\_0 located in SMSG\_UPDATE\_OBJECT
It is a Critical Field in Determining Class Level Stats For the NPC.

NOTE: Typically ONLY Vehicles Are Class=4

Warriors: Do Not Have Mana and Maximum Health and Damage
Paladins: Have a Small Amount Of Mana and Slightly Less Health and Damage From a Warrior
Rogues: (Little is Known Currently But They All Seem To Be Vehicles)
Mages: Have Lots of Mana But Have Very Low Health and Damage

#### Rank

This Field Determines The Rank of the NPC:

| Rank | Name       | Comments                                       |
|------|------------|------------------------------------------------|
| 0    | Normal     |                                                |
| 1    | Elite      | Higher damage, more health, better loot.       |
| 2    | Rare Elite | A rare mob but with elite damage and health.   |
| 3    | World Boss | Highest rank, best loot, longest respawn time. |
| 4    | Rare       | Somewhat better loot, longer respawn time.     |

#### HealthMultiplier

This Value Comes From WDB and Sniff Data. This Is The PRIMARY DB Value That Calculates An NPC's Specific Health Value. NPC Have Various HealthMultipliers But Typically They Are Fairly Rounded Values

(Note: Dungeon/Raid/World Bosses Normally Have Large Very Rounded Values Normally)

This Is The Multiplier Used Against The BaseHealthExp? Value From [Creature\_Template\_ClassLevelStats](Creature_Template_ClassLevelStats) To Calculate An NPC's Final Health Values.

Formula:
MinLevelHealth = ROUND (BaseHealthExp? \* HealthMultiplier)
MaxLevelHealth = ROUND (BaseHealthExp? \* HealthMultiplier)

Example:

| Field                                 | Value | Comments          |
|---------------------------------------|-------|-------------------|
| [Entry](#Entry)                       | 871   | Saltscale Warrior |
| [MinLevel](#MinLevel)                 | 35    | (Sniff Data)      |
| [MaxLevel](#MaxLevel)                 | 36    | (Sniff Data)      |
| [MinLevelHealth](#MinLevelHealth)     | 1403  | (Sniff Data)      |
| [MaxLevelHealth](#MaxLevelHealth)     | 1469  | (Sniff Data)      |
| [UnitClass](#UnitClass)               | 1     | (Sniff Data)      |
| [HealthMultiplier](#HealthMultiplier) | 1.15  | (Sniff Data)      |

Level 35 BaseHealthExp0: 1220
(From [Creature\_Template\_ClassLevelStats](Creature_Template_ClassLevelStats) - BaseHealth Values Calculated From Sniff Data And Extensive Research)

Level 36 BaseHealthExp0: 1277
(From [Creature\_Template\_ClassLevelStats](Creature_Template_ClassLevelStats) - BaseHealth Values Calculated From Sniff Data And Extensive Research)

MinLevelHealth = ROUND (1220\*1.15) = 1403 (1403)
MaxLevelHealth = ROUND (1277\*1.15) = 1468.55 (1469)

#### PowerMultiplier

This Value Comes From WDB and Sniff Data. This Is The PRIMARY DB Value That Calculates An NPC's Specific Mana Value. All NPC Have Nice Rounded Values For PowerMultipliers.

This Is The Multiplier Used Against The BaseMana Value From [Creature\_Template\_ClassLevelStats](Creature_Template_ClassLevelStats) To Calculate An NPC's Final Mana Values.

Note: BaseMana Values Do NOT Scale With Expansion Values Unlike Health And Damage.
Note: For NPC that use Other Power then Mana it will reflect that power instead.

Formula:
MinLevelMana = ROUND (BaseMana \* ManaMultiplier)
MaxLevelMana = ROUND (BaseMana \* ManaMultiplier)

Example:

| Field                              | Value | Comments               |
|------------------------------------|-------|------------------------|
| [Entry](#Entry)                    | 7335  | Death's Head Geomancer |
| [MinLevel](#MinLevel)              | 35    | (Sniff Data)           |
| [MaxLevel](#MaxLevel)              | 35    | (Sniff Data)           |
| [MinLevelMana](#MinLevelMana)      | 5360  | (Sniff Data)           |
| [MaxLevelMana](#MaxLevelMana)      | 5360  | (Sniff Data)           |
| [UnitClass](#UnitClass)            | 8     | (Sniff Data)           |
| [PowerMultiplier](#ManaMultiplier) | 2     | (Sniff Data)           |

Level 35 BaseMana: 2680
(From [Creature\_Template\_ClassLevelStats](Creature_Template_ClassLevelStats) - BaseMana Values Calculated From Sniff Data And Extensive Research)

MinLevelMana = ROUND (2680\*2) = 5360 (5360)
MaxLevelMana = ROUND (2680\*2) = 5360 (5360)

#### DamageMultiplier

This field is the PRIMARY Field for adjusting and setting the Min/Max Damage Values for an NPC.

Damage Calculation Formulas

MIN MELEE DAMAGE = (((Creature\_Template\_Classlevelstats.BaseDamageExp? \* Creature\_Template.DamageVariance) + (Creature\_Template\_Classlevelstats.BaseMeleeAttackPower / 14)) \* (Creature\_Template.BaseMeleeAttackTime / 1000)) \* Creature\_Template.Dmg\_Multiplier

MAX MELEE DAMAGE = ((((Creature\_Template\_Classlevelstats.BaseDamageExp? \* Creature\_Template.DamageVariance) \* 1.5) + (Creature\_Template\_Classlevelstats.BaseMeleeAttackPower / 14)) \* (Creature\_Template.BaseMeleeAttackTime / 1000)) \* Creature\_Template.Dmg\_Multiplier

Some NPC Have Damage Multipliers Applied To Increase Their Damage Above That Of a Normal NPC Of The Same Level.

I am sure people are asking... WHY is there more then just a simple Damage Multiplier Involved To Boost NPC Damage? Here is the only logical answer. With some NPC (Like Bosses) Who have Multipliers in the range of 20 - 75 Min and Max Damage values can fluctuate into VERY Large Ranges. So What Blizz has done is create a Co-Efficient System of 2 Values to help Reign in Max Damage Values so if you require a Set Min/Max Damage For an NPC it can scale the BaseDamage so after being put though the Formula The Min and Max Damage values will be within the Required Range. Damage Variance is used to reduce the Max Damage Value. For NPC Who Do NOT Have an altered Damage Variance the Default Value used is 1 (Normal Variance = 1).

------------------------------------------------------------------------

Here is an Example of an NPC Melee Damage Calculation
-----------------------------------------------------

Nexus-Prince Shaffar = Unit Class 2 (BOSS)
Level 66: BaseDamage = 78.472 / Melee AttackPower = 266 / Base Melee Attack Time = 2000
Bestiary Min Dmg: 1136
Bestiary Max Dmg: 1593
Damage Variance: 1.0 (No Variance)
Damage Multiplier: 5.83 (Calculated Value)

CalculatedMinMeleeDmg=ROUND(((BaseDamage \* Damage Variance) + (Base Melee Attackpower / 14)) \* (Base Attack Time/1000)) \* Damage Multiplier
= ((((78.472 \* 1.0) + (266/14)) \* (2000/1000)) \* 5.83
= (((78.472) + 19) \* 2) = 194.944 \* 5.83 = 1136.52352

CalculatedMaxMeleeDmg=ROUND((((BaseDamage \* Damage Variance) \* 1.5) + (Base Melee Attack Power / 14)) \* (Base Attack Time/1000)) \* Damage Multiplier
= ((((78.472 \* 1.0) \* 1.5) + (266/14)) \* (2000/1000)) \* 5.83
= (((117.708) + 19) \* 2) = 273.416 \* 5.83 = 1594.01528

NOTE:

Very Slight Rounding Errors of 1 or 2 Damage Might Occur... This was due to Rounding When Generating BaseDamage Values in Calculations.

#### DamageVariance

Damage Variance is a Co-Efficient used in Damage Calculations To Limit the Min/Max Damage Range.

Default Value is 1 (Normal) ===> See [DamageMultiplier](#DamageMultiplier) for More Information

#### ArmorMultiplier

This Value Is The Multiplier Value Used To Multiply Against BaseArmor Value in Creature\_Template\_Classlevelstats

Most Normal NPC are = 1

#### ExperienceMultiplier

NOTE: This Field Is Currently Not Used By The Core (Future Implementation)

#### MinLevelHealth

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
(Nice Field To Have Still)

Minimum Level Health Is Now Calculated Using [HealthMultiplier](#HealthMultiplier)

Core Now Automatically Calculates This Value On The Fly

#### MaxLevelHealth

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
(Nice Field To Have Still)

Maximum Level Health Is Now Calculated Using [HealthMultiplier](#HealthMultiplier)

Core Now Automatically Calculates This Value On The Fly

#### MinLevelMana

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
(Nice Field To Have Still)

Minimum Level Mana Is Now Calculated Using [PowerMultiplier](#PowerMultiplier)

Core Now Automatically Calculates This Value On The Fly

#### MaxLevelMana

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
(Nice Field To Have Still)

Maximum Level Mana Is Now Calculated Using [PowerMultiplier](#PowerMultiplier)

Core Now Automatically Calculates This Value On The Fly

#### MinMeleeDmg

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
(Nice Field To Have Still)

Minimum Melee Damage Is Now Calculated Using [DamageMultiplier](#DamageMultiplier)

Core Now Automatically Calculates This Value On The Fly

#### MaxMeleeDmg

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
(Nice Field To Have Still)

Maximum Melee Damage Is Now Calculated Using [DamageMultiplier](#DamageMultiplier)

Core Now Automatically Calculates This Value On The Fly

#### MinRangedDmg

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
(Nice Field To Have Still)

Minimum Ranged Damage Is Now Calculated Using [DamageMultiplier](#DamageMultiplier)

Core Now Automatically Calculates This Value On The Fly

#### MaxRangedDmg

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
(Nice Field To Have Still)

Maximum Ranged Damage Is Now Calculated Using [DamageMultiplier](#DamageMultiplier)

Core Now Automatically Calculates This Value On The Fly

#### Armor

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
DB Devs: Suggested Apply Armor Value For MaxLevel For This Field For FYI Purposes

(Old System Did Not Properly Calculate Armor Values for different NPC Levels)

Core Now Automatically Calculates This Value On The Fly

#### MeleeAttackPower

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
DB Devs: Suggested Apply Value For MaxLevel For This Field For FYI Purposes

Core Now Gets Value From [Creature\_Template\_ClassLevelStats](Creature_Template_ClassLevelStats)

(Old System Did Not Properly Calculate Values for Damage Calculations)

#### RangedAttackPower

NOTE: This Field Is No Longer Used By The Core - Maintained For DB Developers
DB Devs: Suggested Apply Value For MaxLevel For This Field For FYI Purposes

Core Now Gets Value From [Creature\_Template\_ClassLevelStats](Creature_Template_ClassLevelStats)

(Old System Did Not Properly Calculate Values for Damage Calculations)

#### MeleeBaseAttackTime

An NPC's melee attack time in milliseconds. This Field is populated by Sniff Data.

This field is used as part of Min/Max Melee Damage Formula Calculations.

#### RangedBaseAttackTime

An NPC's ranged attack time in milliseconds. This Field is populated by Sniff Data.

This field is used as part of Min/Max Ranged Damage Formula Calculations.

#### DamageSchool

NPC's Melee Damage School. All Melee Damage Will Be Done As This Spell School Damage Set Here.

NOTE: 0 (Normal) = Physical Damage

| ID  | Name                  |
|-----|-----------------------|
| 0   | SPELL\_SCHOOL\_NORMAL |
| 1   | SPELL\_SCHOOL\_HOLY   |
| 2   | SPELL\_SCHOOL\_FIRE   |
| 3   | SPELL\_SCHOOL\_NATURE |
| 4   | SPELL\_SCHOOL\_FROST  |
| 5   | SPELL\_SCHOOL\_SHADOW |
| 6   | SPELL\_SCHOOL\_ARCANE |

#### MinLootGold

Minimum possible money that the NPC drops when killed, in copper.

An NPC Will Drop Random Value Between MinLootGold and MaxLootGold.

NOTE:
1 = 1 Copper
100 = 1 Silver
10000 = 1 Gold

#### MaxLootGold

Maximum possible money that the NPC drops when killed, in copper.

An NPC Will Drop Random Value Between MinLootGold and MaxLootGold.

NOTE:
1 = 1 Copper
100 = 1 Silver
10000 = 1 Gold

#### LootId

The ID of the Loot Template that this NPC uses to generate loot from.
See [creature\_loot\_template.entry](creature_loot_template#entry)

#### PickpocketLootId

The ID of the Pickpocketing Loot Template that this NPC should use to generate pickpocketing loot from.
See [pickpocketing\_loot\_template.entry](pickpocketing_loot_template#entry)

#### SkinningLootId

The ID of the Skinning Loot Template that this NPC should use to generate skinning loot from.
See [skinning\_loot\_template.entry](skinning_loot_template#entry)

CreatureTypeFlags can define the profession required to loot the creature.

| Type                            | Info                                                          |
| ------------------------------- | ------------------------------------------------------------- |
| CREATURE_TYPEFLAGS_HERBLOOT     | Makes Mob Corpse Herbable - Uses Skinning Loot Field          |
| CREATURE_TYPEFLAGS_MININGLOOT   | Makes Mob Corpse Mineable - Uses Skinning Loot Field          |
| CREATURE_TYPEFLAGS_ENGINEERLOOT | Makes Mob Corpse Engineer Lootable - Uses Skinning Loot Field |

For These Other Types Use Skinning\_Loot\_Template For Loot To Be Generated By These Other Professions Also

#### KillCredit1

Additional Creature Template Entry to Assign Quest Kill Credit on NPC Death.
Note: Some Quests Require Additional Quest Kill Credit

#### KillCredit2

Additional Creature Template Entry to Assign Quest Kill Credit on NPC Death.
Note: Some Quests Require Additional Quest Kill Credit

#### MechanicImmuneMask

This makes the NPC immune to specific spell natures. See Spell.dbc at row effect\_X\_mechanic\_id.

Uses references from SpellMechanic.dbc.

| Bit   | Bit       | Type               | Type                      |
|-------|--------------------|-----------|---------------------------|
| 1     | 32768     | MECHANIC\_CHARM    | MECHANIC\_BANDAGE         |
| 2     | 65536     | MECHANIC\_CONFUSED | MECHANIC\_POLYMORPH       |
| 4     | 131072    | MECHANIC\_DISARM   | MECHANIC\_BANISH          |
| 8     | 262144    | MECHANIC\_DISTRACT | MECHANIC\_SHIELD          |
| 16    | 524288    | MECHANIC\_FEAR     | MECHANIC\_SHACKLE         |
| 32    | 1048576   | MECHANIC\_FUMBLE   | MECHANIC\_MOUNT           |
| 64    | 2097152   | MECHANIC\_ROOT     | MECHANIC\_PERSUADE        |
| 128   | 4194304   | MECHANIC\_PACIFY   | MECHANIC\_TURN            |
| 256   | 8388608   | MECHANIC\_SILENCE  | MECHANIC\_HORROR          |
| 512   | 16777216  | MECHANIC\_SLEEP    | MECHANIC\_INVULNERABILITY |
| 1024  | 33554432  | MECHANIC\_SNARE    | MECHANIC\_INTERRUPT       |
| 2048  | 67108864  | MECHANIC\_STUN     | MECHANIC\_DAZE            |
| 4096  | 134217728 | MECHANIC\_FREEZE   | MECHANIC\_DISCOVERY       |
| 8192  | 268435456 | MECHANIC\_KNOCKOUT | MECHANIC\_IMMUNE\_SHIELD  |
| 16384 | 536870912 | MECHANIC\_BLEED    | MECHANIC\_SAPPED          |

To combine immunities just add values. Immune to everything corresponds to the value 1073741823.

#### SchoolImmuneMask

This makes the NPC immune to specific spell schools.

| Type                  | Bitmask |
|-----------------------|---------|
| SPELL\_SCHOOL\_NORMAL | 1       |
| SPELL\_SCHOOL\_HOLY   | 2       |
| SPELL\_SCHOOL\_FIRE   | 4       |
| SPELL\_SCHOOL\_NATURE | 8       |
| SPELL\_SCHOOL\_FROST  | 16      |
| SPELL\_SCHOOL\_SHADOW | 32      |
| SPELL\_SCHOOL\_ARCANE | 64      |

To combine spell school immunities just add values. Immune to everything corresponds to the value 127.

#### ResistanceHoly

An NPC's Additional Holy Spell Resistance Value.

#### ResistanceFire

An NPC's Additional Fire Spell Resistance Value.

#### ResistanceNature

An NPC's Additional Nature Spell Resistance Value.

#### ResistanceFrost

An NPC's Additional Frost Spell Resistance Value.

#### ResistanceShadow

An NPC's Additional Shadow Spell Resistance Value.

#### ResistanceArcane

An NPC's Additional Arcane Spell Resistance Value.

#### PetSpellDataId

ID that displays what spells the pet has in the client.

Note: This Value Comes From DBC (Not Confirmed)

#### MovementType

The NPC's default Movement Type.

| ID  | Type                                                  |
|-----|-------------------------------------------------------|
| 0   | Idle - Stand Still (Stationary)                       |
| 1   | Random Movement - Random Move Inside SpawnDist Radius |
| 2   | Waypoint Movement - Move Along Waypoint Path Defined  |

#### TrainerType

If the NPC is a Trainer (Has Trainer NPCFlag Set), then this field controls what kind of Trainer the NPC is.

NOTE: Both this field and the related field must be filled in for a trainer to work correctly.

| ID  | Related Field  | Type                       | Comments            |
|-----|----------------------------|----------------|---------------------|
| 0   | trainer\_class | TRAINER\_TYPE\_CLASS       | Trains Class Spells |
| 1   | trainer\_race  | TRAINER\_TYPE\_MOUNTS      | Trains Riding Skill |
| 2   | trainer\_spell | TRAINER\_TYPE\_TRADESKILLS | Trains Professions  |
| 3   | trainer\_class | TRAINER\_TYPE\_PETS        | Trains Pet Skills   |

#### TrainerSpell

If the NPC is a trainer that teaches professions ([trainer\_type](creature_template#trainer_type) == 2), then the player must already know the spell ID specified here to be able to talk to this NPC.

#### TrainerClass

If the NPC is a class trainer or a pet trainer ([trainer\_type](creature_template#trainer_type) == 0 or 3), then the player's class must be the same as the value specified here to talk to this trainer. For pet trainers, this value must be 3 (hunter). See [character.class](character#class)

#### TrainerRace

If the NPC is a mount trainer ([trainer\_type](creature_template#trainer_type) == 1), then the player's race must be the same as the value specified here to talk to this trainer. See [character.race](character#race)

#### TrainerTemplateId

The id refers to the [npc\_trainer\_template.](npc_trainer_template).

#### VendorTemplateId

The id refers to the [npc\_vendor\_template.](npc_vendor_template).

#### GossipMenuId

Reference to a [gossip\_menu\_id](gossip_menu).

#### EquipmentTemplateId

The default ID of the equipment that this creature should display. See [creature\_equip\_template.entry](creature_equip_template#entry)

#### Civilian

Used to define Honourable/Dishonourable kills.

| ID  | Comments |
|-----|----------|
| 0   | Normal   |
| 1   | Civilian |

#### AIName

Overrides AI used for the creature.

| Name        | Description                                                    |
|-------------|----------------------------------------------------------------|
| NullAI      | Empty AI, creature does nothing.                               |
| AggressorAI | Creature attacks as soon as something is in aggro range.       |
| ReactorAI   | Creature attacks only if aggroed by attack, spell etc.         |
| GuardAI     |                                                                |
| PetAI       | Creature is a pet.                                             |
| TotemAI     | Creature casts spell from field spell1, otherwise like NullAI. |
| EventAI     | Creature uses Event Based AI (Creature AI).                    |
|             |                                                                |

#### ScriptName

The SD2 Script Name that this creature uses, if any. This ties a script from a scripting engine to this creature.
