Back to [world database](mangosdb_struct) list of tables.

The \`vehicle\_accessory\` table
--------------------------------

This table holds information about placing NPC's on other vehicle NPC's (Mounting NPC's on Vehicles)

### Structure

| **Field**                                           | **Type**              | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------------|-----------------------|----------|---------|-------------|-----------|
| [vehicle\_entry](Vehicle_Entry#vehicle_entry)       | int(10) unsigned      | NO       | PRI     | 0           |           |
| [seat](Seat#seat)                                   | mediumint(8) unsigned | NO       | PRI     | 0           |           |
| [accessory\_entry](Accessory_Entry#accessory_entry) | int(10)               | NO       |         | 0           |           |
| [comment](Comment#comment)                          | float                 | NO       |         | 0           |           |

### Description of the fields

#### vehicle\_entry

The Vehicle NPC entry from Creature\_Template. This is the Vehicle NPC you want the other NPC to Mount.

#### seat

This is the Seat \# you would like the NPC to mount into (Valid Values are 0 -7)

#### accessory\_entry

This is the Creature\_Template entry of the NPC you would like to mount the Vehicle NPC.

NOTE: This NPC Should NOT be spawned in the DB. The Core will Spawn It On The Vehicle as Required.

#### comment

Description of Who is Mounting What NPC
