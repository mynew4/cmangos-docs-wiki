Back to [world database](mangosdb_struct) list of tables.

The \`game\_event\` table
-------------------------

This table is contains definitions for all game events that are activated or deactivated automatically by the Game Event System in the core.

### Structure

| **Field**                             | **Type**              | **Null** | **Key** | **Default**         | **Extra** |
|---------------------------------------|-----------------------|----------|---------|---------------------|-----------|
| [entry](Game_event#entry)             | mediumint(8) unsigned | NO       | PRI     |                     |           |
| [start\_time](Game_event#start_time)  | timestamp             | NO       |         | 0000-00-00 00:00:00 |           |
| [end\_time](Game_event#end_time)      | timestamp             | NO       |         | 0000-00-00 00:00:00 |           |
| [occurence](Game_event#occurence)     | bigint(20) unsigned   | NO       |         | 5184000             |           |
| [holiday](Game_event#holiday)         | mediumint(8) unsigned | NO       |         | 0                   |           |
| [linkedTo](Game_event#linkedTo)       | mediumint(8) unsigned | NO       |         | 0                   |           |
| [EventGroup](Game_event#EventGroup)   | mediumint(8) unsigned | NO       |         | 0                   |           |
| [description](Game_event#description) | varchar(255)          | YES      |         | None                |           |

### Description of the fields

#### entry

Entry of the event. Keep it as low as possible and prevent making holes in the list. Higher the max id is, the more memory will be used to store the event data.

#### start\_time

Absolute start date of the event. The event will start occurring only if the local time at the server is after the one set here.

#### end\_time

Absolute end date of the event. The event will stop occurring if the local time at the server is after the one set here.

#### occurence

Number of minutes between 2 occurrences of the event. (2880 = 2 days, 1440 = 1 day, etc)

#### length

Number of minutes the event will last after the start of the occurrence. (2880 = 2 days, 1440 = 1 day, etc) This value must be lower than occurrence one or the event will never stop.

#### holiday

Holiday ID from enum HolidayIds in SharedDefines.h

#### linkedTo

Linked event which must be active for this event to be able to be activated.

#### EventGroup

Group of events, which are launched automatically daily(length=1440) or weekly(length=10080).

#### description

String containing the name of the event displayed in console each time it starts or stops.
