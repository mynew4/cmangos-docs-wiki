Back to the characters database list of tables.

The \`character\_corpse\` table
-------------------------------

this table is used to store status of players corpse.

### Structure

| **Field**                          | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|------------------------------------|------------------|----------|---------|-------------|-----------|
| [guid](Corpse#guid)                | int(11) unsigned | NO       | PRI     | 0           |           |
| [player](Corpse#player)            | int(11) unsigned | NO       |         | 0           |           |
| [position\_x](Corpse#position_x)   | float            | NO       |         | 0           |           |
| [position\_](Corpse#position_y)    | float            | NO       |         | 0           |           |
| [position\_z](Corpse#position_z)   | float            | NO       |         | 0           |           |
| [orientation](Corpse#orientation)  | float            | NO       |         | 0           |           |
| [zone](Corpse#zone)                | int(11) unsigned | NO       |         | 0           |           |
| [map](Corpse#map)                  | int(11) unsigned | NO       |         | 0           |           |
| [data](Corpse#data)                | longtext         | YES      |         | 0           |           |
| [time](Corpse#time)                | bigint(20)       | NO       |         | 0           |           |
| [corpse\_type](Corpse#corpse_type) | tinyint(3)       | NO       |         | 0           |           |
| [instance](Corpse#instance)        | int(11) unsigned | NO       |         | 0           |           |

**Description of the fields**
