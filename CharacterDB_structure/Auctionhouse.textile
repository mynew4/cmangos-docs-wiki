Back to the "characters database":charactersdb_struct list of tables.

h2. The `auctionhouse` table

Contains all information about the currently ongoing auctions in the auction houses. It controls what items are put up for auction and who put it up, who is the highest bidder, etc.

This table is used by MaNGOS while running and not a table that you would usually edit.

h3. Structure


|*Field*|*Type*|*Null*|*Key*|*Default*|*Extra*|
|"id":Auctionhouse#id|int(11) unsigned|NO|PRI|0||
|"auctioneerguid":Auctionhouse#auctioneerguid|int(11) unsigned|NO||0||
|"itemguid":Auctionhouse#itemguid|int(11) unsigned|NO||0||
|"item_template":Auctionhouse#item_template|int(11) unsigned|NO||0||
|"itemowner":Auctionhouse#itemowner|int(11) unsigned|NO||0||
|"buyoutprice":Auctionhouse#buyoutprice|int(11)|NO||0||
|"time":Auctionhouse#time|bigint(40)|NO||0||
|"buyguid":Auctionhouse#buyguid|int(11) unsigned|NO||0||
|"lastbid":Auctionhouse#lastbid|int(11)|NO||0||
|"startbid":Auctionhouse#startbid|int(11)|NO||0||
|"deposit":Auctionhouse#deposit|int(11)|NO||0||


h3. Description of the fields

h4. id

Unique identifier for every auction.

h4. auctioneerguid

The GUID of the creature where the auction item was added. See "creature.guid":creature#guid

h4. itemguid

The GUID of the item that is up for auction. See "item&#95;instance.guid":item_instance#guid

h4. item&#95;template

The entry of the item up for auction. See "item&#95;template.entry":item_template#entry

h4. itemowner

The GUID of the owner of the item up for auction. See "character.guid":character#guid

h4. buyoutprice

The buyout price of the item in copper. Divide by 100 to get silver and by 100 again to get gold.

h4. time

The time when the auction will end, measured in "Unix time":http://en.wikipedia.org/wiki/Unix_time (number of seconds from 00:00 Jan 1, 1970).

h4. buyguid

The GUID of the highest bidder. See "character.guid":character#guid

h4. lastbid

The amount of copper of the last bid put on the item.

h4. startbid

The amount of copper of the starting bid.

h4. deposit

The amount of copper spent on the deposit.
