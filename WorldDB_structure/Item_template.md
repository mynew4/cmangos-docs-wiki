Back to [world database](mangosdb_struct) list of tables.

The \`item\_template\` table
----------------------------

Holds information on every item that exists in the game. All items are created from their template stored in this table.

### Structure

| **Field**                                                            | **Type**             | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------------------------------|----------------------|----------|---------|-------------|-----------|
| [entry](Item_template#entry)                                         | int(10) unsigned     | NO       | PRI     | 0           |           |
| [class](Item_template#class)                                         | tinyint(3) unsigned  | NO       |         | 0           |           |
| [subclass](Item_template#subclass)                                   | tinyint(3) unsigned  | NO       |         | 0           |           |
| [unk0](Item_template#unk0)                                           | int(10)              | NO       |         | -1          |           |
| [name](Item_template#name)                                           | varchar(255)         | NO       | MUL     |             |           |
| [displayid](Item_template#displayid)                                 | int(10) unsigned     | NO       |         | 0           |           |
| [Quality](Item_template#quality)                                     | tinyint(3) unsigned  | NO       |         | 0           |           |
| [Flags](Item_template#flags)                                         | int(10) unsigned     | NO       |         | 0           |           |
| [BuyCount](Item_template#buycount)                                   | tinyint(3) unsigned  | NO       |         | 1           |           |
| [BuyPrice](Item_template#buyprice)                                   | int(10) unsigned     | NO       |         | 0           |           |
| [SellPrice](Item_template#sellprice)                                 | int(10) unsigned     | NO       |         | 0           |           |
| [InventoryType](Item_template#inventorytype)                         | tinyint(3) unsigned  | NO       |         | 0           |           |
| [AllowableClass](Item_template#allowableclass)                       | mediumint(9)         | NO       |         | -1          |           |
| [AllowableRace](Item_template#allowablerace)                         | mediumint(9)         | NO       |         | -1          |           |
| [ItemLevel](Item_template#itemlevel)                                 | int(11) unsigned     | NO       |         | 0           |           |
| [RequiredLevel](Item_template#requiredlevel)                         | tinyint(3) unsigned  | NO       |         | 0           |           |
| [RequiredSkill](Item_template#requiredskill)                         | int(10) unsigned     | NO       |         | 0           |           |
| [RequiredSkillRank](Item_template#requiredskillrank)                 | int(10) unsigned     | NO       |         | 0           |           |
| [requiredspell](Item_template#requiredspell)                         | int(10) unsigned     | NO       |         | 0           |           |
| [requiredhonorrank](Item_template#requiredhonorrank)                 | int(10) unsigned     | NO       |         | 0           |           |
| [RequiredCityRank](Item_template#requiredcityrank)                   | int(10) unsigned     | NO       |         | 0           |           |
| [RequiredReputationFaction](Item_template#requiredreputationfaction) | int(10) unsigned     | NO       |         | 0           |           |
| [RequiredReputationRank](Item_template#requiredreputationrank)       | int(10) unsigned     | NO       |         | 0           |           |
| [maxcount](Item_template#maxcount)                                   | smallint(5) unsigned | NO       |         | 0           |           |
| [stackable](Item_template#stackable)                                 | smallint(5) unsigned | NO       |         | 0           |           |
| [ContainerSlots](Item_template#containerslots)                       | tinyint(3) unsigned  | NO       |         | 0           |           |
| [StatsCount](Item_template#statscount)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_type1](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value1](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type2](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value2](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type3](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value3](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type4](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value4](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type5](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value5](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type6](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value6](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type7](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value7](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type8](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value8](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type9](Item_template#stat_type)                               | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value9](Item_template#stat_value)                             | smallint(6)          | NO       |         | 0           |           |
| [stat\_type10](Item_template#stat_type)                              | tinyint(3) unsigned  | NO       |         | 0           |           |
| [stat\_value10](Item_template#stat_value)                            | smallint(6)          | NO       |         | 0           |           |
| [ScalingStatDistribution](Item_template#scalingstatdistribution)     | smallint(6)          | NO       |         | 0           |           |
| [ScalingStatValue](Item_template#scalingstatvalue)                   | smallint(6)          | NO       |         | 0           |           |
| [dmg\_min1](Item_template#dmg_min)                                   | float                | NO       |         | 0           |           |
| [dmg\_max1](Item_template#dmg_max)                                   | float                | NO       |         | 0           |           |
| [dmg\_type1](Item_template#dmg_type)                                 | tinyint(3) unsigned  | NO       |         | 0           |           |
| [dmg\_min2](Item_template#dmg_min)                                   | float                | NO       |         | 0           |           |
| [dmg\_max2](Item_template#dmg_max)                                   | float                | NO       |         | 0           |           |
| [dmg\_type2](Item_template#dmg_type)                                 | tinyint(3) unsigned  | NO       |         | 0           |           |
| [dmg\_min3](Item_template#dmg_min)                                   | float                | NO       |         | 0           |           |
| [dmg\_max3](Item_template#dmg_max)                                   | float                | NO       |         | 0           |           |
| [dmg\_type3](Item_template#dmg_type)                                 | tinyint(3) unsigned  | NO       |         | 0           |           |
| [dmg\_min4](Item_template#dmg_min)                                   | float                | NO       |         | 0           |           |
| [dmg\_max4](Item_template#dmg_max)                                   | float                | NO       |         | 0           |           |
| [dmg\_type4](Item_template#dmg_type)                                 | tinyint(3) unsigned  | NO       |         | 0           |           |
| [dmg\_min5](Item_template#dmg_min)                                   | float                | NO       |         | 0           |           |
| [dmg\_max5](Item_template#dmg_max)                                   | float                | NO       |         | 0           |           |
| [dmg\_type5](Item_template#dmg_type)                                 | tinyint(3) unsigned  | NO       |         | 0           |           |
| [armor](Item_template#armor)                                         | int(10) unsigned     | NO       |         | 0           |           |
| [holy\_res](Item_template#holy_res)                                  | int(10) unsigned     | NO       |         | 0           |           |
| [fire\_res](Item_template#fire_res)                                  | int(10) unsigned     | NO       |         | 0           |           |
| [nature\_res](Item_template#nature_res)                              | int(10) unsigned     | NO       |         | 0           |           |
| [frost\_res](Item_template#frost_res)                                | int(10) unsigned     | NO       |         | 0           |           |
| [shadow\_res](Item_template#shadow_res)                              | int(10) unsigned     | NO       |         | 0           |           |
| [arcane\_res](Item_template#arcane_res)                              | int(10) unsigned     | NO       |         | 0           |           |
| [delay](Item_template#delay)                                         | int(10) unsigned     | NO       |         | 1000        |           |
| [ammo\_type](Item_template#ammo_type)                                | int(10) unsigned     | NO       |         | 0           |           |
| [RangedModRange](Item_template#rangedmodrange)                       | float                | NO       |         | 0           |           |
| [spellid\_1](Item_template#spellid)                                  | int(10) unsigned     | NO       |         | 0           |           |
| [spelltrigger\_1](Item_template#spelltrigger)                        | int(10) unsigned     | NO       |         | 0           |           |
| [spellcharges\_1](Item_template#spellcharges)                        | int(11)              | NO       |         | 0           |           |
| [spellppmRate\_1](Item_template#spellppmrate)                        | float                | NO       |         | 0           |           |
| [spellcooldown\_1](Item_template#spellcooldown)                      | int(11)              | NO       |         | -1          |           |
| [spellcategory\_1](Item_template#spellcategory)                      | int(10) unsigned     | NO       |         | 0           |           |
| [spellcategorycooldown\_1](Item_template#spellcategorycooldown)      | int(11)              | NO       |         | -1          |           |
| [spellid\_2](Item_template#spellid)                                  | int(10) unsigned     | NO       |         | 0           |           |
| [spelltrigger\_2](Item_template#spelltrigger)                        | int(10) unsigned     | NO       |         | 0           |           |
| [spellcharges\_2](Item_template#spellcharges)                        | int(11)              | NO       |         | 0           |           |
| [spellppmRate\_2](Item_template#spellppmrate)                        | float                | NO       |         | 0           |           |
| [spellcooldown\_2](Item_template#spellcooldown)                      | int(11)              | NO       |         | -1          |           |
| [spellcategory\_2](Item_template#spellcategory)                      | int(10) unsigned     | NO       |         | 0           |           |
| [spellcategorycooldown\_2](Item_template#spellcategorycooldown)      | int(11)              | NO       |         | -1          |           |
| [spellid\_3](Item_template#spellid)                                  | int(10) unsigned     | NO       |         | 0           |           |
| [spelltrigger\_3](Item_template#spelltrigger)                        | int(10) unsigned     | NO       |         | 0           |           |
| [spellcharges\_3](Item_template#spellcharges)                        | int(11)              | NO       |         | 0           |           |
| [spellppmRate\_3](Item_template#spellppmrate)                        | float                | NO       |         | 0           |           |
| [spellcooldown\_3](Item_template#spellcooldown)                      | int(11)              | NO       |         | -1          |           |
| [spellcategory\_3](Item_template#spellcategory)                      | int(10) unsigned     | NO       |         | 0           |           |
| [spellcategorycooldown\_3](Item_template#spellcategorycooldown)      | int(11)              | NO       |         | -1          |           |
| [spellid\_4](Item_template#spellid)                                  | int(10) unsigned     | NO       |         | 0           |           |
| [spelltrigger\_4](Item_template#spelltrigger)                        | int(10) unsigned     | NO       |         | 0           |           |
| [spellcharges\_4](Item_template#spellcharges)                        | int(11)              | NO       |         | 0           |           |
| [spellppmRate\_4](Item_template#spellppmrate)                        | float                | NO       |         | 0           |           |
| [spellcooldown\_4](Item_template#spellcooldown)                      | int(11)              | NO       |         | -1          |           |
| [spellcategory\_4](Item_template#spellcategory)                      | int(10) unsigned     | NO       |         | 0           |           |
| [spellcategorycooldown\_4](Item_template#spellcategorycooldown)      | int(11)              | NO       |         | -1          |           |
| [spellid\_5](Item_template#spellid)                                  | int(10) unsigned     | NO       |         | 0           |           |
| [spelltrigger\_5](Item_template#spelltrigger)                        | int(10) unsigned     | NO       |         | 0           |           |
| [spellcharges\_5](Item_template#spellcharges)                        | int(11)              | NO       |         | 0           |           |
| [spellppmRate\_5](Item_template#spellppmrate)                        | float                | NO       |         | 0           |           |
| [spellcooldown\_5](Item_template#spellcooldown)                      | int(11)              | NO       |         | -1          |           |
| [spellcategory\_5](Item_template#spellcategory)                      | int(10) unsigned     | NO       |         | 0           |           |
| [spellcategorycooldown\_5](Item_template#spellcategorycooldown)      | int(11)              | NO       |         | -1          |           |
| [bonding](Item_template#bonding)                                     | tinyint(3) unsigned  | NO       |         | 0           |           |
| [description](Item_template#description)                             | varchar(255)         | NO       |         |             |           |
| [PageText](Item_template#pagetext)                                   | int(10) unsigned     | NO       |         | 0           |           |
| [LanguageID](Item_template#languageid)                               | int(10) unsigned     | NO       |         | 0           |           |
| [PageMaterial](Item_template#pagematerial)                           | int(10) unsigned     | NO       |         | 0           |           |
| [startquest](Item_template#startquest)                               | int(10) unsigned     | NO       |         | 0           |           |
| [lockid](Item_template#lockid)                                       | int(10) unsigned     | NO       |         | 0           |           |
| [Material](Item_template#material)                                   | int(11)              | NO       |         | 0           |           |
| [sheath](Item_template#sheath)                                       | int(10) unsigned     | NO       |         | 0           |           |
| [RandomProperty](Item_template#randomproperty)                       | int(10) unsigned     | NO       |         | 0           |           |
| [RandomSuffix](Item_template#randomsuffix)                           | int(10) unsigned     | NO       |         | 0           |           |
| [block](Item_template#block)                                         | int(10) unsigned     | NO       |         | 0           |           |
| [itemset](Item_template#itemset)                                     | int(10) unsigned     | NO       |         | 0           |           |
| [MaxDurability](Item_template#maxdurability)                         | int(10) unsigned     | NO       |         | 0           |           |
| [area](Item_template#area)                                           | int(10) unsigned     | NO       |         | 0           |           |
| [Map](Item_template#map)                                             | int(10)              | NO       |         | 0           |           |
| [BagFamily](Item_template#bagfamily)                                 | int(10)              | NO       |         | 0           |           |
| [TotemCategory](Item_template#totemcategory)                         | int(10)              | NO       |         | 0           |           |
| [socketColor\_1](Item_template#socketcolor)                          | int(10)              | NO       |         | 0           |           |
| [socketContent\_1](Item_template#socketcontent)                      | int(10)              | NO       |         | 0           |           |
| [socketColor\_2](Item_template#socketcolor)                          | int(10)              | NO       |         | 0           |           |
| [socketContent\_2](Item_template#socketcontent)                      | int(10)              | NO       |         | 0           |           |
| [socketColor\_3](Item_template#socketcolor)                          | int(10)              | NO       |         | 0           |           |
| [socketContent\_3](Item_template#socketcontent)                      | int(10)              | NO       |         | 0           |           |
| [socketBonus](Item_template#socketbonus)                             | int(10)              | NO       |         | 0           |           |
| [GemProperties](Item_template#gemproperties)                         | int(10)              | NO       |         | 0           |           |
| [RequiredDisenchantSkill](Item_template#requireddisenchantskill)     | int(10)              | NO       |         | -1          |           |
| [ArmorDamageModifier](Item_template#armordamagemodifier)             | float                | NO       |         | 0           |           |
| [ItemLimitCategory](Item_template#itemlimitcategory)                 | smallint(6)          | NO       |         | 0           |           |
| [ScriptName](Item_template#scriptname)                               | varchar(100)         | NO       |         |             |           |
| [DisenchantID](Item_template#disenchantid)                           | int(10) unsigned     | NO       |         | 0           |           |
| [FoodType](Item_template#foodtype)                                   | tinyint(3) unsigned  | NO       |         | 0           |           |
| [minMoneyLoot](Item_template#minmoneyloot)                           | int(11) unsigned     | NO       |         | 0           |           |
| [maxMoneyLoot](Item_template#maxmoneyloot)                           | int(11) unsigned     | NO       |         | 0           |           |
| [Duration](Item_template#duration)                                   | int(11)              | NO       |         | 0           |           |
| [ExtraFlags](Item_template#extraflags)                               | tinyint(3) unsigned  | NO       |         | 0           |           |

### Description of the fields

#### entry

The ID of the item. This ID is unique between all templates.

#### class

The class of the item:

| ID  | Name                |
|-----|---------------------|
| 0   | Consumable          |
| 1   | Container           |
| 2   | Weapon              |
| 3   | Gem                 |
| 4   | Armor               |
| 5   | Reagent             |
| 6   | Projectile          |
| 7   | Trade Goods         |
| 8   | Generic(OBSOLETE)   |
| 9   | Recipe              |
| 10  | Money(OBSOLETE)     |
| 11  | Quiver              |
| 12  | Quest               |
| 13  | Key                 |
| 14  | Permanent(OBSOLETE) |
| 15  | Miscellaneous       |
| 16  | Glyph               |

#### subclass

The subclass of the item. The following table lists all available subclass and class combinations and the subclass name.

| Class ID | Subclass ID | Subclass Name      | Comments                                              |
|----------|-------------|--------------------|-------------------------------------------------------|
| 0        | 0           | Consumable         | Usability in combat is decided by the spell assigned. |
| 0        | 1           | Potion             |                                                       |
| 0        | 2           | Elixir             |                                                       |
| 0        | 3           | Flask              |                                                       |
| 0        | 4           | Scroll             |                                                       |
| 0        | 5           | Food & Drink       |                                                       |
| 0        | 6           | Item Enhancement   |                                                       |
| 0        | 7           | Bandage            |                                                       |
| 0        | 8           | Other              |                                                       |
| 1        | 0           | Bag                |                                                       |
| 1        | 1           | Soul Bag           |                                                       |
| 1        | 2           | Herb Bag           |                                                       |
| 1        | 3           | Enchanting Bag     |                                                       |
| 1        | 4           | Engineering Bag    |                                                       |
| 1        | 5           | Gem Bag            |                                                       |
| 1        | 6           | Mining Bag         |                                                       |
| 1        | 7           | Leatherworking Bag |                                                       |
| 2        | 0           | Axe                | One handed                                            |
| 2        | 1           | Axe                | Two handed                                            |
| 2        | 2           | Bow                |                                                       |
| 2        | 3           | Gun                |                                                       |
| 2        | 4           | Mace               | One handed                                            |
| 2        | 5           | Mace               | Two handed                                            |
| 2        | 6           | Polearm            |                                                       |
| 2        | 7           | Sword              | One handed                                            |
| 2        | 8           | Sword              | Two handed                                            |
| 2        | 9           | Obsolete           |                                                       |
| 2        | 10          | Staff              |                                                       |
| 2        | 11          | Exotic             |                                                       |
| 2        | 12          | Exotic             |                                                       |
| 2        | 13          | Fist Weapon        |                                                       |
| 2        | 14          | Miscellaneous      | (Blacksmith Hammer, Mining Pick, etc.)                |
| 2        | 15          | Dagger             |                                                       |
| 2        | 16          | Thrown             |                                                       |
| 2        | 17          | Spear              |                                                       |
| 2        | 18          | Crossbow           |                                                       |
| 2        | 19          | Wand               |                                                       |
| 2        | 20          | Fishing Pole       |                                                       |
| 3        | 0           | Red                |                                                       |
| 3        | 1           | Blue               |                                                       |
| 3        | 2           | Yellow             |                                                       |
| 3        | 3           | Purple             |                                                       |
| 3        | 4           | Green              |                                                       |
| 3        | 5           | Orange             |                                                       |
| 3        | 6           | Meta               |                                                       |
| 3        | 7           | Simple             |                                                       |
| 3        | 8           | Prismatic          |                                                       |
| 4        | 0           | Miscellaneous      |                                                       |
| 4        | 1           | Cloth              |                                                       |
| 4        | 2           | Leather            |                                                       |
| 4        | 3           | Mail               |                                                       |
| 4        | 4           | Plate              |                                                       |
| 4        | 5           | Buckler(OBSOLETE)  |                                                       |
| 4        | 6           | Shield             |                                                       |
| 4        | 7           | Libram             |                                                       |
| 4        | 8           | Idol               |                                                       |
| 4        | 9           | Totem              |                                                       |
| 5        | 0           | Reagent            |                                                       |
| 6        | 0           | Wand(OBSOLETE)     |                                                       |
| 6        | 1           | Bolt(OBSOLETE)     |                                                       |
| 6        | 2           | Arrow              |                                                       |
| 6        | 3           | Bullet             |                                                       |
| 6        | 4           | Thrown(OBSOLETE)   |                                                       |
| 7        | 0           | Trade Goods        |                                                       |
| 7        | 1           | Parts              |                                                       |
| 7        | 2           | Explosives         |                                                       |
| 7        | 3           | Devices            |                                                       |
| 7        | 4           | Jewelcrafting      |                                                       |
| 7        | 5           | Cloth              |                                                       |
| 7        | 6           | Leather            |                                                       |
| 7        | 7           | Metal & Stone      |                                                       |
| 7        | 8           | Meat               |                                                       |
| 7        | 9           | Herb               |                                                       |
| 7        | 10          | Elemental          |                                                       |
| 7        | 11          | Other              |                                                       |
| 7        | 12          | Enchanting         |                                                       |
| 8        | 0           | Generic(OBSOLETE)  |                                                       |
| 9        | 0           | Book               |                                                       |
| 9        | 1           | Leatherworking     |                                                       |
| 9        | 2           | Tailoring          |                                                       |
| 9        | 3           | Engineering        |                                                       |
| 9        | 4           | Blacksmithing      |                                                       |
| 9        | 5           | Cooking            |                                                       |
| 9        | 6           | Alchemy            |                                                       |
| 9        | 7           | First Aid          |                                                       |
| 9        | 8           | Enchanting         |                                                       |
| 9        | 9           | Fishing            |                                                       |
| 9        | 10          | Jewelcrafting      |                                                       |
| 10       | 0           | Money(OBSOLETE)    |                                                       |
| 11       | 0           | Quiver(OBSOLETE)   |                                                       |
| 11       | 1           | Quiver(OBSOLETE)   |                                                       |
| 11       | 2           | Quiver             | Can hold arrows                                       |
| 11       | 3           | Ammo Pouch         | Can hold bullets                                      |
| 12       | 0           | Quest              |                                                       |
| 13       | 0           | Key                |                                                       |
| 13       | 1           | Lockpick           |                                                       |
| 14       | 0           | Permanent          |                                                       |
| 15       | 0           | Junk               |                                                       |
| 15       | 1           | Reagent            |                                                       |
| 15       | 2           | Pet                |                                                       |
| 15       | 3           | Holiday            |                                                       |
| 15       | 4           | Other              |                                                       |
| 15       | 5           | Mount              |                                                       |
| 16       | 1           | Warrior            |                                                       |
| 16       | 2           | Paladin            |                                                       |
| 16       | 3           | Hunter             |                                                       |
| 16       | 4           | Rogue              |                                                       |
| 16       | 5           | Priest             |                                                       |
| 16       | 6           | Death Knight       |                                                       |
| 16       | 7           | Shaman             |                                                       |
| 16       | 8           | Mage               |                                                       |
| 16       | 9           | Warlock            |                                                       |
| 16       | 11          | Druid              |                                                       |

#### unk0

#### name

The item's name that will be displayed.

#### displayid

The model ID of the item. Each model has its own icon assigned so this field controls both the model appearance and the icon.

#### Quality

The quality of the item:

| ID  | Color  | Quality   |
|-----|--------|-----------|
| 0   | Grey   | Poor      |
| 1   | White  | Common    |
| 2   | Green  | Uncommon  |
| 3   | Blue   | Rare      |
| 4   | Purple | Epic      |
| 5   | Orange | Legendary |
| 6   | Red    | Artifact  |

#### Flags

Bitmask field that contains flags that the item has on it. As all other such fields, just add the flags together to combine them. Possible flags are listed below.

<table>
<colgroup>
<col width="12%" />
<col width="87%" />
</colgroup>
<thead>
<tr class="header">
<th>Flag</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Soulbound</td>
</tr>
<tr class="even">
<td>2</td>
<td>Conjured</td>
</tr>
<tr class="odd">
<td>4</td>
<td>Lootable (can be opened by right-click)</td>
</tr>
<tr class="even">
<td>8</td>
<td>Wrapped</td>
</tr>
<tr class="odd">
<td>32</td>
<td>Totem</td>
</tr>
<tr class="even">
<td>64</td>
<td>Activatable with right-click</td>
</tr>
<tr class="odd">
<td>256</td>
<td>Wrapper</td>
</tr>
<tr class="even">
<td>1024</td>
<td>Gifts</td>
</tr>
<tr class="odd">
<td>2048</td>
<td>Item is party loot and can be looted by all</td>
</tr>
<tr class="even">
<td>8192</td>
<td>Charter (Arena or Guild)</td>
</tr>
<tr class="odd">
<td>32768</td>
<td>PvP reward item</td>
</tr>
<tr class="even">
<td>524288</td>
<td>Unique equipped (player can only have one equipped at the same time)</td>
</tr>
<tr class="odd">
<td>4194304</td>
<td>Throwable (for tooltip ingame)</td>
</tr>
<tr class="even">
<td>8388608</td>
<td>Special Use</td>
</tr>
</tbody>
</table>

#### BuyCount

The size of the item stack when sold by vendors. Also if a vendor has limited copies of this item available, everytime the vendor list is refreshed (See [npc\_vendor.incrtime](npc_vendor#incrtime)), the number of copies increases by this number.

#### BuyPrice

The price required to pay to buy this item from a vendor, in copper.

#### SellPrice

The price that the vendor will pay you for the item when you sell it and if it is possible to be sold, in copper. Put in 0 if the item cannot be sold to a vendor.

#### InventoryType

In what slot the item can be equipped.

| ID  | Slot Name     | ID  | Slot Name       |
|-----|---------------|-----|-----------------|
| 0   | Non equipable | 15  | Ranged          |
| 1   | Head          | 16  | Back            |
| 2   | Neck          | 17  | Two-Hand        |
| 3   | Shoulder      | 18  | Bag             |
| 4   | Shirt         | 19  | Tabard          |
| 5   | Chest         | 20  | Robe            |
| 6   | Waist         | 21  | Main hand       |
| 7   | Legs          | 22  | Off hand        |
| 8   | Feet          | 23  | Holdable (Tome) |
| 9   | Wrists        | 24  | Ammo            |
| 10  | Hands         | 25  | Thrown          |
| 11  | Finger        | 26  | Ranged right    |
| 12  | Trinket       | 27  | Quiver          |
| 13  | Weapon        | 28  | Relic           |
| 14  | Shield        |     |                 |

#### AllowableClass

Bitmask controlling which classes can use this item. Add ids together to combine class possibilities. Use -1 if all classes can use it.

#### AllowableRace

Bitmask controlling which races can use this item. Add ids together to combine race possibilities. Use -1 for all races.

#### ItemLevel

Base item level.

#### RequiredLevel

Required level the player has to be to use this item.

#### RequiredSkill

The skill required to use this item. See SkillLine.dbc

#### RequiredSkillRank

The required skill rank the player needs to have to use this item.

#### requiredspell

The required spell that the player needs to have to use this item.

#### requiredhonorrank

The honor rank the player needs to have to use this item.

#### RequiredCityRank

#### RequiredReputationFaction

The faction template ID (from [Faction.dbc](Faction.dbc)) of the faction that the player has to have a certain ranking with.

#### RequiredReputationRank

The rank the player has to have with the faction from [RequiredReputationFaction](#RequiredReputationFaction).

| ID  | Rank       |
|-----|------------|
| 0   | Hated      |
| 1   | Hostile    |
| 2   | Unfriendly |
| 3   | Neutral    |
| 4   | Friendly   |
| 5   | Honored    |
| 6   | Revered    |
| 7   | Exalted    |

#### maxcount

Maximum number of copies of this item a player can have. Use 0 for infinite.

#### stackable

The number of copies of this item that can be stacked in the same slot.

#### ContainerSlots

If the item is a bag, this field controls the number of slots the bag has.

#### StatsCount

The number of stats used for this item. Only the first n stats are used.

#### stat\_type

The type of stat to modify.

| ID  | Stat Type                              |
|-----|----------------------------------------|
| 0   | ITEM\_MOD\_MANA                        |
| 1   | ITEM\_MOD\_HEALTH                      |
| 3   | ITEM\_MOD\_AGILITY                     |
| 4   | ITEM\_MOD\_STRENGTH                    |
| 5   | ITEM\_MOD\_INTELLECT                   |
| 6   | ITEM\_MOD\_SPIRIT                      |
| 7   | ITEM\_MOD\_STAMINA                     |
| 12  | ITEM\_MOD\_DEFENSE\_SKILL\_RATING      |
| 13  | ITEM\_MOD\_DODGE\_RATING               |
| 14  | ITEM\_MOD\_PARRY\_RATING               |
| 15  | ITEM\_MOD\_BLOCK\_RATING               |
| 16  | ITEM\_MOD\_HIT\_MELEE\_RATING          |
| 17  | ITEM\_MOD\_HIT\_RANGED\_RATING         |
| 18  | ITEM\_MOD\_HIT\_SPELL\_RATING          |
| 19  | ITEM\_MOD\_CRIT\_MELEE\_RATING         |
| 20  | ITEM\_MOD\_CRIT\_RANGED\_RATING        |
| 21  | ITEM\_MOD\_CRIT\_SPELL\_RATING         |
| 22  | ITEM\_MOD\_HIT\_TAKEN\_MELEE\_RATING   |
| 23  | ITEM\_MOD\_HIT\_TAKEN\_RANGED\_RATING  |
| 24  | ITEM\_MOD\_HIT\_TAKEN\_SPELL\_RATING   |
| 25  | ITEM\_MOD\_CRIT\_TAKEN\_MELEE\_RATING  |
| 26  | ITEM\_MOD\_CRIT\_TAKEN\_RANGED\_RATING |
| 27  | ITEM\_MOD\_CRIT\_TAKEN\_SPELL\_RATING  |
| 28  | ITEM\_MOD\_HASTE\_MELEE\_RATING        |
| 29  | ITEM\_MOD\_HASTE\_RANGED\_RATING       |
| 30  | ITEM\_MOD\_HASTE\_SPELL\_RATING        |
| 31  | ITEM\_MOD\_HIT\_RATING                 |
| 32  | ITEM\_MOD\_CRIT\_RATING                |
| 33  | ITEM\_MOD\_HIT\_TAKEN\_RATING          |
| 34  | ITEM\_MOD\_CRIT\_TAKEN\_RATING         |
| 35  | ITEM\_MOD\_RESILIENCE\_RATING          |
| 36  | ITEM\_MOD\_HASTE\_RATING               |
| 37  | ITEM\_MOD\_EXPERTISE\_RATING           |

#### stat\_value

The value to change the stat type to.

#### dmg\_min

The minimum damage of the item.

#### dmg\_max

The maximum damage of the item.

#### dmg\_type

The damage type that the item uses.

| ID  | Damage Type |
|-----|-------------|
| 0   | Physical    |
| 1   | Holy        |
| 2   | Fire        |
| 3   | Nature      |
| 4   | Frost       |
| 5   | Shadow      |
| 6   | Arcane      |

#### armor

The armor value of the item.

#### holy\_res

Holy resistance.

#### fire\_res

Fire resistance.

#### nature\_res

Nature resistance.

#### frost\_res

Frost resistance.

#### shadow\_res

Shadow resistance.

#### arcane\_res

Arcane resistance.

#### delay

The time in milliseconds between successive hits.

#### ammo\_type

The type of ammunition the item uses. Arrows = 2; Bullets = 3

#### RangedModRange

#### spellid

The spell ID of the spell that the item can cast or trigger.

#### spelltrigger

The type of trigger for the spell.

| ID  | Trigger Type                      |
|-----|-----------------------------------|
| 0   | Use                               |
| 1   | On Equip                          |
| 2   | Chance on Hit                     |
| 4   | Soulstone                         |
| 5   | Use with no delay                 |
| 6   | Learn spell if spellid\_1 = 55884 |

#### spellcharges

The number of times that the item can cast the spell. If 0, then infinite charges are possible. If negative, then after the number of charges is depleted, the item is deleted as well. If positive, then the item is not deleted after all the charges are spent.

#### spellppmRate

The proc per minute rate controlling how often the spell is triggered (if [\#spelltrigger](#spelltrigger) == 2).

#### spellcooldown

The cooldown in milliseconds for the specific spell controlling how often the spell can be used. Use -1 to use the default spell cooldown.

#### spellcategory

The category that the spell is in.

#### spellcategorycooldown

The cooldown time in milliseconds that is applied to all other spells in the category that the triggered spell is also in. Use -1 to use the default spell cooldown.

#### bonding

The bonding for the item.

| ID  | Bonding Type         |
|-----|----------------------|
| 1   | Binds when picked up |
| 2   | Binds when equipped  |
| 3   | Binds when used      |
| 4   | Quest item           |

#### description

The description that appears in orange letters at the bottom of the item tooltip.

#### PageText

The ID referring to the text that the item will show (if it is a book or a letter, etc). The item will have a magnifying glass cursor in the game and will show the text when right-clicked. See [page\_text.entry](page_text#entry)

#### LanguageID

The language that the item text is written in.

#### PageMaterial

The background texture that appears in the page text window.

#### startquest

The ID of the quest that this item will start if right-clicked. See [quest\_template.entry](quest_template#entry)

#### lockid

The lock entry ID that this item (which serves as a key) is tied to. This field is used in key-door mechanics. See Lock.dbc

#### Material

The material that the item is made of. The value here affects the sound that the item makes when moved. Use -1 for consumable items like food, reagents, etc.

| ID  | Material |
|-----|----------|
| 1   | Metal    |
| 2   | Wood     |
| 3   | Liquid   |
| 4   | Jewelry  |
| 5   | Chain    |
| 6   | Plate    |
| 7   | Cloth    |
| 8   | Leather  |

#### sheath

Controls how the item is put away on the character (pressing the 'Z' hotkey).

| ID  | Type              | Position                                 |
|-----|-------------------|------------------------------------------|
| 1   | Two Handed Weapon | Diagonally across the back pointing down |
| 2   | Staff             | Diagonally across the back pointing up   |
| 3   | One Handed        | To the side                              |
| 4   | Shield            | On the back in the middle                |
| 5   | Enchanter's Rod   |                                          |
| 6   | Off hand          | On the other side of One Handed          |

#### RandomProperty

The number in this field points to [item\_enchantment\_template.entry](item_enchantment_template#entry) and ties in an item's chance at having a random property attached to it when it shows up for the first time. This field and the [RandomSuffix](#RandomSuffix) field CANNOT both have non-zero values. Either one is filled, or the other. Also, the primary source for the number in this field are WDBs.

#### RandomSuffix

The number in this field points to [item\_enchantment\_template.entry](item_enchantment_template#entry) and ties in an item's chance at having a random suffix attached to it when it shows up for the first time. This field and the [RandomProperty](#RandomProperty) field CANNOT both have non-zero values. Either one is filled, or the other. Also, the primary source for the number in this field are WDBs.

#### block

If the item is a shield, the block chance of the shield.

#### itemset

The ID of the item set that this item belongs to. To save you some time, you CAN NOT make up new item sets. Item sets are defined in ItemSet.dbc

#### MaxDurability

The maximum durability of this item.

#### area

The zone ID that this item can be used in.

#### Map

The map ID that this item can be used in.

#### BagFamily

If the item is a bag, this field is a bitmask controlling what types of items can be put in this bag. You can combine different types by adding up the bit numbers.

| ID   | Bag Family Mask         |
|------|-------------------------|
| 0    | None                    |
| 1    | Arrows                  |
| 2    | Bullets                 |
| 4    | Soul Shards             |
| 8    | Leatherworking Supplies |
| 32   | Herbs                   |
| 64   | Enchanting Supplies     |
| 128  | Engineering Supplies    |
| 256  | Keys                    |
| 512  | Gems                    |
| 1024 | Mining Supplies         |

#### TotemCategory

Corresponds to the ID in TotemCategory.dbc.

| ID  | Category Name           |
|-----|-------------------------|
| 1   | TC\_SKINNING\_SKIFE     |
| 2   | TC\_EARTH\_TOTEM        |
| 3   | TC\_AIR\_TOTEM          |
| 4   | TC\_FIRE\_TOTEM         |
| 5   | TC\_WATER\_TOTEM        |
| 6   | TC\_COPPER\_ROD         |
| 7   | TC\_SILVER\_ROD         |
| 8   | TC\_GOLDEN\_ROD         |
| 9   | TC\_TRUESILVER\_ROD     |
| 10  | TC\_ARCANITE\_ROD       |
| 11  | TC\_MINING\_PICK        |
| 12  | TC\_PHILOSOPHERS\_STONE |
| 13  | TC\_BLACKSMITH\_HAMMER  |
| 14  | TC\_ARCLIGHT\_SPANNER   |
| 15  | TC\_ GYROMATIC\_MA      |
| 21  | TC\_MASTER\_TOTEM       |
| 41  | TC\_FEL\_IRON\_ROD      |
| 62  | TC\_ADAMANTITE\_ROD     |
| 63  | TC\_ETERNIUM\_ROD       |

#### socketColor

The color of the socket that can be placed in this item.

| ID  | Color  |
|-----|--------|
| 1   | Meta   |
| 2   | Red    |
| 4   | Yellow |
| 8   | Blue   |

#### socketContent

#### socketBonus

#### GemProperties

The value here corresponds to the ID in GemProperties.dbc.

#### RequiredDisenchantSkill

The required proficiency in disenchanting that the player needs to have to be able to disenchant this item.

#### ArmorDamageModifier

#### ItemLimitCategory

#### ScriptName

The name of the script that the item should use. There is no 'internalitemhandler' or 'internalitemhanler' script so mangos will ignore any such values in this field.

#### DisenchantID

The disenchant loot template ID. See [disenchant\_loot\_template.entry](loot_template#entry)

#### FoodType

If this item is a food type item, this field defines what type of food it is for hunters who want to feed their pets. It controls in what diet this food item falls in.

NOTE: Raw meat and fish is not the same as regular meat and fish. It seems that the last two types of diets include grey "poor" types of food that players have no use for but some pets seem to be able to eat. Also, those food types appeared in TBC so most likely only TBC pets will have those types of diets.

| ID  | Type     |
|-----|----------|
| 1   | Meat     |
| 2   | Fish     |
| 3   | Cheese   |
| 4   | Bread    |
| 5   | Fungus   |
| 6   | Fruit    |
| 7   | Raw Meat |
| 8   | Raw Fish |

#### minMoneyLoot

If the item is a container that can contain money, then this field defines the minimum coinage held in this container, in copper.

#### maxMoneyLoot

If the item is a container that can contain money, then this field defines the maximum coinage held in this container, in copper.

#### Duration

The duration of the item in seconds. If positive, it is the duration measured in ingame time. If you need realtime duration then ExtraFlags = 2

#### ExtraFlags

| ID  | Type             |
|-----|------------------|
| 0   | None             |
| 1   | None Consumable  |
| 2   | Raltime Duration |


