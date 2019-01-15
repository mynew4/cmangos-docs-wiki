# Bot Interaction

Your bots will interact with pretty much anything you do!

### Merchants

If you talk to a vendor, your bots will sell trash items, and tell you anything else they can sell.<br>
They will also buy what you tell them to buy.

### Quest Givers

If you talk to a questgiver, your bots know it, and watch to see if you take a quest.. if so they do too!

### Combat

If you fight they fight, if you take a taxi ... guess what?  They do too!
Of course they better have the cash and know the location your going to!

### Pets

Hunters will automatically feed their pets and keep them happy.

### Socialize

Bots will respond to you in tells, and other chat, as you interact with them.


Gameobject interaction with bots:
=================================

  The bot(s) can interact with gameobjects. This is particularly useful, in order to complete 'gather' type
  quests (e.g Milly's harvest in Northshire). The bot(s) can also harvest 'ore deposits' and 'herbs'

  Four commands have been introduced 'collect', 'survey, 'find' & 'get', to facilitate this feature.

  The 'collect' command provides a way to have a bot automatically get loot or objects in the world.
  The command by itself gives you a display of what settings the bots have. Defaults are stored in
  the playerbot.conf. The subcommands do the actual work:
    combat - bot will loot after combat for the options that are set
    loot - bot will grab all loot available from corpse
    quest - bot will grab all quest items on corpse
    profession - bot will grab any profession related item that the bot has from corpse
    skin - if you have skinning, and corpse has been looted, bot will skin corpse. Most of
        the time you may want this option and the loot option enabled, but if you are grabbing
        the stuff as you are going around, the bot will skin afterwards.
    objects - bot will collect things that are specified by the survey and get <shift-click> commands
    distance:<value> - bot will loot objects in the specified distance value
    none - removes any collect options that have been set

  The 'survey' command provides the means for bot(s) to detect gameobjects in the world. It can be used to detect
  available gameobjects local to a single bot, or more effectively (wider area) those for a party of bots.

  Suggestion: setup the 'survey' command as an assigned macro button, on the client (e.g /p survey). You can
  then quickly refresh the gameobject list.

  Gameobject list [GAMEOBJECT LINK] (Currently bots can only interact with ore, herb and needed quest items)
  ---------------

  `[Copper Vein][Silverleaf][Earthroot][Milly's Harvest][Battered Chest][Food Crate]`

  Then, use the 'find' or 'get' commands to interect with the gameobject.

  Using the gameobject list information, it is possible to locate and/or fetch each of the gameobjects. To select
  a [GAMEOBJECT LINK], hold down the shift key and click on the relevant link with your mouse.


Creature interaction with bots:
===============================

  The bot(s) can now interact directly with creatures. This will enable bot(s) to independently contact NPCs, without
  the need for player's selection. This opens up new possiblities for bot/NPC commerce.

  Each bot will maintain it's own item list (m_itemIds - This is a list of paired data). The first component (UNIT_NPC_FLAG)
  dictates what is to done with the second component (itemid).

  Each bot will also maintain it's own active auction list (m_auctions - This is a list of paired data). The first component
  (ActionFlags) dictates the action to be performed on the second component (auctionid).

  While(m_itemIds not empty)
  {
      bot will scan for surrounding creatures (findNearbyCreature()) who can service m_itemIds
      if(found)
          Search is carried out for all itemids that can be processed by this creature.
          if(processed successfully)
              This instance of the data pair (npcflag,itemid) will be removed from m_itemIds
              While(m_auctions not empty)
                  process contained auctionids according to ActionFlag & then update m_auctions
  }

  Please note that bot(s) m_itemIds & m_auctions will be emptied, when bot(s) are dismissed.

Repair with bots:
=================

  Bot can now repair <all or selected> items - equipped or in bags. If the bot is
  a member of a guild, then the guild fund is used for repairs. If not, the bots own
  gold supply is used. If the bot cannot pay for the repair, they remain damaged.

  The new 'stats' command provides useful information to help in the repair decision.

  First: Money available to bot(s)<br>
  Second: Free inventory slots for bot(s)<br>
  Third: Estimated (excludes NPC reputation discount) item damage cost for bot(s).

Trading with bots:
==================

To trade items/money with your bot simply initiate a trade and the bot will tell you how much money and items are available. To request an item simple whisper the bot and shift click the link of the item you would like. You can link multiple items on the same line. You can also request money in the following manner when the trade window is open:<br>
/w BOTNAME 10g <-- request that the bot give you 10 gold<br>
/w BOTNAME 6g500s25c <-- request 6 gold, 500 silver, and 25 copper

A bot is also able to show an item in its 'Will not be traded' slot. The item can be either
in its bags or be equipped and even be soulbound. Using this you can cast spells/enchantments
on soulbound items ('nt' stands for 'not trading').<br>
/w BOTNAME nt [Enchantable Soulbound Item]
