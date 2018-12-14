### **The \`instance\_reset\` table**

This table hold information about instance reset time.

### **Structure**

| <strong>**Field**</strong>              | <strong>**Type**</strong> | <strong>**Null**</strong> | <strong>**Key**</strong> | <strong>**Default**</strong> |
|-----------------------------------------|---------------------------|---------------------------|--------------------------|------------------------------|
| [mapid](Instance_reset#mapid)           | int(11) unsigned          | NO                        | PRI                      | 0                            |
| [difficulty](Instance_reset#difficulty) | tinyint(1)                | NO                        |                          | 0                            |
| [resettime](Instance_reset#resettime)   | bigint(40) unsigned       | NO                        |                          | 0                            |
|                                         |                           |

### **Description of the fields**

mapid
-----

The map ID of the instance. See Map.dbc

difficulty
----------

Dungeon difficulty

resettime
---------

Dungeon reset time in seconds.
