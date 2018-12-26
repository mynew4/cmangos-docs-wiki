Back to [world database](mangosdb_struct) list of tables.

The \`\*\_loot\_template\` tables
---------------------------------

General
-------

Well, according to vocabulary the meaning of the word "loot" is good for corpse loot and may be for some gameobjects like chests but quite unfit for fishing "loot". Nevermind. We will use term "loot" here as "a set of items generated on an event for a player" and "loot definition" as "a set of rules for loot generation". And forget about vocabulary for a while.

This table format is used for 11 different tables to generate different loot items for different things. The 11 tables are creature\_loot\_template, disenchant\_loot\_template, fishing\_loot\_template, gameobject\_loot\_template, item\_loot\_template, pickpocketing\_loot\_template, prospecting\_loot\_template, skinning\_loot\_template, mail\_loot\_template, reference\_loot\_template, milling\_loot\_template. The general description here is valid for all 11 because the loot system is the same for all eleven.

Loot templates define only items in the loot. See comments about money drop in corpse, pickpocketing and luggage loot in [creature\_template](creature_template) and [item\_template.](item_template).

Structure
---------

| **Field**                                                | **Type**           | **Null** | **Key** | **Default** | **Extra** |
|----------------------------------------------------------|--------------------|----------|---------|-------------|-----------|
| [entry](Loot_template#entry)                             | mediumint unsigned | NO       | PRI     | 0           |           |
| [item](Loot_template#item)                               | mediumint unsigned | NO       | PRI     | 0           |           |
| [ChanceOrQuestChance](Loot_template#chanceorquestchance) | float              | NO       |         | 100         |           |
| [groupid](Loot_template#groupid)                         | tinyint            | NO       |         | 0           |           |
| [mincountOrRef](Loot_template#mincountorref)             | mediumint          | NO       |         | 1           |           |
| [maxcount](Loot_template#maxcount)                       | tinyint unsigned   | NO       |         | 1           |           |
| [condition\_id](Loot_template#condition_id)              | mediumint(8)       | unsigned |         | NO          | 0         |

Relations
---------

The 11 tables have different relations with other DB tables.

| Loot table                  | Field                        | Relation                                                                   | Related table                              | Field                                                 | Comment                                                                                                                              |
| --------------------------- | ---------------------------- | -------------------------------------------------------------------------- | ------------------------------------------ | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| fishing_loot_template       | no relation                  | [entry](Loot_template#entry) is linked with ID of the fishing zone or area |                                            |                                                       |                                                                                                                                      |
| spell_loot_template         | no relation                  | [entry](Loot_template#entry) is linked with ID of the Spell.               |                                            |                                                       |                                                                                                                                      |
| creature_loot_template      | [entry](Loot_template#entry) | many <- many                                                               | [creature_template](Creature_template)     | [lootid](Creature_template#lootid)                    |                                                                                                                                      |
| gameobject_loot_template    | [entry](Loot_template#entry) | many <- many                                                               | [gameobject_template](Gameobject_template) | [data1](Gameobject_template#data0-23)                 | Only GAMEOBJECT_TYPE_CHEST (3) or GAMEOBJECT_TYPE_FISHINGHOLE (25) use data1 as loot ID, for other types data1 is used in other ways |
| item_loot_template          | [entry](Loot_template#entry) | many <- one                                                                | [item_template](Item_template)             | [entry](Item_template#entry)                          |                                                                                                                                      |
| disenchant_loot_template    | [entry](Loot_template#entry) | many <- many                                                               | [item_template](Item_template)             | [disenchantid](Item_template#disenchantid)            |                                                                                                                                      |
| prospecting_loot_template   | [entry](Loot_template#entry) | many <- one                                                                | [item_template](Item_template)             | [entry](Item_template#entry)                          |                                                                                                                                      |
| milling_loot_template       | [entry](Loot_template#entry) | many <- one                                                                | [item_template](Item_template)             | [entry](Item_template#entry)                          |                                                                                                                                      |
| pickpocketing_loot_template | [entry](Loot_template#entry) | many <- many                                                               | [creature_template](Creature_template)     | [pickpocketloot](Creature_template#pickpocketloot)    |                                                                                                                                      |
| skinning_loot_template      | [entry](Loot_template#entry) | many <- many                                                               | [creature_template](Creature_template)     | [skinloot](Creature_template#skinloot)                | Can also store minable/herbable items gathered from creatures                                                                        |
| mail_loot_template          | [entry](Loot_template#entry) |                                                                            | [quest_template](Quest_template)           | [RewMailTemplateId](Quest_template#rewmailtemplateid) | Send mail reward upon quest completion                                                                                               |
| reference_loot_template     | [entry](Loot_template#entry) | many <- many                                                               | * _loot_template                           | [-mincountOrRef](Loot_template#mincountorref)         | In case of negative mincountOrRef                                                                                                    |

Description of the fields
-------------------------

### entry

The ID of the loot definition (loot template). The rows with the same ID defines a single loot.
It is often the same ID as the loot source (item, creature, etc) but when the [link](#Relations) is made not on **entry** field of the Related table then ID can be different. For example, when several loot sources should provide the same loot, single loot definition can be used. In this case the loot sources have the same value in the link field.

It is possible also to set up **artificial loot templates** which are not used directly at all as they have ID which are not referenced from the related source. Such "support templates" can be [referenced](#Template_reference) from "normal" loot templates.

When a common or artificial loot template is used a problem arises: what ID to use for that template? Depending on the loot table, different rules can be agreed on to simplify maintenance for the table. Moreover, such rules would be very handy but it seems at the moment there are very few rules explicitly defined.

Agreements on **entry** field values are described [there](#Agreements).

### item

[Template ID](item_template#entry) of the item which can be included into the loot.

NOTE: For [reference entries](#mincountOrRef) this field has no meaning and not used by the core in any way. Yet because of the PRIMARY KEY on the entry + item combination, this field will nonetheless need to be a unique number for each reference entry so that no indexing conflicts arise.

### ChanceOrQuestChance

Meaning of that field is a bit different depending on its sign and the sign of [mincountOrRef](#mincountOrRef):

#### Plain entry

**ChanceOrQuestChance** > 0, [mincountOrRef](#mincountOrRef) > 0

Absolute value of **ChanceOrQuestChance** (actuallu just the value as it's positive in this case) signifies the percent chance that the item has to drop. Any floating point number is allowed but indeed any value larger that 100 will make the same result as 100.

#### Quest drop

**ChanceOrQuestChance** < 0, [mincountOrRef](#mincountOrRef) > 0

Just as for [plain entries](#Plain_entry) absolute value of **ChanceOrQuestChance** signifies the percent chance that the item has to drop. But in addition negative **ChanceOrQuestChance** informs the core that the item should be shown only to characters having appropriate quest. This means that even if item is dropped, in order to see it in the loot the player must have at least one [quest](quest_template) that has the [item ID](#item) in its [ReqItemIdN](quest_template#ReqItemId) fields or in its [ReqSourceIdN](quest_template#ReqSourceId) fields. The player must also have less copies of the item than [ReqItemCountN](quest_template#ReqItemCount) or [ReqSourceCountN](quest_template#ReqSourceCount).

#### Chanced references

[mincountOrRef](#mincountOrRef) < 0

For negative [mincountOrRef](#mincountOrRef) (*reference entries*) **ChanceOrQuestChance** signifies the percent chance that the reference has to be used. So it is very similar to [plain entries](#Plain_entry) meaning, just note that entire reference is skipped if the chance is missed.

Negative and zero values of **ChanceOrQuestChance** make no sense for that case and cannot be used.

#### Common remarks

Zero value of **ChanceOrQuestChance** is allowed for [grouped entries](#groupid) only.

(Non-zero) values of **ChanceOrQuestChance** in loot definition are multiplied by RATE\_DROP\_ITEMS (mangos config setting) during loot generation for references and non-reference entries, but not for grouped entries.

### groupid

A group is a set of loot definitions processed in such a way that at any given looting event the loot generated can receive only 1 (or none) [item](#item) from the items declared in the loot definitions of the group. Groups are formed by loot definitions having the same values of [entry](#entry) and **groupid** fields AND have **MinCountOrRef > 0**.

A group may consists of **explicitly-chanced** (having non-zero [ChanceOrQuestChance](#ChanceOrQuestChance)) and **equal-chanced** ([ChanceOrQuestChance](#ChanceOrQuestChance) = 0) entries. Every *equal-chanced* entry of a group is considered having such a chance that:

-   all equal-chanced entries have the same chance
-   **group chance** (sum of chances of all entries) is 100%

Of course group may consist of

-   only explicitly-chanced entries or
-   only equal-chanced entries or
-   entries of both type.

The easies way to understand what are groups is to understand how core processes grouped entries:

At loading time:

-   groups are formed - all grouped entries with the same values of **groupid** and **entry** fields are gathered into two sets - one for explicitly-chanced entries and one for equal-chanced. Note that order of entries in the sets can not be defined by DB - you should assume that the entries are in an unknown order. But indeed every time core processes a group the entries are in some order, constant during processing.

During loot generation:

-   core rolls for explicitly-chanced entries (if any):
    -   a random number **R** is rolled in range 0 to 100 (floating point value).
    -   chance to drop is checked for every (explicitly-chanced) entry in the group:
        -   if **R** is less than absolute value of [ChanceOrQuestChance](#ChanceOrQuestChance) of the entry then the entry 'wins': the [item](#item) is included in the loot. Group processing stops, the rest of group entries are just skipped.
        -   otherwise the entry 'looses': the [item](#item) misses its chance to get into the loot. **R** is decreased by the absolute value of [ChanceOrQuestChance](#ChanceOrQuestChance) and next explicitly-chanced entry is checked.
-   if none of explicitly-chanced entries got its chance then equal-chanced part (if any) is processed:
    -   a random entry is selected from the set of equal-chanced entries and corresponding [item](#item) is included in the loot.
-   If nothing selected yet (this never happens if the group has some equal-chanced entries) - no item from the group is included into the loot.

Let us use term **group chance** as the sum of [ChanceOrQuestChance](#ChanceOrQuestChance) (absolute) values for the group. Please note that even one equal-chanced entry makes group chance to be 100% (provided that sum of explicit chances does not exceed 100%).

If you understand the process you can understand the results:

-   Not more than one item from a group may drop at any given time.
-   If **group chance** is at least 100 then one item will be dropped for sure.
-   If *group chance* does not exceed 100 then every item defined in group entries has *exactly* that chance to drop as set in [ChanceOrQuestChance](#ChanceOrQuestChance).
-   If *group chance* is greater than 100 then some entries will lost a part of their chance (or even not be checked at all - that will be the case for all equal-chanced entries) whatever value takes the roll **R**. So for some items chance to drop will be less than their [ChanceOrQuestChance](#ChanceOrQuestChance). That is *very* bad and that is why having *group chance* > 100 is strictly prohibited.
-   Processing of *equal-chanced* part takes much less time then of *explicitly-chanced* one. So usage of equal-chanced groups is recommended when possible.

So now basic applications of the groups are clear:

-   Groups with *group chance* of 100% generate **exactly one** [item](#item) every time. This is needed quite often, for example such behavior is needed to define a loot template for tier item drop from a boss.
-   Groups with *group chance* < 100 generate **one or zero** [items](#item) every time keeping [chances](#ChanceOrRef) of every item unchanged. Such behavior is useful to limit maximum number of items in the loot.
-   A single group may be defined for a set of items common for several loot sources. This could be very useful for decreasing DB size without any loss of data. See [References](#Group_reference) for more details.

There is no way to have a [reference](#mincountOrRef) as a part of a group.

Note: A group may contain definitions of non-quest drop, quest drop or both, but mixing non-quest and quest drop in a single group is not recommended.

Note: The core has a limitation - only 16 non-quest items (money and items added into the loot for quests are not counted for this "16") may come into the loot. And this is not a caprice of core devs - the client has some constraints. As most of loots have much more than 16 possible items (sometimes several hundreds) so without groups there is a (little) chance that more than 16 items will be rolled for a given loot but player will be able to see (and take) only first 16 of them. With groups you can ensure that more than 16 items will *never* drop. If DB pretends to be a quality software it must have loot template definitions which ensure that not more than 16 plain entries and groups are defined for any loot template. This is just a note - such declaration is not issued by UDB developers yet.

Note: The core has no limitation for number of groups (except 255 by DB field size), but according to the previous note there is no need to use values greater than 16.

### mincountOrRef

This field defines

-   when positive: the minimum number of copies of the item that can drop in a single loot
-   when negative: a *reference* to another template.

Zero value makes no sense and should not be used.

Meaning of positive values is quite clear and requires no additional comments. *References* can point to either a whole template or to single group of a template and decribed below.

#### Template reference

[mincountOrRef](#mincountOrRef) < 0, [group](#groupid) = 0

Template reference asks core to process another loot template (having [entry](#entry) equal to "-mincountOrRef") and to include all items dropped for that template into current loot. Simple idea.

Value of [maxcount](#maxcount) field is used as a repetition factor for references - the reference will be processed not just once but exactly **maxcount** times. So if the referenced template can produce 3 to 10 items (depending on luck) and value of **maxcount** is '5' then after processing of that reference 15 to 50 items will be added to the loot. An awful example, isn't it? Actually no good example for whole template reference repetition is known, but it is quite useful for [group references](#Group_reference) sometimes.

Be careful. Self references (loot template includes reference to itself) and loop references (loot template A includes reference to entire template B, loot template B includes reference to entire template A) are *completely* different from [internal references](#Group_reference). If you make a self-reference like

`` INSERT INTO `creature_loot_template` (`entry`,`item`,`mincountOrRef`) VALUES ('21215','0','-21215'); ``

then the core will crash due to stack overflow at first attempt of loot 21215 processing. That is why **self references and loop references are strictly forbidden**.

#### Filtered references

[mincountOrRef](#mincountOrRef) < 0, [group](#groupid) > 0

Group reference asks core to process another loot template (having [entry](#entry) equal to "-mincountOrRef") only in the part of one [group](#groupid) - with id equal to value of \`groupid\` field of the reference entry. So this reference may add only none or 1 item into the loot (provided [maxcount](#maxcount) is equal to 1).

Meaning of [maxcount](#maxcount) field value is the same as described in [Template reference](#Template_reference).

Note that there is no way to have a [reference](#mincountOrRef) as a part of a group as such *grouped reference* would have the same format as *reference to group* described here.

There are two types of group references:

-   *external reference* when group reference row has **entry** different from **entry** of the referenced group
-   *internal reference* when group reference row has the same **entry** as the referenced group.

Basic usage of group references is to avoid repetition of group definitions when several loot sources have common parts of the loot. In this case it is possible:

-   to define groups with the same contents (items/drop chances) again and again. The simpliest way, but very RAM consumable.
-   to define the group once as a part of one of loot source loot definition and to include group references in loot definitions of the other loot sources instead of repeating group definition.
-   to define the group once as a part of an artificial loot definition (having **entry** not corresponding to any source) and to include group references in loot definitions for every related loot source.

The first way is deprecated, both second and third use *external references*. UDB recommends to use the third way.

As references have [chance](#ChanceOrQuestChance) to be processed it is possible to use them effiently for *zone* or *world* drop definitions. Those drops often have different chances for different loot sources (low/high skill gameobjects, non-elite/elite creatures etc) while having the same contents of the loot. The recommended way to define such drops is as following:

-   to set up a group with 100% [group chance](#groupid) in an artificial loot template (using [equal-chanced entries](#groupid) when possible)
-   to include references to that group into loot definition of every related loot source setting the drop chance for the reference.

Some bosses drop more than one tier item (two or three). Loot statistics looks like the same group is rolled 2 or 3 times and every time an item (possible the same) is chosen. It is simple to define a [group](#Grouped_entry) for single item, but how to define drop for the second and the third? We can:

-   repeat group definition 2 (or 3) times with change of group id
-   define the group once and include 1 (or 2) *internal references*.
-   define the group once as a part of an artificial loot definition and include 2 (or 3) *external* group references.
-   define the group once as a part of an artificial loot definition and include an *external* group reference with [repetition factor](#maxcount) of 2 (or 3).

The in-game results will be the same. But again - the first way is very inefficient and then deprecated. UDB recommends to use the forth way.

### maxcount

For non-reference entries - the maximum number of copies of the item that can drop in a single loot.

For [references](#Template_reference) value of **maxcount** field is used as a repetition factor for references - the reference will be processed not just once but exactly **maxcount** times. This is designed to serve a single purpose: to make definition of tier token drops a bit simplier (tokens of a tier are defined as a 100-chance group of an artificial template and bosses' loot templates include 100-chanced reference to that group with repetition factor of 2 or 3 depending on the case). Using non-1 repetition factor for other things (references to a group with *group chance* less than 100% or [chanced references](#Chanced_references) with chance less than 100%) must be agreed with UDB devs first (and described here).

Note: core rolls chance for any loot definition entry just one time - so if a references looses its chance it is skipped for the current loot completely whatever is **maxcount** value.

### condition\_id

Value that represents a [condition](Conditions#condition_entry) that must be met in order for the item to drop.
See [Conditions table](Conditions) for detailed description.

Note: For [reference entries](loot_template#mincountOrRef) only some conditions can be used

Agreements
----------

These agreements are different for different loot tables. Mainly agreements defines rules for loot template IDs ([entry](#entry)) and groups

### Fishing haul

For fishing\_loot\_template, ID is the zone or area ID from [AreaTable.dbc](AreaTable.dbc) (Note: Area IDs are not included in the link)

Also an extra note on fishing\_loot\_template: if just one area ID is defined for a zone, then that whole zone ID is skipped and therefore all areas in that zone need to have entries in the table. Only when there doesn't exist any area entries for a zone does the core use the zone ID directly. Zone = Wetlands, Elwynn, etc; Area = Northshire, Lakeshire, etc.

When several zones uses the same loot definition then

-   the loot template of the zone with minimal ID (minID) should be defined without references
-   the other zone with the same loot should have loot definition as a single [reference](#mincountOrRef) to the minID loot definition

Note: To be confirmed by UDB developers

As successful fishing should give exactly 1 fish (with an exception for quest fishes) so non-quest part of every loot template should be

-   or single [plain entry](#Plain_entry) with 100% drop chance
-   or a single group with [*group chance*](#groupid) equal to 100%
-   or a reference to a template made according to previous two variants. It is recommended to use [group references](#Group_reference).

When a fish is catched for a quest it becoms the *second* fish on the hook. Many people rolled on floor laughing but this is blizzlike and fortunately easy to implement. Just add necessary [quest drop](#Quest_drop) definition(s).

### Corpse loot

For creature\_loot\_template basic approach is to use [creature\_template.lootid](creature_template#lootid) equal to [creature\_template.entry](creature_template#entry). But this results in great overhead in the loot table as

-   many creatures use the same loot definition (well, stats on sites are *similar* due to the nature of random roll)
-   even more creatures use same parts of loot definition

That is why it is recommended to use [grouping](#groupid), [group references](#Group_reference) and [template references](#Template_reference).

### Disenchant outcome

Agreements for disenchant loot templates numbering is \*[item.level](item_template#level*100) + [item.quality](item_template#quality*) where **item** is disenchanting target.

As disenchanting should give exactly 1 type of shard/essence/dust/etc so every loot template should be

-   or single [plain entry](#Plain_entry) with 100% drop chance
-   or a single group with [*group chance*](#groupid) equal to 100%

There is no use for references here as the reference is done with the relation field. No quest drop at all.

### Gameobject harvest

***TBD***

### Luggage contents

***TBD***

### Pocket pick-ups

Agreements for pickpocketing loot templates numbering is not known.

***TBD***

### Prospecting outcome

Agreements for prospecting loot templates numbering is not known.

***TBD***

### Skinning pulls

Agreements for skinning loot templates numbering is not known. It's a real pity as many creatures should use the same templates. In most cases mobs with the same family and level have *very* similar skinning statistics.

As skinning should give exactly 1 type of skin/hide/etc so every loot template should be

-   or single [plain entry](#Plain_entry) with 100% drop chance
-   or single group with [*group chance*](#groupid) equal to 100%

There is no use for references here as the reference is done with the relation field.

When a skin is pulled for a quest it becoms the *second* skin from the mob. Yes, funny. This is blizzlike and fortunately easy to implement. Just add necessary [quest drop](#Quest_drop) definition(s).

Examples
--------

The example here mainly taken from current UDB (339) or from UDB forum. Often examples have several authors and it is uneasy to credit right people so: many thanks to ALL UDB devs and conributors.

But please note that some (or even all) example may contain incorrect data and are shown just for demostration of different loot data organisation.

### Simple examples

#### Gameobject dropping a single non-quest item

    # gameobject_template: entry=1622 name='Bruiseweed' type=3 data1=1419

    DELETE gameobject_loot_template WHERE entry=1419;
    INSERT INTO gameobject_loot_template
      (entry, item, ChanceOrRef, QuestChanceOrGroup, mincount, maxcount, freeforall, lootcondition, condition_value1, condition_value2)
    VALUES
      (1419, 2453, 100, 0, 1, 3, 0, 0, 0, 0);  # 100% drop a pile of 1 to 3 items [2453] 'Bruiseweed'

Taking into account default values of the table the second query could be simplified with no change of data (\`mincount\` is left on cosmetic reasons as \`maxcount\` has a non-default value):

    gameobject_template: entry=1622 name='Bruiseweed' type=3 data1=1419

    INSERT INTO gameobject_loot_template
      (entry, item, ChanceOrRef, mincount, maxcount)
    VALUES
      (1419, 2453, 100, 1, 3);  # 100% drop a pile of 1 to 3 items [2453] 'Bruiseweed'

#### Creature having in the pocket single quest item

    # creature_template: entry=6846, name='Defias Dockmaster', pickpocketloot=6846
    # Note: link with pickpocketing_loot_template is on `pickpocketloot` field (which is equal to `entry` field in this case)

    DELETE pickpocketing_loot_template WHERE entry=6846;

    INSERT INTO pickpocketing_loot_template
      (entry, item, ChanceOrRef, QuestChanceOrGroup, mincount, maxcount, freeforall, lootcondition, condition_value1, condition_value2)
    VALUES
      (6846, 7675, 0, 100, 1, 1, 0, 0, 0, 0);

Again, taking into account default values of the table the second query could be simplified with no change of data:

    INSERT INTO pickpocketing_loot_template
      (entry, item, ChanceOrRef, QuestChanceOrGroup)
    VALUES
      (6846, 7675, 0, 100);

Note that ChanceOrRef can not be skipped as it has default value of 100.

#### Wrong definition: combined quest and non-quest chances

    SELECT * FROM `pickpocketing_loot_template` WHERE `entry` = '20424';

| entry | item  | ChanceOrRef | QuestChanceOrGroup | mincount | maxcount | freeforall | lootcondition | condition_value1 | condition_value2 |
| ----- | ----- | ----------- | ------------------ | -------- | -------- | ---------- | ------------- | ---------------- | ---------------- |
| 20424 | 422   | 0.1         | 100                | 1        | 1        | 0          | 0             | 0                | 0                |
| 20424 | 929   | 0.1         | 100                | 1        | 1        | 0          | 0             | 0                | 0                |
| 20424 | 4538  | 0.1         | 100                | 1        | 1        | 0          | 0             | 0                | 0                |
| 20424 | 4542  | 0.1         | 100                | 1        | 1        | 0          | 0             | 0                | 0                |
| 20424 | 5374  | 0.1         | 100                | 1        | 1        | 0          | 0             | 0                | 0                |
| 20424 | 16882 | 22.2222     | 0                  | 1        | 1        | 0          | 0             | 0                | 0                |

First 5 rows in the result are incorrect, ChanceOrRef and QuestChanceOrGroup should not be positive simultanously. See [allowed combinations](#ChanceOrRef). The core does not crash encounering that, but non-quest chances are ignored.

### Groups

#### Simple skinning group

    SELECT * FROM `skinning_loot_template` WHERE `entry` = '100003';

gives

| entry  | item | ChanceOrRef | QuestChanceOrGroup | mincount | maxcount | freeforall | lootcondition | condition_value1 | condition_value2 |
| ------ | ---- | ----------- | ------------------ | -------- | -------- | ---------- | ------------- | ---------------- | ---------------- |
| 100003 | 8170 | 80          | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 100003 | 8171 | 20          | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |

Quite correct. Used quite widely:

    SELECT entry FROM `creature_template` WHERE `skinloot` = '100003';

gives

    659 2707 4242 4243 5347 5440 6582 6583 6648 7376 8024 8025 8204 8302 8303 8925 8932 9032 9297
    9521 9526 9527 10177 10204 10376 10596 10619 10717 10942 10979 10988 11181 11374 11671 11672
    11710 11740 11741 11885 11896 11897 11956 12124 12125 12803 13160 13178 13221 13618 13676 13916
    14283 14344 14476 14477 14566 14568 14732 14884 14943 14944 14945 14946 14947 14948 14965 14986
    14988 15041 15114 15172 15204 15220 15316 15338 15718

#### Almost correct skinning loot

    SELECT * FROM `skinning_loot_template` WHERE `entry` = '5292';

gives

| entry | item | ChanceOrRef | QuestChanceOrGroup | mincount | maxcount | freeforall | lootcondition | condition_value1 | condition_value2 |
| ----- | ---- | ----------- | ------------------ | -------- | -------- | ---------- | ------------- | ---------------- | ---------------- |
| 5292  | 4304 | 49.655      | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 5292  | 4234 | 43.1624     | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 5292  | 8169 | 4.0984      | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 5292  | 4235 | 3.0676      | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 5292  | 8973 | 0           | 80                 | 1        | 1        | 0          | 0             | 0                | 0                |

Quest entry and a group. Would be good if [group chance](#groupid) was 100, but it is only 99.9834. So on average at 166 skinning attempts over 1000 000 player will get an empty loot window (withuot considering quest skins which are very rare).

Used for creadure with entry=5292 only.

#### Damnly wrong skinning loot

    SELECT * FROM `skinning_loot_template` WHERE `entry` = '10151';

gives

| entry | item | ChanceOrRef | QuestChanceOrGroup | mincount | maxcount | freeforall | lootcondition | condition_value1 | condition_value2 |
| ----- | ---- | ----------- | ------------------ | -------- | -------- | ---------- | ------------- | ---------------- | ---------------- |
| 10151 | 8154 | 60          | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 10151 | 8170 | 48          | -1                 | 1        | 2        | 0          | 0             | 0                | 0                |
| 10151 | 4304 | 40          | -1                 | 1        | 2        | 0          | 0             | 0                | 0                |
| 10151 | 8368 | 5           | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 10151 | 8171 | 4           | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 10151 | 8169 | 3           | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |

    SELECT entry, name FROM `creature_template` WHERE `skinloot` = '10151';

gives

| entry | name      |
|-------|-----------|
| 11614 | Bloodshot |

First problem the [group chance](#groupid) is 160 that is much higher than 100. If by a case order of records in core (actually it is unknown) is such that chances of 60 and 40 are in the beginning then the rest of the group will never be processed. The result will be exacly the same is if the loot template was

| entry | item | ChanceOrRef | QuestChanceOrGroup | mincount | maxcount | freeforall | lootcondition | condition_value1 | condition_value2 |
| ----- | ---- | ----------- | ------------------ | -------- | -------- | ---------- | ------------- | ---------------- | ---------------- |
| 10151 | 8154 | 60          | -1                 | 1        | 1        | 0          | 0             | 0                | 0                |
| 10151 | 4304 | 40          | -1                 | 1        | 2        | 0          | 0             | 0                | 0                |

Moreover, skinloot in not equal to creature\_template.entry and this is NOT a reference to the same loot - 10151 is used ONLY by creature 11614. And the last problem - wowhead has no data about this skinning loot of this pet at all...
