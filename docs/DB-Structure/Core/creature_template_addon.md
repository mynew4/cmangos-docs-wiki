Back to [world database](mangosdb_struct) list of tables.

The \`creature\_(template\_)addon\` tables
------------------------------------------

define different things that are applied on creatures when they are loaded, either by [\`creature\`.\`guid\`](Creature#guid) or [\`creature\_template\`.\`entry\`](Creature_template#entry).
So two creatures using the same creature\_template\_addon can look different, if one is additionally defined in creature\_addon.

Through the use of the fields in this table, many things can be changed about the outward visual appearance of the creature. Potential usage examples are: to have the creature be mounted, to have it emote something, to have it display an aura effect, etc.

NOTE:

-   A creature\_addon record will override a creature\_template\_addon record should they overlap on the same creature.
-   The data for this table is largely incomplete and is mostly just a regurgitation of what the client receives from the server. This article is a WIP as to what all the possible values are.

### Structure

| **Field**                                            | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [entry/guid](creature_template_addon#entry/guid)     | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [mount](creature_template_addon#mount)               | mediumint(8) unsigned | NO       |         | 0           |           |
| [bytes1](creature_template_addon#bytes1)             | int(10) unsigned      | NO       |         | 0           |           |
| [b2\_0\_sheath](creature_template_addon#b2_0_sheath) | tinyint(3) unsigned   | NO       |         | 0           |           |
| [b2\_1\_flags](creature_template_addon#b2_1_flags)   | tinyint(3) unsigned   | NO       |         | 0           |           |
| [emote](creature_template_addon#emote)               | mediumint(8) unsigned | NO       |         | 0           |           |
| [moveflags](creature_template_addon#moveflags)       | int(10) unsigned      | NO       |         | 0           |           |
| [auras](creature_template_addon#auras)               | text                  | YES      |         |             |           |

### Description of the fields

#### entry/guid

For creature\_template\_addon, this field signifies the creature template ID. It will affect all spawned creatures using that template ID. For creature\_addon, this field signifies a unique creature guid. It will affect just that creature whose GUID matches the one specified here.

#### mount

The model ID of the mount to be used to make the creature appear mounted. The value here overrides the value for the creature's unit field UNIT\_FIELD\_MOUNTDISPLAYID. List of known values and what their visual effects on the creature

#### bytes1

(UNIT\_FIELD\_BYTES\_1,0)

| Bit | Name                              | Comment                                                             |
| --- | --------------------------------- | ------------------------------------------------------------------- |
| 0   | UNIT_STAND_STATE_STAND            | normal behavior                                                     |
| 1   | UNIT_STAND_STATE_SIT              | sitting on ground                                                   |
| 2   | UNIT_STAND_STATE_SIT_CHAIR        | sitting on normal chair                                             |
| 3   | UNIT_STAND_STATE_SLEEP            | sleeping                                                            |
| 4   | UNIT_STAND_STATE_SIT_LOW_CHAIR    | sitting on low chair                                                |
| 5   | UNIT_STAND_STATE_SIT_MEDIUM_CHAIR | sitting on medium chair                                             |
| 6   | UNIT_STAND_STATE_SIT_HIGH_CHAIR   | sitting on high chair                                               |
| 7   | UNIT_STAND_STATE_DEAD             | play dead                                                           |
| 8   | UNIT_STAND_STATE_KNEEL            | kneel                                                               |
| 9   | UNIT_STAND_STATE_CUSTOM           | Depends on model animation. Submerge, freeze, hide, hibernate, rest |
#### bytes1\_flags

(UNIT\_FIELD\_BYTES\_1,3) used instead of bytes1 in some cases.

| Flag     | Name                         | Comment                                                                                                                                           |
| -------- | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0x01     | UNIT_BYTE1_FLAG_ALWAYS_STAND | always stand state                                                                                                                                |
| 0x02     | UNIT_BYTE1_FLAG_FLY_ANIM     | Creature that can fly and are not on the ground appear to have this flag. If they are on the ground, flag is not present.                         |
| 0x04     | UNIT_BYTE1_FLAG_UNTRACKABLE  | untrackable                                                                                                                                       |
| 65536    | ?                            | Linked to Defensive Stance? (not actively added flag?)                                                                                            |
| 131072   | ?                            | no name &amp; health bar visible with plate mode on (name only when targeted) Linked to Stealth? Linked to DeathState? (not actively added flag?) |
| 1048576  | ?                            | Linked to Defensive Stance? (not actively added flag?)                                                                                            |
| 33554432 | ?                            | Linked to Stealth? (not actively added flag?)                                                                                                     |
| 0xFF     | UNIT_BYTE1_FLAG_ALL          | all                                                                                                                                               |

#### b2\_0\_sheath

(UNIT\_FIELD\_BYTES\_2,0)

| Bit | Name                   | Comment                     |
|-----|------------------------|-----------------------------|
| 0   | SHEATH\_STATE\_UNARMED | all weapons sheathed        |
| 1   | SHEATH\_STATE\_MELEE   | melee weapon(s) unsheathed  |
| 2   | SHEATH\_STATE\_RANGED  | ranged weapon(s) unsheathed |

#### b2\_1\_flags

(UNIT\_FIELD\_BYTES\_2,1)

| Bit | Name                                           | Comment |
|-----|------------------------------------------------|---------|
| 16  | UNIT\_BYTE2\_CREATURE\_DEBUFF\_LIMIT           | ?       |
| 40  | UNIT\_BYTE2\_PLAYER\_CONTROLLED\_DEBUFF\_LIMIT | ?       |

#### emote

Emote ID that the creature should continually perform.

COMPLETE LIST OF EMOTES CAN BE FOUND IN: Emotes.dbc
(They Are Different Between Client Versions)

| Bit | Name                                    | Bit | Name                                   |
|-----|-----------------------------------------|-----|----------------------------------------|
| 0   | EMOTE\_ONESHOT\_NONE                    | 400 | EMOTE\_STATE\_DANCESPECIAL             |
| 1   | EMOTE\_ONESHOT\_TALK                    | 401 | EMOTE\_ONESHOT\_DANCESPECIAL           |
| 2   | EMOTE\_ONESHOT\_BOW                     | 402 | EMOTE\_ONESHOT\_CUSTOMSPELL01          |
| 3   | EMOTE\_ONESHOT\_WAVE                    | 403 | EMOTE\_ONESHOT\_CUSTOMSPELL02          |
| 4   | EMOTE\_ONESHOT\_CHEER                   | 404 | EMOTE\_ONESHOT\_CUSTOMSPELL03          |
| 5   | EMOTE\_ONESHOT\_EXCLAMATION             | 405 | EMOTE\_ONESHOT\_CUSTOMSPELL04          |
| 6   | EMOTE\_ONESHOT\_QUESTION                | 406 | EMOTE\_ONESHOT\_CUSTOMSPELL05          |
| 7   | EMOTE\_ONESHOT\_EAT                     | 407 | EMOTE\_ONESHOT\_CUSTOMSPELL06          |
| 10  | EMOTE\_STATE\_DANCE                     | 408 | EMOTE\_ONESHOT\_CUSTOMSPELL07          |
| 11  | EMOTE\_ONESHOT\_LAUGH                   | 409 | EMOTE\_ONESHOT\_CUSTOMSPELL08          |
| 12  | EMOTE\_STATE\_SLEEP                     | 410 | EMOTE\_ONESHOT\_CUSTOMSPELL09          |
| 13  | EMOTE\_STATE\_SIT                       | 411 | EMOTE\_ONESHOT\_CUSTOMSPELL10          |
| 14  | EMOTE\_ONESHOT\_RUDE                    | 412 | EMOTE\_STATE\_EXCLAIM                  |
| 15  | EMOTE\_ONESHOT\_ROAR                    | 415 | EMOTE\_STATE\_SIT\_CHAIR\_MED          |
| 16  | EMOTE\_ONESHOT\_KNEEL                   | 422 | EMOTE\_STATE\_SPELLEFFECT\_HOLD        |
| 17  | EMOTE\_ONESHOT\_KISS                    | 423 | EMOTE\_STATE\_EAT\_NO\_SHEATHE         |
| 18  | EMOTE\_ONESHOT\_CRY                     | 424 | EMOTE\_STATE\_MOUNT                    |
| 19  | EMOTE\_ONESHOT\_CHICKEN                 | 425 | EMOTE\_STATE\_READY2HL                 |
| 20  | EMOTE\_ONESHOT\_BEG                     | 426 | EMOTE\_STATE\_SIT\_CHAIR\_HIGH         |
| 21  | EMOTE\_ONESHOT\_APPLAUD                 | 427 | EMOTE\_STATE\_FALL                     |
| 22  | EMOTE\_ONESHOT\_SHOUT                   | 428 | EMOTE\_STATE\_LOOT                     |
| 23  | EMOTE\_ONESHOT\_FLEX                    | 429 | EMOTE\_STATE\_SUBMERGED\_NEW           |
| 24  | EMOTE\_ONESHOT\_SHY                     | 430 | EMOTE\_ONESHOT\_COWER                  |
| 25  | EMOTE\_ONESHOT\_POINT                   | 431 | EMOTE\_STATE\_COWER                    |
| 26  | EMOTE\_STATE\_STAND                     | 432 | EMOTE\_ONESHOT\_USESTANDING            |
| 27  | EMOTE\_STATE\_READYUNARMED              | 433 | EMOTE\_STATE\_STEALTH\_STAND           |
| 28  | EMOTE\_STATE\_WORK                      | 434 | EMOTE\_ONESHOT\_OMNICAST\_GHOUL        |
| 29  | EMOTE\_STATE\_POINT                     | 435 | EMOTE\_ONESHOT\_ATTACKBOW              |
| 30  | EMOTE\_STATE\_NONE                      | 436 | EMOTE\_ONESHOT\_ATTACKRIFLE            |
| 33  | EMOTE\_ONESHOT\_WOUND                   | 437 | EMOTE\_STATE\_SWIM\_IDLE               |
| 34  | EMOTE\_ONESHOT\_WOUNDCRITICAL           | 438 | EMOTE\_STATE\_ATTACK\_UNARMED          |
| 35  | EMOTE\_ONESHOT\_ATTACKUNARMED           | 439 | EMOTE\_ONESHOT\_SPELLCAST\_W\_SOUND    |
| 36  | EMOTE\_ONESHOT\_ATTACK1H                | 440 | EMOTE\_ONESHOT\_DODGE                  |
| 37  | EMOTE\_ONESHOT\_ATTACK2HTIGHT           | 441 | EMOTE\_ONESHOT\_PARRY1H                |
| 38  | EMOTE\_ONESHOT\_ATTACK2HLOOSE           | 442 | EMOTE\_ONESHOT\_PARRY2H                |
| 39  | EMOTE\_ONESHOT\_PARRYUNARMED            | 443 | EMOTE\_ONESHOT\_PARRY2HL               |
| 43  | EMOTE\_ONESHOT\_PARRYSHIELD             | 444 | EMOTE\_STATE\_FLYFALL                  |
| 44  | EMOTE\_ONESHOT\_READYUNARMED            | 445 | EMOTE\_ONESHOT\_FLYDEATH               |
| 45  | EMOTE\_ONESHOT\_READY1H                 | 446 | EMOTE\_STATE\_FLY\_FALL                |
| 48  | EMOTE\_ONESHOT\_READYBOW                | 447 | EMOTE\_ONESHOT\_FLY\_SIT\_GROUND\_DOWN |
| 50  | EMOTE\_ONESHOT\_SPELLPRECAST            | 448 | EMOTE\_ONESHOT\_FLY\_SIT\_GROUND\_UP   |
| 51  | EMOTE\_ONESHOT\_SPELLCAST               | 449 | EMOTE\_ONESHOT\_EMERGE                 |
| 53  | EMOTE\_ONESHOT\_BATTLEROAR              | 450 | EMOTE\_ONESHOT\_DRAGONSPIT             |
| 54  | EMOTE\_ONESHOT\_SPECIALATTACK1H         | 451 | EMOTE\_STATE\_SPECIALUNARMED           |
| 60  | EMOTE\_ONESHOT\_KICK                    | 452 | EMOTE\_ONESHOT\_FLYGRAB                |
| 61  | EMOTE\_ONESHOT\_ATTACKTHROWN            | 453 | EMOTE\_STATE\_FLYGRABCLOSED            |
| 64  | EMOTE\_STATE\_STUN                      | 454 | EMOTE\_ONESHOT\_FLYGRABTHROWN          |
| 65  | EMOTE\_STATE\_DEAD                      | 455 | EMOTE\_STATE\_FLY\_SIT\_GROUND         |
| 66  | EMOTE\_ONESHOT\_SALUTE                  | 456 | EMOTE\_STATE\_WALKBACKWARDS            |
| 68  | EMOTE\_STATE\_KNEEL                     | 457 | EMOTE\_ONESHOT\_FLYTALK                |
| 69  | EMOTE\_STATE\_USESTANDING               | 458 | EMOTE\_ONESHOT\_FLYATTACK1H            |
| 70  | EMOTE\_ONESHOT\_WAVE\_NOSHEATHE         | 459 | EMOTE\_STATE\_CUSTOMSPELL08            |
| 71  | EMOTE\_ONESHOT\_CHEER\_NOSHEATHE        | 460 | EMOTE\_ONESHOT\_FLY\_DRAGONSPIT        |
| 92  | EMOTE\_ONESHOT\_EAT\_NOSHEATHE          | 461 | EMOTE\_STATE\_SIT\_CHAIR\_LOW          |
| 93  | EMOTE\_STATE\_STUN\_NOSHEATHE           | 462 | EMOTE\_ONE\_SHOT\_STUN                 |
| 94  | EMOTE\_ONESHOT\_DANCE                   | 463 | EMOTE\_ONESHOT\_SPELLCAST\_OMNI        |
| 113 | EMOTE\_ONESHOT\_SALUTE\_NOSHEATH        | 465 | EMOTE\_STATE\_READYTHROWN              |
| 133 | EMOTE\_STATE\_USESTANDING\_NOSHEATHE    | 466 | EMOTE\_ONESHOT\_WORK\_CHOPWOOD         |
| 153 | EMOTE\_ONESHOT\_LAUGH\_NOSHEATHE        | 467 | EMOTE\_ONESHOT\_WORK\_MINING           |
| 173 | EMOTE\_STATE\_WORK\_NOSHEATHE           | 468 | EMOTE\_STATE\_SPELL\_CHANNEL\_OMNI     |
| 193 | EMOTE\_STATE\_SPELLPRECAST              | 469 | EMOTE\_STATE\_SPELL\_CHANNEL\_DIRECTED |
| 213 | EMOTE\_ONESHOT\_READYRIFLE              | 470 | EMOTE\_STAND\_STATE\_NONE              |
| 214 | EMOTE\_STATE\_READYRIFLE                | 471 | EMOTE\_STATE\_READYJOUST               |
| 233 | EMOTE\_STATE\_WORK\_NOSHEATHE\_MINING   | 473 | EMOTE\_STATE\_STRANGULATE              |
| 234 | EMOTE\_STATE\_WORK\_NOSHEATHE\_CHOPWOOD | 474 | EMOTE\_STATE\_READYSPELLOMNI           |
| 253 | EMOTE\_zzOLDONESHOT\_LIFTOFF            | 475 | EMOTE\_STATE\_HOLD\_JOUST              |
| 254 | EMOTE\_ONESHOT\_LIFTOFF                 | 476 | EMOTE\_ONESHOT\_CRY\_JAINA             |
| 273 | EMOTE\_ONESHOT\_YES                     |     |                                        |
| 274 | EMOTE\_ONESHOT\_NO                      |     |                                        |
| 275 | EMOTE\_ONESHOT\_TRAIN                   |     |                                        |
| 293 | EMOTE\_ONESHOT\_LAND                    |     |                                        |
| 313 | EMOTE\_STATE\_AT\_EASE                  |     |                                        |
| 333 | EMOTE\_STATE\_READY1H                   |     |                                        |
| 353 | EMOTE\_STATE\_SPELLKNEELSTART           |     |                                        |
| 373 | EMOTE\_STATE\_SUBMERGED                 |     |                                        |
| 374 | EMOTE\_ONESHOT\_SUBMERGE                |     |                                        |
| 375 | EMOTE\_STATE\_READY2H                   |     |                                        |
| 376 | EMOTE\_STATE\_READYBOW                  |     |                                        |
| 377 | EMOTE\_ONESHOT\_MOUNTSPECIAL            |     |                                        |
| 378 | EMOTE\_STATE\_TALK                      |     |                                        |
| 379 | EMOTE\_STATE\_FISHING                   |     |                                        |
| 380 | EMOTE\_ONESHOT\_FISHING                 |     |                                        |
| 381 | EMOTE\_ONESHOT\_LOOT                    |     |                                        |
| 382 | EMOTE\_STATE\_WHIRLWIND                 |     |                                        |
| 383 | EMOTE\_STATE\_DROWNED                   |     |                                        |
| 384 | EMOTE\_STATE\_HOLD\_BOW                 |     |                                        |
| 385 | EMOTE\_STATE\_HOLD\_RIFLE               |     |                                        |
| 386 | EMOTE\_STATE\_HOLD\_THROWN              |     |                                        |
| 387 | EMOTE\_ONESHOT\_DROWN                   |     |                                        |
| 388 | EMOTE\_ONESHOT\_STOMP                   |     |                                        |
| 389 | EMOTE\_ONESHOT\_ATTACKOFF               |     |                                        |
| 390 | EMOTE\_ONESHOT\_ATTACKOFFPIERCE         |     |                                        |
| 391 | EMOTE\_STATE\_ROAR                      |     |                                        |
| 392 | EMOTE\_STATE\_LAUGH                     |     |                                        |
| 393 | EMOTE\_ONESHOT\_CREATURE\_SPECIAL       |     |                                        |
| 394 | EMOTE\_ONESHOT\_JUMPLANDRUN             |     |                                        |
| 395 | EMOTE\_ONESHOT\_JUMPEND                 |     |                                        |
| 396 | EMOTE\_ONESHOT\_TALK\_NOSHEATHE         |     |                                        |
| 397 | EMOTE\_ONESHOT\_POINT\_NOSHEATHE        |     |                                        |
| 398 | EMOTE\_STATE\_CANNIBALIZE               |     |                                        |
| 399 | EMOTE\_ONESHOT\_JUMPSTART               |     |                                        |

#### moveflags

Flags controlling how the creature will behave animation-wise while moving. <span style="color: red">This table is 100% wrong as of 3.1. It is still here for a period of time for reference and to convert values in DB.

See the proper table under this one</span>

| Bit        | Name                      | Comment                                                                                |
| ---------- | ------------------------- | -------------------------------------------------------------------------------------- |
| 0          | MOVEMENTFLAG_NONE         |                                                                                        |
| 1          | MOVEMENTFLAG_FORWARD      | instantly teleport creature, then creature move forward animation but no real movement |
| 2          | MOVEMENTFLAG_BACKWARD     | instantly teleport creature, then creature move back animation but no real movement    |
| 4          | MOVEMENTFLAG_STRAFE_LEFT  | instantly teleport creature, then creature move left animation but no real movement    |
| 8          | MOVEMENTFLAG_STRAFE_RIGHT | instantly teleport creature, then creature move right animation but no real movement   |
| 16         | MOVEMENTFLAG_LEFT         | creature spin left animation                                                           |
| 32         | MOVEMENTFLAG_RIGHT        | then creature spin right animation                                                     |
| 64         | MOVEMENTFLAG_PITCH_UP     | no effect on creature                                                                  |
| 128        | MOVEMENTFLAG_PITCH_DOWN   | no effect on creature                                                                  |
| 256        | MOVEMENTFLAG_RUN_MODE     | If flag set then player runs                                                           |
| 512        | MOVEMENTFLAG_ONTRANSPORT  | causes creatures to fly while moving (not include standing)                            |
| 1024       | MOVEMENTFLAG_HOVERING     | hovering animation at stand (not include moving)                                       |
| 2048       | MOVEMENTFLAG_FLY_UNK1     |                                                                                        |
| 4096       | MOVEMENTFLAG_JUMPING      | Jump animation                                                                         |
| 8192       | MOVEMENTFLAG_UNK1         |                                                                                        |
| 16384      | MOVEMENTFLAG_FALLING      | Falling                                                                                |
| 32768      | MOVEMENTFLAG_UNK2         |                                                                                        |
| 65536      | MOVEMENTFLAG_UNK3         |                                                                                        |
| 131072     | MOVEMENTFLAG_UNK4         |                                                                                        |
| 262144     | MOVEMENTFLAG_UNK5         |                                                                                        |
| 524288     | MOVEMENTFLAG_UNK6         |                                                                                        |
| 1048576    | MOVEMENTFLAG_UNK7         | Causes creature to instantly appear at new position                                    |
| 2097152    | MOVEMENTFLAG_SWIMMING     | appears with fly flag also (causes creatures to fall to ground at stand state)         |
| 4194304    | MOVEMENTFLAG_FLY_UP       | no effect on creature                                                                  |
| 8388608    | MOVEMENTFLAG_CAN_FLY      | no effect on creature                                                                  |
| 16777216   | MOVEMENTFLAG_FLYING       | no effect on creature                                                                  |
| 33554432   | MOVEMENTFLAG_UNK8         | Creature flying (not hover at stop moving)                                             |
| 67108864   | MOVEMENTFLAG_SPLINE       | probably wrong name (no effect on creature)                                            |
| 134217728  | MOVEMENTFLAG_SPLINE2      | no effect on creature                                                                  |
| 268435456  | MOVEMENTFLAG_WATERWALKING | also prevent creature from falling under water                                         |
| 536870912  | MOVEMENTFLAG_SAFE_FALL    | active rogue safe fall spell (passive) (no effect on creature)                         |
| 1073741824 | MOVEMENTFLAG_UNK9         | Causes creature to hover at stand state (not include moving)                           |
| 2147483648 | MOVEMENTFLAG_UNK10        | Causes creature to roll to strange angle                                               |

<span style="color: red">Proper table as of 3.1</span>

| Bit        | Name                      | Comment                                                                                |
| ---------- | ------------------------- | -------------------------------------------------------------------------------------- |
| 0          | MONSTER_MOVE_NONE         | InhabitType]] and [MovementType](creature_template#MovementType)                       |
| 1          | MONSTER_MOVE_FORWARD      | Instantly teleport creature, then creature move forward animation but no real movement |
| 2          | MONSTER_MOVE_BACKWARD     | Instantly teleport creature, then creature move back animation but no real movement    |
| 4          | MONSTER_MOVE_STRAFE_LEFT  | Instantly teleport creature, then creature move left animation but no real movement    |
| 8          | MONSTER_MOVE_STRAFE_RIGHT | Instantly teleport creature, then creature move right animation but no real movement   |
| 16         | MONSTER_MOVE_LEFT         | Creature spin left animation                                                           |
| 32         | MONSTER_MOVE_RIGHT        | Then creature spin right animation                                                     |
| 64         | MONSTER_MOVE_PITCH_UP     | Seams to have no effect                                                                |
| 128        | MONSTER_MOVE_PITCH_DOWN   | Seams to have no effect                                                                |
| 256        | MONSTER_MOVE_TELEPORT     | Makes creature teleport instead of walking                                             |
| 512        | MONSTER_MOVE_TELEPORT2    | Makes creature a better Fly Animation (2.4.3)                                          |
| 1024       | MONSTER_MOVE_LEVITATING   |                                                                                        |
| 2048       | MONSTER_MOVE_UNK1         |                                                                                        |
| 4096       | MONSTER_MOVE_WALK         | Makes creature walk                                                                    |
| 8192       | MONSTER_MOVE_SPLINE       |                                                                                        |
| 16384      | No name in core           | Makes creature run                                                                     |
| 32768      | No name in core           | Makes creature run                                                                     |
| 65536      | No name in core           | Makes creature run                                                                     |
| 131072     | No name in core           | Makes creature run                                                                     |
| 262144     | MONSTER_MOVE_SPLINE2      |                                                                                        |
| 524288     | MONSTER_MOVE_UNK2         | Used for flying mobs                                                                   |
| 1048576    | MONSTER_MOVE_UNK3         | Used for flying mobs                                                                   |
| 2097152    | MONSTER_MOVE_UNK4         |                                                                                        |
| 4194304    | MONSTER_MOVE_UNK5         | Run in place, then teleport to final point                                             |
| 8388608    | MONSTER_MOVE_UNK6         | Teleport                                                                               |
| 16777216   | MONSTER_MOVE_UNK7         | Run                                                                                    |
| 33554432   | MONSTER_MOVE_FLY          | Swimming / Flying                                                                      |
| 67108864   | MONSTER_MOVE_UNK9         | Run                                                                                    |
| 134217728  | MONSTER_MOVE_UNK10        | Run                                                                                    |
| 268435456  | MONSTER_MOVE_UNK11        | Run                                                                                    |
| 536870912  | MONSTER_MOVE_UNK12        | Run                                                                                    |
| 1073741824 | MONSTER_MOVE_UNK13        | Levitating                                                                             |

Note: MONSTER\_MOVE\_SPLINE\_FLY = MONSTER\_MOVE\_WALK + MONSTER\_MOVE\_SPLINE and makes creature fly by points. Note2: Copy from Mangos

#### auras

This field controls any auras to be applied on the creature (both in effect and visually). To apply multiple auras, you can add more aura entries, separating each entry by a space.

List of useful aura entries:

-   '16380' - Makes the creature invisible.
-   '18950' - Makes the creature detect other invisible units (players or creatures).
-   '37613' - Casting teleport forever.
