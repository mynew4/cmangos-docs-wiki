Back to [world database](mangosdb_struct) list of tables.

The \`db\_version\` table
-------------------------

This table contains the version of the DB in use. It is highly recommended to any repacker or any other team that is working on the database to update this field at any change made.

### Structure

| **Field**                                               | **Type**     | **Null** | **Key** | **Default** | **Extra** |
|---------------------------------------------------------|--------------|----------|---------|-------------|-----------|
| [version](Db_version#version)                           | varchar(120) | YES      |         | NULL        |           |
| [creature\_ai\_version](Db_version#creature_ai_version) | varchar(120) | YES      |         | NULL        |           |
| [cache\_id](Db_version#cache_id)                        | INT (10)     | YES      |         | 0           |           |

### Description of the fields

#### version

The version of the database that is in use. The contents of this field identifies the database name and version that is in use and is also displayed at mangos startup.
