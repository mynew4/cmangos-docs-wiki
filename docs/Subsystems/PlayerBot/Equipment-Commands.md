Bot Equipment Commands
======================

Shortcuts:

e = equip


Some commands deal with your bots' items or equipment.

/t BOTNAME equip [ITEM LINK]

/t BOTNAME sell [ITEM LINK] (bot will sell item(s) with nearest vendor)
/t BOTNAME buy [ITEM LINK] (bot buy item(s) from selected vendor)
/t BOTNAME drop [ITEM LINK] (bot will drop item immediately, permanently destroying it)

/t BOTNAME repair [ITEM LINK] (bot will seek out armourer and repair selected items specified by [ITEM LINK] )
/t BOTNAME repair all (bot(s) will seek out armourer and repair all damaged items equipped, or in bags )

Repair with bots:
=================

  Bot can now repair <all or selected> items - equipped or in bags. If the bot is
  a member of a guild, then the guild fund is used for repairs. If not, the bots own
  gold supply is used. If the bot cannot pay for the repair, they remain damaged.

  The new 'stats' command provides useful information to help in the repair decision.

  First: Money available to bot(s)
  Second: Free inventory slots for bot(s)
  Third: Estimated (excludes NPC reputation discount) item damage cost for bot(s).