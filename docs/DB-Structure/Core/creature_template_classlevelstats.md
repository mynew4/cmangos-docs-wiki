This table contains 6 - 10 fields (classic - wrath);
- `BaseHealthExp?` (0 - 2)
- `BaseMana`
- `BaseDamageExp?` (0 - 2)
- `BaseMeleeAttackPower`
- `BaseRangedAttackPower`
- `BaseArmor`

You access them in the core by using;

Classic: `sObjectMgr.GetCreatureClassLvlStats(level, cInfo->UnitClass)`
TBC/Wrath: `sObjectMgr.GetCreatureClassLvlStats(level, cInfo->UnitClass, cInfo->Expansion)`

( cInfo = `GetCreatureInfo()`)

And are included in the following formulas:

- Min Melee/Ranged damage:

`(BaseDamage * cInfo->DamageVariance + (Base?AttackPower / 14) * (?BaseAttackTime/1000)) * Info->DamageMultiplier`

( Max Melee/Ranged damage: `minDmg * 1.5` )

- Armor/(Min/Max Level Health/Mana):

 `Base? * ?Multiplier`