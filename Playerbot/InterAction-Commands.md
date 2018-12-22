# InterAction Commands

More commands... Great!

But they are useful! And with good macro skills, you can have most of your commands right at the click of a button.

Shortcuts:

c = cast

e = equip

u = use

### Commands

### Item/Object Manipulation

/t BOTNAME use [ITEM LINK] (use item on self. If item hold quest, it will be accepted. If inventory item is lootable, it 
will be looted)

/t BOTNAME use [ITEM LINK] TARGET (use item on selected unit)

/t BOTNAME use [ITEM LINK][EQUIPPED ITEM LINK] (use item on equipped item)

/t BOTNAME use [ITEM LINK][GAMEOBJECT LINK] (use item on gameobject )

/t BOTNAME equip [ITEM LINK]

/t BOTNAME get [GAMEOBJECT LINK] (bot will fetch the selected gameobject and then return to the player)

### Quest Commands

/t BOTNAME quest (Shows bot's current quests)

/t BOTNAME quest < add | a > [QUESTLINK] (Adds a quest)

/t BOTNAME quest < drop | d > [QUESTLINK] (Drop a quest)

/t BOTNAME quest < end | e > (Turns in a completed quest)

/t BOTNAME quest < end | e > (Turns in a completed quest)

/t BOTNAME quest < report | r > (bot reports all items, creatures or gameobjects needed to finish quests)

### Info Commands

/t BOTNAME stats (bot shows available money, free inventory space and estimated item repair costs)

/t BOTNAME survey (bot shows all available gameobjects, within a local perimeter around the bot)

/t BOTNAME find [GAMEOBJECT LINK] (bot will travel to the gameobject location and then wait)

### Vendor/Auction/Collection Commands

/t BOTNAME collect (shows collect subcommand options and current collect status)

/t BOTNAME sell [ITEM LINK] (bot will sell item(s) with nearest vendor)

/t BOTNAME buy [ITEM LINK] (bot buy item(s) from selected vendor)

/t BOTNAME drop [ITEM LINK] (bot will drop item immediately, permanently destroying it)

/t BOTNAME auction (bot will display all it's active owned auctions. Auction info will include an [AUCTION LINK] )

/t BOTNAME auction add [ITEM LINK] (bot will add item to it's m_itemIds, for later auction)

/t BOTNAME auction remove [AUCTION LINK] (bot will add auctionid to it's m_auctions, for later auction cancellation)

### You have MAIL !

/t BOTANME mail inbox [MAILBOX] (Lists all bot mail from selected [MAILBOX])

/t BOTNAME mail getcash [MAIL ID].. (gets all cash from selected [MAIL ID])

/t BOTNAME mail getitem [MAIL ID].. (gets all items from selected [MAIL ID])

/t BOTNAME mail delete [MAIL ID].. (delete all bot mail selected [MAIL ID])

### Repair Commands

/t BOTNAME repair [ITEM LINK] (bot will seek out armourer and repair selected items specified by [ITEM LINK] )

/t BOTNAME repair all (bot(s) will seek out armourer and repair all damaged items equipped, or in bags )

### You've got TaLENT !

/t BOTNAME talent (Lists bot(s) active talents [TALENT LINK] & glyphs [GLYPH LINK], unspent talent points & cost to reset all talents)

/t BOTNAME talent learn [TALENT LINK} .. (Learn selected talent from bot client 'inspect' dialog -> 'talent' tab or from talent command (shift click icon or link))

/t BOTNAME talent reset (Resets all talents)

/t BOTNAME talent spec (Lists talent specs available to this bot's class, with #, to use below)

/t BOTNAME talent spec # (If valid, uses this # talent spec for this bot (see # from talent spec above))

### Money in the Bank!

/t BOTNAME bank (Lists bot(s) bank balance)

/t BOTNAME bank deposit [Item Link][Item Link] .. (Deposit item(s) in bank)

/t BOTNAME bank withdraw [Item Link][Item Link] .. (Withdraw item(s) from bank. ([Item Link] from bank))

### Skill Commands

/t BOTNAME skill (lists all [PROFESSION LINK] bot Primary profession skills)

/t BOTNAME skill learn (lists [TRAINING LINK] available class, weapon & profession (Primary or Secondary) skills & spells, from selected trainer)

/t BOTNAME skill learn [TRAINING LINK] (learn selected skill or spell, from selected trainer)

/t BOTNAME skill unlearn [PROFESSION LINK] (unlearn selected primary profession skill & all associated spells)

