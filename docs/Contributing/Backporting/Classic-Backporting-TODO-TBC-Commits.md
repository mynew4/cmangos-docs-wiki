This has no application in classic content. Keep it here as reference in case it was needed to get code in sync!
TBC(cleaned)_COMMIT 237f9ab  by VladimirMangos (commiter TheLuda)
```
 [s1326] Implement in proper way ITEM_SPELLTRIGGER_ON_STORE (5)
```
DestroyItemWithOnStoreSpell does not exist in Classic - Missing another backport?
TBC(cleaned)_COMMIT 6605f7a  by VladimirMangos (commiter TheLuda)

```
 [s1327] More consitence use m_target for DestroyItemWithOnStoreSpell call in aura.
```
Xfurry: not sure if the following is required
[tbc](http://github.com/cmangos/mangos-tbc/commit/aace559): aace559 * virusav (committer Salja)
```
[s1457] Remove check for quest_template if QuestSort and SkillId match
```
***

> Xfurry: Transporter commits - require additional research
stfx: Could only think of being used for pets so that they dont fall off the transport when it starts moving - but its impossible to say without npc-on-transport being finished

* [tbc](http://github.com/cmangos/mangos-tbc/commit/252e045): 252e045 * kid10 (committer stfx)
```
[s1685] Implement abstract classes for transporter
```
* [tbc](http://github.com/cmangos/mangos-tbc/commit/1c71e40): 1c71e40 * kid10 (committer stfx)
```
[s1686] Add a TransportInfo class to WorldObjects
```
* [tbc](http://github.com/cmangos/mangos-tbc/commit/ffd46e6): ffd46e6 * kid10 (committer Xfurry)
```
[s1734] Add abstract Board/Unboard Passenger functions to TransportBase
```
* [tbc](http://github.com/cmangos/mangos-tbc/commit/b8e5466): b8e5466 * evil-at-wow (committer Xfurry)
```
Fix build on Linux/GCC): hash_map's 'erase' member takes an iterator, so passing it a const_iterator is a no go.
```
End of transporter commits

***

> Xfurry: Disengage commits - not sure if apply to classic

* [tbc](http://github.com/cmangos/mangos-tbc/commit/55d1fb6): 55d1fb6 * Den (committer Xfurry)
```
[s1768] Fix Spell::CheckCast for Disengage
```
* [tbc](http://github.com/cmangos/mangos-tbc/commit/bd5ce36): bd5ce36 * rsa (committer Xfurry)
```
[s1771] Make check for Disengange like spells of [12215] more generic
```
* [tbc](http://github.com/cmangos/mangos-tbc/commit/254f1a0): 254f1a0 * Schmoozerd (committer Xfurry)
```
[s1828] Use SpellFocus check for all Spells
```
> stfx: That might work, needs to be tested if it doesnt cause issue

End of other misc commits

***