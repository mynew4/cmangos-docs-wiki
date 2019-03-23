Back to [realm database](realmdb_struct) list of tables.

The \`realmlist\` table
-----------------------

This table sets up information on all available realms. Each row controls a different realm.

### Structure

| **Field**                                              | **Type**            | **Null** | **Key** | **Default** | **Extra**       |
|--------------------------------------------------------|---------------------|----------|---------|-------------|-----------------|
| [id](Realmlist#id)                                     | int(11) unsigned    | NO       | PRI     |             | auto\_increment |
| [name](Realmlist#name)                                 | varchar(32)         | NO       | UNI     |             |                 |
| [address](Realmlist#address)                           | varchar(32)         | NO       |         | 127.0.0.1   |                 |
| [port](Realmlist#port)                                 | int(11)             | NO       |         | 8085        |                 |
| [icon](Realmlist#icon)                                 | tinyint(3) unsigned | NO       |         | 0           |                 |
| [color](Realmlist#color)                               | tinyint(3) unsigned | NO       |         | 2           |                 |
| [timezone](Realmlist#timezone)                         | tinyint(3) unsigned | NO       |         | 0           |                 |
| [allowedSecurityLevel](Realmlist#allowedsecuritylevel) | tinyint(3) unsigned | NO       |         | 0           |                 |
| [population](Realmlist#population)                     | float unsigned      | NO       |         | 0           |                 |

### Description of the fields

#### id

The realm ID. This number is unique for every realm and it MUST correlate with the RealmID configuration value in mangosd.conf.

#### name

The name of the realm. This will appear in the realm selection list as well as in the character selection screen.

#### address

The public IP address of the world server. DO NOT use localhost or 127.0.0.1 in this field as this will cause a loop.

#### port

The port that the world server is running on. If all world servers are on the same machine, they will all need to use a different port.

#### icon

The icon of the realm.

| Icon | Type   |
|------|--------|
| 0    | Normal |
| 1    | PvP    |
| 4    | Normal |
| 6    | RP     |
| 8    | RP PvP |

#### color

The color denoting how "full" you want the realm to be displayed as.

#### timezone

The realm timezone, it will be displayed in the tabs of the realmlist

| timezone | displayed name |
|----------|----------------|
| 1        | Development    |
| 2        | United States  |
| 3        | Oceanic        |
| 4        | Latin America  |
| 5        | Tournament     |
| 6        | Korea          |
| 7        | Tournament     |
| 8        | English        |
| 9        | German         |
| 10       | French         |
| 11       | Spanish        |
| 12       | Russian        |
| 13       | Tournament     |
| 14       | Taiwan         |
| 15       | Tournament     |
| 16       | China          |
| 17       | CN1            |
| 18       | CN2            |
| 19       | CN3            |
| 20       | CN4            |
| 21       | CN5            |
| 22       | CN6            |
| 23       | CN7            |
| 24       | CN8            |
| 25       | Tournament     |
| 26       | Test Server    |
| 27       | Tournament     |
| 28       | QA Server      |
| 29       | CN9            |

#### allowedSecurityLevel

The minimum account [gmlevel](account#gmlevel) required for accounts to log in to this realm.

#### population

This field is automatically updated at regular intervals and will have the current population. The formula to calculate the value in this field is: playerCount / maxPlayerCount \* 2. In the realm list in-game, the thresholds for low, medium, and high population are 0.5, 1.0, and 2.0 respectively.

Back to [realm database](realmdb_struct) list of tables.
