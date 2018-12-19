Back to [world database](mangosdb_struct) list of tables.

The \`taxi\_shortcuts\` table
-----------------------------

This table contains information about shortcuts for taxi system to take when building long multi-route taxi flights.

### Structure

| **Field**                           | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-------------------------------------|------------------|----------|---------|-------------|-----------|
| [pathid](taxi_shortcuts#pathid)     | int(10) unsigned | NO       | PRI     | 0           |           |
| [takeoff](taxi_shortcuts#takeoff)   | int(10) unsigned | NO       |         | 0           |           |
| [landing](taxi_shortcuts#landing)   | int(10) unsigned | NO       |         | 0           |           |
| [comments](taxi_shortcuts#comments) | text             | NO       |         | ""          |           |

### Description of the fields

#### pathid

This is the id of the individual flight path from [TaxiPath.dbc](TaxiPath.dbc).

#### takeoff

This is length of the takeoff sequence of the taxi flight: amount of waypoints starting from the beginning.

#### landing

This is length of the landing sequence of the taxi flight: amount of waypoints starting from the end.

#### comments

This is the text containing hints about this particular flight path. It is useful to include destinations, faction (if same destinations are available in faction variants), and notes about origin of this shortcut.
Currently there are following origin markers used:

-   "... verified: type of the source":
    This shortcut is faithful to the source, no further alterations required.
-   "... extracted from verified":
    This shortcut was recontructed using similar nodes from verified shortcut, usually 100% faithful with no futher alterations required.
-   "... is approximate":
    No verified sources were provided, however there are similar nodes which require only minimal guesswork. Sometimes may differ from the original by 1 or 2 nodes. Needs to be verified against some reputable source.

