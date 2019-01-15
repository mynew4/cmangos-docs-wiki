Back to [characters database](charactersdb_struct) list of tables.

The \`arena\_team\` table
-------------------------

### Structure

| **Field**                                     | **Type**            | **Null** | **Key** | **Default** |
|-----------------------------------------------|---------------------|----------|---------|-------------|
| [arenateamid](Arena_team#arenateamid)         | int(10) unsigned    | NO       | PRI     | 0           |
| [name](Arena_team#name)                       | char(255)           | NO       |         |             |
| [captainguid](Arena_team#captainguid)         | int(10) unsigned    | NO       |         | 0           |
| [type](Arena_team#type)                       | tinyint(3) unsigned | NO       |         | 0           |
| [EmblemStyle](Arena_team#emblemstyle)         | int(10) unsigned    | NO       |         | 0           |
| [EmblemColor](Arena_team#emblemcolor)         | int(10) unsigned    | NO       |         | 0           |
| [BorderStyle](Arena_team#borderstyle)         | int(10) unsigned    | NO       |         | 0           |
| [BorderColor](Arena_team#bordercolor)         | int(10) unsigned    | NO       |         | 0           |
| [BackgroundColor](Arena_team#backgroundcolor) | int(10) unsigned    | NO       |         | 0           |

### Description of the fields

#### arenateamid

#### name

The name of the team

#### captainguid

The character global unique identifier of leader. View Characters.guid

#### type

0 = 2v2<br>
1 = 3v3<br>
2 = 5v5

#### EmblemStyle

#### EmblemColor

#### BorderStyle

#### BorderColor

#### BackgroundColor
