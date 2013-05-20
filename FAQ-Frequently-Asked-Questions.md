# Frequently Asked Questions around CMaNGOS

## Generic things to do in case of a problem
* Read Server.log output. Read it carefully!

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
### MaNGOSd or/and Realmd instantly closes when i start them!
* Run mangos in command line instead, if you have git bash that's also fine. Then you will see the onscreen error output and be able to continue from there.
* Make sure there are no other processes using the required ports (default 8085 & 3724).

### I play TBC or WotLK and cannot access the Blood Elves, Draenei, Worgen or Goblins
* You need to set the expansion of your account to 1/2/3 (for TBC/WotLK/Cata). See [[Installation Instructions]]

### I play WotLK/Cata and cannot access the Death Knight
* You need to the expansion of your account to 2 or 3 (2 for TBC, 3 for Cata)
* You need to level a character to level 50 OR
* Change the config option "MinLevelForHeroicCharacterCreating" in your mangosd.conf OR
* Set your account to be a GM Account (see next question)

### How can i use GM commands?
* You need to set your GM-Level. See [[Installation Instructions]]

### Npcs directly evade when I try to attack
### All Npcs are friendly or neutral
### All Gameobjects around me sparkle
* You need to turn GM mode off: .gm off
* Maybe you have still invisibility on, try .gm visi on

## How to Update?

### Updating the source code
* Open a Git Bash (see [[Installation Instructions]]) in your C:\Mangos or ~/mangos (or your base directory)
* `cd mangos` (This assumes you followed the Installation Instructions, and the directory where your sources are is located in C:\Mangos\mangos or ~/Mangos/mangos
* Invoke `git pull` to update
* `cd src/bindings/ScriptDev2` (This step and the next only if you also want to update SD2 and you had it installed)
* Invoke `git pull`

### Compiling and installing the update
* You need to compile core and SD2 just like you did before in your first setup (See [[Installation Instructions]] )

### Fetching new content from the database provider
* This depends on your database provider, you might want to update your SVN or Git clone of the database

### Updateing the database
* Even if your Database provider did not ship new updates, you still might have to update your database content due to core changes.
* In this case the easiest is to rerun an Installer Script of your DB-provider

* If you don't want to reset the database to a clean state (for example because you added some custom things), then you _might_ need to update manually.
* To check if you need a manual update, just start the mangosd and check if a database error on start is printed.
* If it is, read the error message carefully (you can read it more easily from the file Server.log)
