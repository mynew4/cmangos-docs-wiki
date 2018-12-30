Back to [dbc files](dbc_files) list.

### AreaGroup.dbc

This DBC stores IDs used in [AreaGroupId](Spell.dbc#spelldbc) in Spell.dbc and [AreaId](spell_template#areaid) in Spell\_template.

**Version is : 3.3.5a**

### **Structure**

| **Column** | **Name** | **Type** |
|------------|----------|----------|
| 1          | ID       | Integer  |
| 2          | Entry1   | iRefID   |
| 3          | Entry2   | iRefID   |
| 4          | Entry3   | iRefID   |
| 5          | Entry4   | iRefID   |
| 6          | Entry5   | iRefID   |
| 7          | Entry6   | iRefID   |
| 8          | Entry7   | iRefID   |

***
#### ID

[AreaId](spell_template#areaid) in Spell\_template uses this Id for specify the allowed areas for a successful cast.

#### Entry1-7

Entry ID's taken from [AreaTable.dbc](AreaTable.dbc#content)
Groups several small areas into one larger area or category.
