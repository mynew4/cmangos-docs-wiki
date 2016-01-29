Commits left over in backporting run from 1.09.2015

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/c60c9d3): c60c9d3 * xfurry (committer xfurry)
```
[12905] Allow spell effect 32 to trigger spells on unitTarget
```
* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/808cc1b): 808cc1b * xfurry (committer xfurry)
```
[12906] Implement spell effect 153 - Create Tamed Pet for Hunters
```
* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/8a6be23): 8a6be23 * Dehravor (committer stfx)
```
[12927] Fix showing trade cancelled message twice as client checks it as well
```
> Easily tested on client by checking if message is shown twice without this change

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/55813a4): 55813a4 * Shauren (committer stfx)
```
[12934] Second part of recent SendNotification trade packet improvement
```
> Depends on not yet backported code which needs to be checked if its needed

---
Backports which require additional testing and fixing:

[d94054](http://github.com/cmangos/mangos-tbc/commit/d94054abab9541586bf1fbecb6c8a3edb2a464e7)

[28c09b](http://github.com/cmangos/mangos-tbc/commit/28c09bce045722ccaab0a8c3765d8c22c4f0e792)

---
Commits which require research before backporting:

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/8953e34): 8953e34 * Schmoozerd (committer Schmoozerd)
```
[12483] Improvements for NPC summoning code
```
> SpellAttributes...

---
Commits left over in recent backport run:

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/771342e): 771342e * Schmoozerd (committer Schmoozerd)
```
[12483] Improvements for NPC summoning code
```
> WTF has happened here - the summoning changes are not properly backported..

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/4ece3ed): 4ece3ed * Shauren (committer stfx)
```
[12487] Improve alcohol handling
```
> Also for TBC this change? Depends on not backported code
> If it still works correctly after changes then yes since its better code

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/9d20ead): 9d20ead * Schmoozerd (committer Schmoozerd)
```
[12494] Fix SMSG_BINDPOINTUPDATE and SMSG_PLAYERBOUND sent data
```
> Does this spell require attributes?

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/659f65e): 659f65e * Schmoozerd (committer Schmoozerd)
```
[12505] Add and implement server-side spell 23770
```
***
Possible forgotten stuff:

https://github.com/cmangos/mangos-wotlk/commit/aa65a175298693499202429368514814d2a45d17 (for tbc spells)

https://github.com/cmangos/mangos-wotlk/commit/0390d28e3e17e3e9a6fc877c7ca4162fd413d756

Laise's spell changes:

https://github.com/cmangos/mangos-wotlk/commit/e7da1b0c9b065fb3e28d8792839b882c97799ea1

https://github.com/cmangos/mangos-wotlk/commit/76f8a24fa18600364479354b2c15b5f051ff9666

https://github.com/cmangos/mangos-wotlk/commit/dbcf0f3fc2932b4bf9d5df33987befef753c679b

https://github.com/cmangos/mangos-wotlk/commit/0cd64d0bae6272ea65e61b3662b1ceb986feb82c

https://github.com/cmangos/mangos-wotlk/commit/ce04030906d8af51bad6295f38ef1d1648af0266

https://github.com/cmangos/mangos-wotlk/commit/7027f52c35dba53075493adc84fcea4f415a0843

https://github.com/cmangos/mangos-wotlk/commit/f683e3cb007a678cb537b3d3d09d29ab32321e99

https://github.com/cmangos/mangos-wotlk/commit/0ca23d519518a328555b828150c3b6637b2fd995

https://github.com/cmangos/mangos-wotlk/commit/bf7744be754ea49e90dd8cd767c933f89b2f8014

https://github.com/cmangos/mangos-wotlk/commit/ad46ddcf239a2dd92d52c56275f7cabd94cd7f53

https://github.com/cmangos/mangos-wotlk/commit/a725f83946c7833e1e33015324a5c9e69b2f6bf1

https://github.com/cmangos/mangos-wotlk/commit/218a7d7d6ae180f6a6b1256e482061973ef3d188

https://github.com/cmangos/mangos-wotlk/commit/8496f6dadf947dfcae9571a25c41844745c0ab1b

> The first commit is actually the most problematic because it causes a conflict with https://github.com/cmangos/mangos-tbc/commit/a15c62a9b63e19b8b4a066034f2864c99fe8a5c9 - after that it should be easy though


TOM_RUS's SMSG_CAST_FAILED updates:
https://github.com/cmangos/mangos-wotlk/commit/8125239fcd643525f0997090c73ee4ef6067af3d


Older stuff noted by Vladimir:

	!+2f3c20ec14d386f1b784ef26fe6e76ba8ea03ac5 [8776] proper arena rating calculation
	!+ca88fc52a7e17148a91532cbbfd9ea55b41bc5a6 [8780] fixed typos with arenarating

	Need before for normal way move moveinfo to Unit, so manually recreate muster way work with movement info for creatures
	!+5eec80f67ff310aa9b8004da175b6bdb05d2f0cd [8880] Some adjustments/additions for updateflag_living and flying creatures
	!+60b1c604a656a322aaf702c61c8f180b219c5a3a [9210] Fix visual bug making npc run-in-same-position in client.
	* addd8b5ea59a544e0b672a01c0119cc388930581 Movement packets fix.
	* 5b0f7a88c180776cb58c76f9a78db0b1e6e11ffd Movement packets cleanup.
	* 986e5b76ae8758d8c895edce483c8cb84801c57d Get rid of monster movement flags, since it's really spline flags. Thanks to Ralek for research.
	!+404c8534283493c1dc9824343d9d91d1c3572808 [9335] Clarify error log message after rewrite of monster_* to spline_* flags
	* 33596e718b20b1302452901408f7de7b9e17e44d How this happened?
	* 93b2f8ff3966d7faa9f69cc1a75a58c9790f507c [10620] Fixed MSG_MOVE_HEARTBEAT structure. (need remove creature case)
	*+14c9042dedce2f19e73aa7e9f4ab4a694157b513 [10759] Correctly reset mob orientation upon reaching spawn point. Should also improve visualisation of mob orientation on clients
	*+17ffb949bfa3cd5dfcef2f77d9ffb3af1de7e31f [11149]*[unit moveinfo] Correct MSG_MOVE_SET_*_SPEED packet structures -> [11156] (need remove creature case)
	*+e49699eb025c5a791f322cf5278641cb9e4ca36c [11210]*[unit moveflags] Set moveflags from CMSG_MOVE_SET_CAN_FLY_ACK to proper mover.
	*+4c82c86e20c5abba0cdaed187f8951c15dde4f5b [11385] Add support for static vehicle spawns (movebuild part) ->[11386]
	*+003c56143cc39b5142cc5fcc27afdf6c56e5e006 [11386] Revert small unexpected change -_-
	*+1149a1034ab8c6fe86b2748a707c6dbe410eb2ba [11388] Don't add MOVEFLAG_ROOT in case creature has no moving state


	Need per spell check
	!+c646ed13fe95da0b0a37a158967a8909c6c0805b [9019] Add/update some hidden threat values for warrior/druid spells.
	!+90c01bdcba252f66d73d66d751134a15f9159404 [11036] Update some data in spell_threat, making use of the new parameters

	Unclear what do: 0.12 enum different from 3.x version but used numeric values fit to 3.x enums...
	!+1265a13f63ff20fa48a90fbf715754b124b3c28a [10031] Replace hard coded quest dialog status value with enum value

	Unclear how this must be in 2.x, all my expremeents fail
	!+b640a6de05b0c8ca6390b4e36a956ba2eb4f3eb6 [10955] Fixed MSG_PVP_LOG_DATA data prepering.

	Unclear how this must be in 2.x, have same structure without real usages
	+ f9530a5de076a0b9647e5102658df5c022e83f39 [11554] Add some "tail" data for SMSG_CAST_FAILED and SMSG_PET_CAST_FAILED

	! - need additional research
	* - backported (need recheck for possible reapply need)
	*+- need reapply in future after some not backported commit