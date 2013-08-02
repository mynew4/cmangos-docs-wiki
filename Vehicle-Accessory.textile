Back to "world database":mangosdb_struct list of tables.

h2. The `vehicle&#95;accessory` table

This table holds information about placing NPC's on other vehicle NPC's (Mounting NPC's on Vehicles) 

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"vehicle_entry":Vehicle_Entry#vehicle_entry|int(10) unsigned|NO|PRI|0||
|"seat":Seat#seat|mediumint(8) unsigned|NO|PRI|0||
|"accessory_entry":Accessory_Entry#accessory_entry|int(10)|NO||0||
|"comment":Comment#comment|float|NO||0||



h3. Description of the fields

h4. vehicle_entry

The Vehicle NPC entry from Creature_Template. This is the Vehicle NPC you want the other NPC to Mount.

h4. seat

This is the Seat # you would like the NPC to mount into (Valid Values are 0 -7)

h4. accessory_entry

This is the Creature_Template entry of the NPC you would like to mount the Vehicle NPC.

NOTE: This NPC Should NOT be spawned in the DB. The Core will Spawn It On The Vehicle as Required.

h4. comment

Description of Who is Mounting What NPC

