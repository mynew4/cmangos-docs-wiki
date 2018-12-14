Back to [world database](mangosdb_struct) list of tables.

The \`transports\` table
------------------------

This table contains all type 15 transports (Boats and Zeppelins). All other transport types have their frame time read from TransportAnimation.dbc.

### Structure

| **Field**                   | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------|------------------|----------|---------|-------------|-----------|
| [entry](Transports#entry)   | int(10) unsigned | NO       | PRI     | 0           |           |
| [name](Transports#name)     | text             | YES      |         | NULL        |           |
| [period](Transports#period) | int(10) unsigned | YES      |         | 0           |           |

### Description of the fields

#### entry

This is entry to be used for this transport from [gameobject\_template.entry](gameobject_template#entry). It must be a type 15 game object.

#### name

This is an arbitrary name that is only used to describe this transport entry.

#### period

This is the amount of time that it take for the transport to make one full pass through all the frames in TaxiNode.dbc. When a client change occurs, usually this field must be updated as Blizz changes the speeds of the transports on the official servers. The only known way to get this value is to ride the transports on the official servers and then tweak it until you get the proper value. This values in in milliseconds.
