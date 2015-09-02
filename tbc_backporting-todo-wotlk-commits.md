Commits left over in backporting run from 1.09.2015

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/f0ed1a7): f0ed1a7 * xfurry (committer xfurry)
```
[12904] Set positive effect for spells 58533 and 58552
```
* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/c60c9d3): c60c9d3 * xfurry (committer xfurry)
```
[12905] Allow spell effect 32 to trigger spells on unitTarget
```
* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/808cc1b): 808cc1b * xfurry (committer xfurry)
```
[12906] Implement spell effect 153 - Create Tamed Pet for Hunters
```
* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/addd971): addd971 * kaelima (committer stfx)
```
[12919] Wait proper time before arena/bg invitation window is removed
```
* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/8a6be23): 8a6be23 * Dehravor (committer stfx)
```
[12927] Fix showing trade cancelled message twice as client checks it as well
```
> Needs to be tested on client - quite easy to do

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/55813a4): 55813a4 * Shauren (committer stfx)
```
[12934] Second part of recent SendNotification trade packet improvement
```
> Depends on not yet backported code which needs to be checked

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/a1ffc9e): a1ffc9e * Cyberium (committer Cyberium)
```
[12935] Adding Visual Studio 2015 support
```
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

[Older commits outstanding](https://github.com/stfx/one/issues/1)

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

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/9d20ead): 9d20ead * Schmoozerd (committer Schmoozerd)
```
[12494] Fix SMSG_BINDPOINTUPDATE and SMSG_PLAYERBOUND sent data
```
> Does this spell require attributes?

* [wotlk](http://github.com/cmangos/mangos-wotlk/commit/659f65e): 659f65e * Schmoozerd (committer Schmoozerd)
```
[12505] Add and implement server-side spell 23770
```
