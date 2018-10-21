# Combat Commands

The following commands are for combat related situations.


/t BOTNAME attack (bot will attack selected target, similar to the way a pet can attack)

/t BOTNAME assist (you'll need to be attacking something and the bot only does melee atm)

/t BOTNAME cast <SPELLID | (part of) SPELLNAME | [SPELLLINK]>

/t BOTNAME pet spells (Shows spells known to bot's pet. Autocast spells will be shown in green)

/t BOTNAME pet cast <SPELLID | (part of) SPELLNAME | [SPELLLINK]>

/t BOTNAME pet toggle <SPELLID | (part of) SPELLNAME | [SPELLLINK]> (Toggle autocast for a given spell)

/t BOTNAME pet react <(a)ggressive | (d)efensive | (p)assive> (Set bot's pet reaction mode)

### Combat Orders explained:
========================

  There are primary and secondary commands which can be combined. In this way it is

  possible to define a bot to assist the main tank and also protect the healer, making
  combat management much easier.

  The commands assist and protect require a target parameter or a friendly player
  selected by bots master.

 ###  Available Combat Orders:

* tank pri try to bind all targets involved in combat by gaining highest threat

* assist pri do damage on selected targets attacker without getting highest threat

* heal  pri concentrate on healing - no offensive spells, try to keep threat low

* protect  sec if target of protect get's directly attacked gain higher threat on attacker

* reset clear out assist and protect targets and set combat order to nothing

  ### Examples:

    /t TheTank orders combat tank

    /t MyHealer orders combat heal

    /t TheBrutal orders combat assist TheTank

    /t TheBrutal orders combat protect MyHealer