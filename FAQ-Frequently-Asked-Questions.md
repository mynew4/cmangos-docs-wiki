# Frequently Asked Questions around CMaNGOS

## How to Install?
See our [[Installation Instructions]]

## First time users
### The server has an error when i try to start it
See the part about Howto Install

### I cannot login onto my server
* realmd started?
* mangosd started?
* realmd database, table `realmlist` set to match the values in your mangosd.conf?
* realmlist set to your localhost? (set realmlist 127.0.0.1)
* User account created? (See [[Installation Instructions]] again)

### I play TBC or WotLK and cannot access the Blood Elves, Draenei, Worgen or Goblins
* You need to set the expansion of your account to 1/2/3 (for TBC/WotLK/Cata). See [[Installation Instructions]]

### I play WotLK/Cata and cannot access the Death Knight
* You need to the expansion of your account to 2 or 3 (2 for TBC, 3 for Cata)
* You need to level a character to level 50 OR
* Change the config option "MinLevelForHeroicCharacterCreating" in your mangosd.conf OR
* Set your account to be a GM Account (see next question)

### How can i use GM commands?
* You need to set your GM-Level. See [[Installation Instructions]]

## How to Update?
..