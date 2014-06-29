h3. Event AI Tables

"creature_ai_scripts":creature_ai_scripts

"creature_ai_summons":creature_ai_summons

"creature_ai_texts":creature_ai_texts

h2. Summoning Table Introduction

This table is used to provide NPC support for an event using action *_32 = ACTION&#95;T&#95;SUMMON_* as one of its Actions. <em>To quote from the "_Event&#95;AI_":Event_AI page:</em>

* *32 = ACTION&#95;T&#95;SUMMON*: Summons a creature using the data specified in the separate summons table.
** Parameter 1: The creature template ID to be summoned. The value here needs to be a valid creature template ID.
** Parameter 2: The target type defining who the summoned creature will attack. The value in this field needs to be a valid target type as specified in the reference tables below. NOTE: Using target type 0 will cause the summoned creature to not attack anyone.
** Parameter 3: The summon ID from the eventai&#95;summons table controlling the position (and spawntime) where the summoned mob should be spawned at.

As we see from Parameter 3, this table will be controlling the arrival point of the NPC. If you wish for the NPC to spawn at the same point as the NPC spawning it, use *Action 12* instead of 32.

h3. Explaining the Fields of the Table

h4. id

This arbitrary value will be matched by the third parameter in the *32 = ACTION&#95;T&#95;SUMMON* Event Type. It does not need to be in solid descending order.

Tip: Be sure to start your first custom input at least 1,000 digits ahead of the latest entry when you first start editing this table. I.e. in a newly installed database that you plan on working with for the long term, if the last id value here is 9, start at 5000, not at 10. If your database gets an update, if you had started at 10, those values could be overwritten.

h4. position&#95;x

The *_X_* position of the NPC to be spawned. (Note that this will obviously take place on the same map that you and the NPC are on, so no Map number will be necessary here.)

h4. position&#95;y

The *_Y_* position of the NPC to be spawned.

h4. position&#95;z

The *_Y_* (height) position of the NPC to be spawned.

h4. orientation

The orientation of the NPC when it appears. It can be any value, (experiment as necessary) but here are some values already known:

This value is measured in "radians":http://en.wikipedia.org/wiki/Radian.

|_. Value|_. Direction|
|0|North|
|1.57|East|
|3.14|South|
|-1.57|West|


h4. spawntimesecs

(Requires an elaboration and confirmation) - Most likely the time for the NPC to disappear once it has been summoned, in MILIseconds.

h4. comment

The arbitrary string of text that you deposit into the table to describe the actions of this particular record in the table. The comment has no bearing on the table's effects other than your own ability to recognize what each record is doing.
