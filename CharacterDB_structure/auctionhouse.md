Back to the [characters database](charactersdb_struct) list of tables.

The \`auctionhouse\` table
--------------------------

Contains all information about the currently ongoing auctions in the auction houses. It controls what items are put up for auction and who put it up, who is the highest bidder, etc.

This table is used by MaNGOS while running and not a table that you would usually edit.

### Structure

| **Field**                                     | **Type**         | **Null** | **Key** | **Default** | **Extra** |
|-----------------------------------------------|------------------|----------|---------|-------------|-----------|
| [id](Auctionhouse#id)                         | int(11) unsigned | NO       | PRI     | 0           |           |
| [auctioneerguid](Auctionhouse#auctioneerguid) | int(11) unsigned | NO       |         | 0           |           |
| [itemguid](Auctionhouse#itemguid)             | int(11) unsigned | NO       |         | 0           |           |
| [item\_template](Auctionhouse#item_template)  | int(11) unsigned | NO       |         | 0           |           |
| [itemowner](Auctionhouse#itemowner)           | int(11) unsigned | NO       |         | 0           |           |
| [buyoutprice](Auctionhouse#buyoutprice)       | int(11)          | NO       |         | 0           |           |
| [time](Auctionhouse#time)                     | bigint(40)       | NO       |         | 0           |           |
| [buyguid](Auctionhouse#buyguid)               | int(11) unsigned | NO       |         | 0           |           |
| [lastbid](Auctionhouse#lastbid)               | int(11)          | NO       |         | 0           |           |
| [startbid](Auctionhouse#startbid)             | int(11)          | NO       |         | 0           |           |
| [deposit](Auctionhouse#deposit)               | int(11)          | NO       |         | 0           |           |

### Description of the fields

#### id

Unique identifier for every auction.

#### auctioneerguid

The GUID of the creature where the auction item was added. See [creature.guid](creature#guid)

#### itemguid

The GUID of the item that is up for auction. See [item\_instance.guid](item_instance#guid)

#### item\_template

The entry of the item up for auction. See [item\_template.entry](item_template#entry)

#### itemowner

The GUID of the owner of the item up for auction. See [characters.guid](characters#guid)

#### buyoutprice

The buyout price of the item in copper. Divide by 100 to get silver and by 100 again to get gold.

#### time

The time when the auction will end, measured in [Unix time](http://en.wikipedia.org/wiki/Unix_time) (number of seconds from 00:00 Jan 1, 1970).

#### buyguid

The GUID of the highest bidder. See [characters.guid](characters#guid)

#### lastbid

The amount of copper of the last bid put on the item.

#### startbid

The amount of copper of the starting bid.

#### deposit

The amount of copper spent on the deposit.
