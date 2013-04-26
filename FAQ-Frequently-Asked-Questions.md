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
* Don't use email as login
* Delete or rename wow.mfil and wow.tfil files
* use ONLY wow.exe to start up the client, never use launcher.exe
  (client versions 4.x and up require wow.exe to be patched prior aswell)

### My client still connect to a different host/address
* Add in your /WTF/config.wtf (SET realmlist "127.0.0.1") before (SET accountName "youraccount")

### I play TBC or WotLK and cannot access the Blood Elves, Draenei, Worgen or Goblins
* You need to set the expansion of your account to 1/2/3 (for TBC/WotLK/Cata). See [[Installation Instructions]]

### MaNGOSd or/and Realmd instantly closes when i start them!
* Run mangos in command line instead, if you have git bash that's also fine. Then you will see the onscreen error output and be able to continue from there.

### I play WotLK/Cata and cannot access the Death Knight
* You need to the expansion of your account to 2 or 3 (2 for TBC, 3 for Cata)
* You need to level a character to level 50 OR
* Change the config option "MinLevelForHeroicCharacterCreating" in your mangosd.conf OR
* Set your account to be a GM Account (see next question)

### How can i use GM commands?
* You need to set your GM-Level. See [[Installation Instructions]]

## How to Update?
### Updating MaNGOS source
* First off you should have git installed. Then you can "cd" into your mangos source folder. For example: "cd /c/MaNGOS/" When you are inside of there you type "git pull".
### Updating database
* After updating MaNGOS you might need to update the database structure, to find out, simply start MaNGOS and see if it gives you a "database error". If it does you must apply all updates from the sql update folder which is "after" what update mangos tells you you currently have. Note that you should apply the updates on correct databases (see filenames in updates folder)
### Updating ScriptDev2
* As with updating MaNGOS you must "cd" into the git repository, for example "cd /c/MaNGOS/src/bindings/ScriptDev2". Then you type git pull.

Note: After both the MaNGOS and ScriptDev2 procedure you must compile the core.
The reason we do this in mangos is to see if there are any database updates, then you will want the latest PvE "scripts" from ScriptDev on top of that for extra awesomeness!