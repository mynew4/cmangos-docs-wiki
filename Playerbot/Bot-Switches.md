# Bot Switches

Switches work just like it sounds.. they turn settings for bots On, OFF, Or maybe just GO one time and stop.


### Here are the switch commands:

/t BOTNAME follow (orders bot to follow player; will also revive bot if dead or teleport bot if far away)

/t BOTNAME follow far (orders bot to increment follow distance +1.0 from what it is now)

/t BOTNAME follow near (orders bot to decrement follow distance -1.0 from what it is now)

/t BOTNAME follow auto (turns auto variable follow distance on/off) see [Automatic Action](Automatic-Action) for details.

/t BOTNAME stay

/t BOTNAME assist (you'll need to be attacking something and the bot only does melee atm)

/t BOTNAME reset (will reset states, orders and loot list)

/t BOTNAME collect <subcommand(s)> (subcommands can be alone or together [none combat loot objects profession quest])

/t BOTNAME sell all (Bot will sell all white low level items the NEXT time you sell. This must be given each time)

/t BOTNAME talent reset (Resets all talents)

/t BOTNAME autoequip ( bot will autoequip items they can use. Must be given each time you log in. once for ON, again for OFF)

/t BOTNAME autoequip <on | of | now> ( either on, or off or do it now one time regardless of setting)

