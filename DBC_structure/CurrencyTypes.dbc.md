Back to "dbc files":dbc_files list.

h3. CurrencyTypes.dbc

This DBC contains all currency types a player can know and store.

*Version is : 3.2.2a*

h3. Structure


|*Field Nb*|*Name*|*Type*|
|1|ID|Int|
|2|ItemId|Int|
|3|Category|Int|
|4|BitIndex|Int|


h3. Content


|ID|*ItemId*|Category|*BitIndex*|
||
|1|37711|1|1|
|2|37742|1|2|
|42|29434|1|7|
|61|41596|1|8|
|81|43016|1|9|
|241|44990|1|25|
|103|43307|2|12|
|104|43308|2|13|
|121|20560|2|14|
|122|20559|2|15|
|123|29024|2|16|
|124|42425|2|17|
|125|20558|2|18|
|126|43589|2|19|
|161|43228|2|21|
|181|44209|2|22|
|201|37836|2|23|
|321|47395|2|28|
|4|38644|3|3|
|101|40752|22|10|
|102|40753|22|11|
|221|45624|22|24|
|301|47241|22|27|
|22|41749|24|5|
|141|43949|2089878896|20|


h3. Usage in MaNGOS

bc. struct CurrencyTypesEntry
{
    //uint32  ID;           // 0   not used
    uint32    ItemId;       // 1   used as real index
    //uint32  Category;     // 2   may be category
    uint32    BitIndex;     // 3   bit index in PLAYER_FIELD_KNOWN_CURRENCIES (1 << (index-1))
};

