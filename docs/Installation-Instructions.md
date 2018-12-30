# Introduction

How to install C(ontinued)-MaNGOS from scratch and how to update it.

This Guide will help you for Windows or \*nix (Ubuntu, Debian) and for all supported clients: Classic - TBC - WotLK.

There is a guide with detailed screenshots on [how to install on Windows][1] for users unfamiliar with version control, compiling source code, etc.

Instructions covering Mac OS X (10.6 & 10.7) specific steps are available [here](Build-CMaNGOS-for-Mac-OS-X) in addition of this guide.

For other environments (like FreeBSD, ARM and similar) please consider our [forum](https://forum.cmangos.net) for assistance.

If you run into issues during installation or need help understanding one of the following steps, please visit [discord](https://discord.gg/Dgzerzb) to look for solutions and ask questions.

These Installation Instructions are expected to be current, so please read through every step again to ensure that you didn’t skip or misunderstand something before going to the forums.

If you are an absolute beginner to programming and compiling then you may want to go through the [Beginner’s Guide](Beginners-Guide-Home) first.

# Addresses

-   CMaNGOS: [site](https://cmangos.net) | [forum](https://forum.cmangos.net) | [git repositories](https://github.com/cmangos) | [discord](https://discord.gg/Dgzerzb)
-   Classic-DB: [forum](https://github.com/cmangos/classic-db/issues) | [git repository](https://github.com/cmangos/classic-db.git)
-   TBC-DB: [forum](https://github.com/cmangos/tbc-db/issues) | [git repository](https://github.com/cmangos/tbc-db.git)
-   WOTLK-DB: [forum](https://github.com/cmangos/wotlk-db/issues) | [git repository](https://github.com/cmangos/wotlk-db.git)
-   YTDB: [forum](http://ytdb.ru) | [svn repository](http://svn2.assembla.com/svn/ytdbase/)
-   PSDB: [forum](http://project-silvermoon.forumotion.com/) | [svn repository](http://subversion.assembla.com/svn/psmdb_wotlk/)

# Software requirements (Windows)

Game client of:

-   World of Warcraft Classic (1.12.x) for cmangos-classic
-   World of Warcraft TBC (2.4.3) for cmangos-tbc
-   World of Warcraft WotLK (3.3.5a) for for cmangos-wotlk

Some tools:

-   Git: [Main Download Page](https://git-scm.com/). Select the "Git Bash Here" and "Use Git Bash only" options from the respective pages of the [install Wizard](http://tinypic.com/view.php?pic=v45smh&s=6#.V2vSH_krKHs) in order to follow along with these instructions; otherwise, just use the default install options. *Alternatively, you can install ([Git Extensions](http://sourceforge.net/projects/gitextensions/files/latest/download)) instead, which comes with Git, MySYSGit, and KDiff).*
-   CMAKE is now used to generate visual studio project file as it’s are not provided anymore [Download it from here](https://cmake.org/).
-   Visual C++ 2015 or newer: [Visual Studio Downloads](https://www.visualstudio.com/downloads/) ([Visual Studio Community](https://www.visualstudio.com/vs/community/) 2015 is recommended, but Express 2015 for Desktop will also do the job and is free, it is however not as good a choice for open source development as CE (Community Edition).
-   Any MySQL server such as [MySQL server community edition](http://dev.mysql.com/downloads/mysql/) or [XAMPP](http://www.apachefriends.org/en/xampp.html). (Note 2018-05-02: Do not use MySQL version 8.0 for now since build will fail on some queries. Use 5.7 until resolved)
-   Any MySQL client (optional, for easy database access) such as [MySQL Workbench](http://dev.mysql.com/downloads/workbench/) or [SQLyog](https://www.webyog.com/)
-   SVN (very optional, for easy download of alternative (not directly supported by the cmangos team) databases (ytdb / psdb)): [Tortoise SVN](http://tortoisesvn.net/downloads).
-   An advanced text editor (optional) such as [Notepad++](http://notepad-plus-plus.org/). Definitely not required but will make editing the configuration files much easier in later steps.

You can find [a video here](https://youtu.be/drnlf4UMZ1w) of how to install Git, Visual Studio and CMAKE.

There is a detailed installation guide on [how to install on Windows][1].

# Software requirements (\*nix)

You will need Git, GCC, CMake, MySQL, Boost and a few libraries

## Ubuntu (12.04)

```bash
sudo apt-get install build-essential gcc g++ automake git-core autoconf make patch libmysql++-dev mysql-server libtool libssl-dev grep binutils zlibc libc6 libbz2-dev cmake subversion libboost-all-dev
```

## Debian

```bash
apt-get install grep build-essential gcc g++ automake git-core autoconf make patch cmake libmysql++-dev mysql-server libtool libssl-dev binutils zlibc libc6 libbz2-dev subversion libboost-all-dev
```

## Fedora

```bash
dnf install git cmake gcc patch autoconf mariadb-server mariadb-devel libtool zfstream gcc-c++ subversion boost-devel
```

*Note: installing boost-devel has not been tested yet.*

# Essentials

**CMaNGOS**  
is the server, also called "core", which manages all the game inquiries and accesses your SQL Database to get the information needed.

**ScriptDev2**  
is an optional library which contains C++ scripts that, when added to CMaNGOS, handles special events, quests, encounters and bosses. **AS OF 11/1/2015 ScriptDev2 HAS BEEN INTEGRATED INTO THE "CORE"**

**ACID**  
stands for "Advanced Creature Intelligence Database". It is an optional SQL database that handles regular mobs and bosses. ACID and ScriptDev2 complement each other and you should use both. ACID is usually already included in the database shipped by the database providers. **AS OF 10/2016 ACID HAS BEEN INTEGRATED INTO THE "DATABASES"**

in the context of CMaNGOS installation is usually referring to the world database, which contains all of the content of the game world run by CMaNGOS.

**CMaNGOS databases**  
cMaNGOS provides 3 different content databases depending on the core version:

-   WOTLK-DB (for WotLK - 3.3.5a)
-   TBC-DB (for TBC - 2.4.3)
-   Classic-DB (for Classic - 1.12.1)

**Alternative databases**  
A few other teams also provide databases that work with the cmangos core, and while we here at cmangos don’t directly support them they still are a valid choice, and to some a more prefered one.

-   YTDB (for WotLK - 3.3.5a)
-   PSDB (for WotLK - 3.3.5a)

**World Of Warcraft Client**  
is a client to connect to the server. It’s your own copy of the game.

# Tools

**Git**  
is a free distributed revision control or source code management tool which allows you to easily manage a virtual filesystem. With this tool, you’ll download the code from CMaNGOS, ScriptDev2, and ACID.

**CMAKE**  
its the most used tools that help to keep this project cross-platform.

**Microsoft Visual Studio**  
is used to created, modify and compile the code using C and C++ programming languages. With this tool, you’ll compile CMaNGOS and ScriptDev2 on Windows.

**MySQL server**  
is a relational database management system (RDBMS) that runs as a server providing multi-user access to a number of databases. After you’ve created the databases and imported the data, they will contain your entire world for World of Warcraft.

**MySQL client**  
allows you to connect to the MySQL server by providing an easy-to-use interface to import and change the data in the database.

**IRC**  
is a simple chat system that is used by supporters and developers of CMaNGOS.

# How things fit together

The following parts exist:

-   Server services: The binary files `mangosd(.exe)` and `realmd(.exe)` manage the communication with the client
-   World database: This database is filled by the database provider and contains content like NPCs, quests and objects
-   Characters database: Contains the information about characters like player-name, level and items
-   Realmd database: This database contains account-information (account-name, password and such)
-   Client: Which will, with adapted **realmlist**, connect to your server

## Get the remote data to your system

It is a good idea to start off your installation with some basic directory structure. See the below options depending on your operating system and follow along.

## For Windows

[CMaNGOS Installation Guide for Windows][1]

For this guide we will assume that you will use `C:\mangos` as base directory under which you put everything.

All shell commands are expected to be typed from a **Git bash** started from the `C:\mangos` directory. To do so, right-click onto `C:\mangos` in the windows explorer, and select `Git bash here` from the context menu.

## For \*nix

If desired, a new user can be created to run your mangos server under

```bash
useradd -m -d /home/mangos -c "MaNGOS" -U mangos
```

This guide assumes you will use this new user personal folder (`/home/mangos`) as a base folder under which you will put everything.

```bash
cd /home/mangos
```

## Clone CMaNGOS

After having opened Git bash in the right folder, simply type:

| Version | Command                                                 |
| ------- | ------------------------------------------------------- |
| Classic | `git clone git://github.com/cmangos/mangos-classic.git` |
| TBC     | `git clone git://github.com/cmangos/mangos-tbc.git`     |
| WotLK   | `git clone git://github.com/cmangos/mangos-wotlk.git`   |

Submit this git command with enter/return. This will take a little time to complete, but afterwards you will have created a sub-directory named `mangos-classic`, `mangos-tbc`, or `mangos-wotlk`, into which the CMaNGOS sources are cloned.

**Important note:** Throughout the guide some pathes will contain the string `mangos-version`. You will be expected to substitute `-version`, with the correct `-classic`, `-tbc`, or `-wotlk`, depending on which version you are installing.

A simple [video](https://youtu.be/At3VUI9fOq4) of the process

## Get the world-database stuff

### Official Databases

| Version | Command                                             |
| ------- | --------------------------------------------------- |
| Classic | `git clone git://github.com/cmangos/classic-db.git` |
| TBC     | `git clone git://github.com/cmangos/tbc-db.git`     |
| WotLK   | `git clone git://github.com/cmangos/wotlk-db.git`   |

### YTDB (WotLK)

**On Windows**

-   Open `C:\mangos` in the explorer, right-click on the right hand side
-   Select "Tortoise SVN Checkout" from the context menu.
-   Insert as SVN-URL: `http://svn2.assembla.com/svn/ytdbase/`

**On \*nix**

```bash
svn co http://svn2.assembla.com/svn/ytdbase/
```

This will create a new folder (likely `ytdbase`) in which YTDB SQL-files are located.

**On \*nix**

```bash
svn co http://svn2.assembla.com/svn/ytdbase/Mangos/Cataclysm ytdbase/
```

This will create a new folder (likely `ytdbase`) in which YTDB SQL-files are located.

### PSDB (WotLK)

**On Windows**

-   Open `C:\mangos` in the explorer, right-click on the right hand side
-   Select "Tortoise SVN Checkout" from the context menu.
-   Insert as SVN-URL: `http://svn.assembla.com/svn/psmdb_wotlk/`

**On \*nix**

```bash
svn co http://svn.assembla.com/svn/psmdb_wotlk/
```

## Directory structure

Now you should have the following subfolders:

-   `mangos` (containing the sources of CMaNGOS)
-   `classic-db` OR `tbc-db` OR `wotlk-db` OR `Database` containing the content of your database-provider

For windows we suggest creating an additional `run` folder, on \*nix this can be useful if you don’t want to install to `/opt` or so

-   `run`

For \*nix or cmake compile we suggest creating an additional `build` folder, this is not required for Visual Studio

-   `build`

# Compiling CMaNGOS

## Installing and Configuring boost (UNIX)

The CMaNGOS cmake scripts should automatically detect the location of your boost installation, and configure the build accordingly. If it is not detected, please ensure that your BOOST\_ROOT environment variable is set properly.

On most \*nix you just have to install boost development libraries from your distribution package repositories.

On Debian and Ubuntu you can simply install the `libboost-all-dev` meta-package. On Fedora there should be a package named `boost-devel` (untested). If you followed the [Software requirements (\*nix)](Installation-Instructions#software-requirements-nix) step above you should have the respective package installed already.

For instructions on how to compile boost from source code or general information, see the boost [Getting Started](http://www.boost.org/more/getting_started/index.html) guide.

## Installing and Configuring boost (Windows)

**Video Guide**  
-   [Download prebuild boost binaries](https://youtu.be/lxHTOM9KZak)
-   [Set BOOST\_ROOT environment variable](https://youtu.be/uBe2GIW0Af4)

**Step-by-step Guide**  
-   Go to <https://sourceforge.net/projects/boost/files/boost-binaries>
    -   Download the correct version as indicated in the table below **or** the `boost_x_xx_x-bin-msvc-all-32-64.7z` (the x\_xx\_x part is the boost version). If you need the Win32 or x64 version depends on what architecture you would like your compiled server executable to use. For most people x64 is fine.
        -   **Note: This has nothing to do with your Windows version**, apart from the fact that 64bit executables will not run on a 32bit Windows. It is very unlikely you have a 32bit OS but if you want to make sure that you have a 64bit one press **Win+Pause**.
        -   **Note:** You can install both the Win32 and the x64 binaries into the same directory, in case you want to switch build architectures. Visual Studio will automatically select the correct version.
    -   Version 1.64.0 is working as of 2017-12-30.
    -   You can try a more recent version if you want.
    -   There have been problems reported with version 1.66.0.

|         | Win32                         | x64                           |
| ------- | ----------------------------- | ----------------------------- |
| VS 2015 | boost_x_xx_x-msvc-14.0-32.exe | boost_x_xx_x-msvc-14.0-64.exe |
| VS 2017 | boost_x_xx_x-msvc-14.1-32.exe | boost_x_xx_x-msvc-14.1-64.exe |

-   Install the downloaded binaries.
-   Go to the **PC Properties** (press `<Win>+<Pause>`)
-   Click on **Advanced System Settings**
-   Click on **Environment Variables**
-   At the bottom under **System variables** click **New**
    -   Name: **BOOST\_ROOT**
    -   Value: **C:\\local\\boost\_x\_xx\_x** *Replace the x with the version number you downloaded, e.g. boost\_1\_64\_0.*
        -   If you changed the path while installing the binaries, you will have to do that here as well.
    -   Confirm
-   To make sure all programs are aware of the added environment variable reboot your system.

## Additional remarks regarding boost for advanced users (Windows)

If you are not using cmake, the built-in project files assume that BOOST\_ROOT environment variable is set.

If you have already boost in another folder schema you can also define *BOOST\_LIBRARYDIR* to point to the right folder. Then only win32 or x64 will work according to the file you have on that folder. Point BOOST\_LIBRARYDIR to the folder where the dll and lib files are, usually a subfolder of your boost root folder, e. g. the subfolder lib32-msvc-14.1.

If you are using cmake to generate a solution and project files, the CMaNGOS cmake scripts should automatically detect the location of your boost installation, and configure the build accordingly. If it is not detected, please ensure that your BOOST\_ROOT environment variable is set properly.

For instructions on how to compile boost from source code or general information, see the boost [Getting Started](http://www.boost.org/more/getting_started/index.html) guide.

Note: In a typical boost installation environment with Visual Studio, the user will configure their Visual Studio property sheets to point to the boost installation. This will allow boost to be found by all projects on that system. For information on configuring property sheets, look [here](https://msdn.microsoft.com/en-us/library/669zx6zc.aspx).

If you’re experiencing issues with CMake (The following Boost libraries could not be found), you will have to rename folder in boost directory.

```
(boost\lib32-msvc-14.1 -> boost\lib)
```

**Compiling CMaNGOS (Windows)**  
A [video](https://youtu.be/KlRM18SVCQA) of the build process is now available.

-   Launch cmake
-   Set the source bin to C:\\mangos\\mangos-version
-   Set the destination folder to C:\\mangos\\mangos-version\\bin\\buildir (create that folder if it doesn’t exist)
-   Tick *BUILD\_EXTRACTORS*
-   Click *Configure* button and set your compiler version and platform.
-   Select your options then click another time on *Configure* button
-   Click 'Generate’button
-   Now you can click on *Open* button or go to C:\\mangos\\mangos-version\\bin\\buildir and click on the .sln file
-   Wait for Visual Studio to finish loading.
-   Open the menu "Build" → "Configuration Manager"
    -   Choose "Release" in the drop down box for "Active Solution Configuration"
    -   The drop down box "Active Solution Platform" should be set to "Win32" by default. Change it to "x64" if you want to compile 64bit executables. (This setting has to correspond with the boost version you installed.)
    -   Close the window
-   Click the menu "Build" → "Build Solution"
    -   This will take some time.
    -   You might get some warning messages. Don’t worry about it, that’s normal.
    -   You must not get any error messages, although if you do so, you could click the menu "Build" → "Clean Solution" to restart the compile.
    -   If you get error messages saying some boost files cannot be found, you may need to restart your Visual Studio and/or your computer for the environment variables to be set.

If you cannot solve an error, please use the official forums or IRC channels to ask for help

**Compiling CMaNGOS (\*nix)**  

-   Go to your `/home/mangos` folder:<br>
    `cd /home/mangos`
-   Enter the build folder:<br>
    `cd build`
-   Invoke `cmake ../mangos`, suggested options are:
    -   `-DCMAKE_INSTALL_PREFIX=\../mangos/run` to install into the "run" subfolder of `/home/mangos` folder, otherwise this will install to `/opt/mangos`
    -   `-DPCH=1` to compile with PCH mode (much faster after updates).
    -   `-DDEBUG=0` to remove debug mode from compiling
    -   `-DBUILD_PLAYERBOT=ON` to build with playerbots enabled
    -   **Examples:**
        -   Just want to compile CMaNGOS<br>
            `cmake ../mangos -DCMAKE_INSTALL_PREFIX=\../mangos/run -DPCH=1 -DDEBUG=0`
        -   Want compile CMaNGOS & the map extraction tools<br>
            `cmake ../mangos -DCMAKE_INSTALL_PREFIX=\../mangos/run -DBUILD_EXTRACTORS=ON -DPCH=1 -DDEBUG=0`
        -   Want compile CMaNGOS & the map extraction tools & playerbots<br>
            `cmake ../mangos -DCMAKE_INSTALL_PREFIX=\../mangos/run -DBUILD_EXTRACTORS=ON -DPCH=1 -DDEBUG=0 -DBUILD_PLAYERBOT=ON`
-   Invoke `make` to compile CMaNGOS. You may specify the number of cores to be used with the `-j` option.<br>
    `make -j8`
-   Invoke `make install` to install CMaNGOS to the location specified in `DCMAKE_INSTALL_PREFIX`.

# Install CMaNGOS binary files

-   Transfer the files from your compile folder (likely `C:\mangos\mangos-version\bin\Win32_Release`) into `C:\mangos\run`
-   Go to `C:\mangos\mangos-version\src\game\AuctionHouseBot` and copy `ahbot.conf.dist.in` to `C:\mangos\run` and rename it to `ahbot.conf`
-   If you compiled project with the PlayeBots enabled, go to `C:\mangos\mangos-version\src\game\PlayerBot` and copy `playerbot.conf.dist.in` to `C:\mangos\run` and rename it to `playerbot.conf`

On \*nix this is partly done with the `make install` command (from the build directory).

You will however still need to manually copy and rename the .conf.dist files to .conf files.

# Extract files from the client

## Windows

-   Copy the content of `C:\mangos\mangos-version\bin\Win32_Release\Extractors\` into your `C:\World of Warcraft` folder
-   Run `ExtractResources.sh` from your `C:\World of Warcraft`.
    For this you can open a "Git Bash" on your C:\\World of Warcraft folder and type `ExtractResources.sh`
    Depending on your installation settings, a simple double click onto the `ExtractResources.sh` file from your explorer might also work.
    -   You must extract **DBC/maps** and **vmaps** for CMaNGOS to work, **mmaps** are optional (and take very long)
-   When finished, move the folders `maps`, `dbc`, `Cameras` and `vmaps` - optionally `mmaps` - that have been created in your `C:\World of Warcraft` to your `C:\mangos\run` (the buildings folder is not required and can be deleted).

## \*nix

Ever since extractors are no longer in repository, you will need to compile them yourself. The extraction process should work identically to Windows, since the scripts are portable.

If you followed this guide the file can be found in:

-   Executables: `/home/mangos/mangos-version/run/bin/tools`
-   Scripts: `/home/mangos/mangos-version/contrib/extractor_scripts`

# Install databases

For this section it is assumed you have already installed your MySQL server, and have a password for "root" user.

To make use of some additional installation helper scripts it is HIGHLY suggested when installing MYSQL you include the command path to the BIN folder (Option during Install). If this option was not available or if you missed it please follow the instructions found [here](http://dev.mysql.com/doc/mysql-windows-excerpt/5.1/en/mysql-installation-windows-path.html) before proceeding. If you don’t have this configured properly then you will not be able to follow along with the command-line steps below in the guide because the command prompt will not recognize "mysql" as a valid command.

## Create empty databases

Either use a GUI tool for mysql and open the SQL-files, or do it by command-line as this guide shows.

From the C:\\mangos folder invoke (in Git bash):

-   `mysql -uroot -p < mangos/sql/create/db_create_mysql.sql`
-   Enter your password in the following dialogue (similar in all other next steps)
-   This will create a user (name `mangos`, password `mangos`) with rights to the databases `mangos` (world-db), `characters` and `realmd`

## Initialize Mangos database

From the `C:\mangos` folder invoke (in Git bash):

| Version | Command                                                              |
| ------- | -------------------------------------------------------------------- |
| Classic | `mysql -uroot -p classicmangos < mangos-classic/sql/base/mangos.sql` |
| TBC     | `mysql -uroot -p tbcmangos < mangos-tbc/sql/base/mangos.sql`         |
| WotLK   | `mysql -uroot -p wotlkmangos < mangos-wotlk/sql/base/mangos.sql`     |

This will create and fill the Mangos database with some values.

## Initialize DBC data

From the C:\\mangos folder invoke (in Git bash):

| Version | Command                                                             |
| ------- | ------------------------------------------------------------------- |
| Classic | `mysql -uroot -p classicmangos < mangos-classic/sql/base/dbc/*.sql` |
| TBC     | `mysql -uroot -p tbcmangos < mangos-tbc/sql/base/dbc/*.sql`         |
| WotLK   | `mysql -uroot -p wotlkmangos < mangos-wotlk/sql/base/dbc/*.sql`     |

This will create and fill in Mangos database the imported DBC data.

On \*nix you may want to use the following two scripted commands:

| Version | Command                                                                                                                              |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Classic | `for sql_file in ls mangos-classic/sql/base/dbc/original_data/*.sql; do mysql -uroot -p --database=classicmangos < $sql_file ; done` |
| TBC     | `for sql_file in ls mangos-tbc/sql/base/dbc/original_data/*.sql; do mysql -uroot -p --database=tbcmangos < $sql_file ; done`         |
| WotLK   | `for sql_file in ls mangos-wotlk/sql/base/dbc/original_data/*.sql; do mysql -uroot -p --database=wotlkmangos < $sql_file ; done`     |

| Version | Command                                                                                                                              |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Classic | `for sql_file in ls mangos-classic/sql/base/dbc/cmangos_fixes/*.sql; do mysql -uroot -p --database=classicmangos < $sql_file ; done` |
| TBC     | `for sql_file in ls mangos-tbc/sql/base/dbc/cmangos_fixes/*.sql; do mysql -uroot -p --database=tbcmangos < $sql_file ; done`         |
| WotLK   | `for sql_file in ls mangos-wotlk/sql/base/dbc/cmangos_fixes/*.sql; do mysql -uroot -p --database=wotlkmangos < $sql_file ; done`     |

## Initialize characters database:

From the C:\\mangos folder invoke (in Git bash):

| Version | Command                                                                      |
| ------- | ---------------------------------------------------------------------------- |
| Classic | `mysql -uroot -p classiccharacters < mangos-classic/sql/base/characters.sql` |
| TBC     | `mysql -uroot -p tbccharacters < mangos-tbc/sql/base/characters.sql`         |
| WotLK   | `mysql -uroot -p wotlkcharacters < mangos-wotlk/sql/base/characters.sql`     |

This will create an empty characters database.

## Initialize realmd database:

From the C:\\mangos folder invoke (in Git bash):

| Version | Command                                                              |
| ------- | -------------------------------------------------------------------- |
| Classic | `mysql -uroot -p classicrealmd < mangos-classic/sql/base/realmd.sql` |
| TBC     | `mysql -uroot -p tbcrealmd < mangos-tbc/sql/base/realmd.sql`         |
| WotLK   | `mysql -uroot -p wotlkrealmd < mangos-wotlk/sql/base/realmd.sql`     |

This will create an empty realmd database.

## Fill world database:

**Support for cmangos databases.**

From the C:\\mangos folder invoke (in Git bash or depending on installation with double-click!)

-   Run `cd classic-db`, `cd tbc-db`, or `cd wotlk-db` (choose the one applicable to your situation)
-   Run `./InstallFullDB.sh`<br>
    This will create a config file named `InstallFullDB.config`, looking like this:

```
####################################################################################################
# This is the config file for the './InstallFullDB.sh' script
#
# You need to insert
#   MANGOS_DBHOST:  Your MANGOS database host
#   MANGOS_DBNAME:  Your MANGOS database schema
#   MANGOS_DBUSER:  Your MANGOS username
#   MANGOS_DBPASS:  Your MANGOS password
#   CORE_PATH:      Your path to core's directory
#   MYSQL:          Your mysql command (usually mysql)
#
####################################################################################################

## Define the host on which the mangos database resides (typically localhost)
MANGOS_DBHOST="localhost"

## Define the database in which you want to add clean DB
MANGOS_DBNAME="VERSIONmangos"

## Define your username
MANGOS_DBUSER="mangos"

## Define your password (It is suggested to restrict read access to this file!)
MANGOS_DBPASS="mangos"

## Define the path to your core's folder
##   If set the core updates located under sql/updates/mangos from this mangos-directory will be added automatically
CORE_PATH=""

## Define your mysql programm if this differs
MYSQL="mysql"

# Enjoy using the tool
```
-   Change configuration in any text-editor<br>
    With the default configuration, you only need to change `CORE_PATH` to:<br>
    `CORE_PATH="../mangos-version"`
    -   This assumes database and core repositories have been cloned to the same location, e.g. they are both in `C:\mangos` or `/home/mangos`.
    -   If relative path does not work, use absolute path:
        -   Windows: `CORE_PATH="/c/mangos/mangos-version"` (case-sensitive)
        -   \*nix: `CORE_PATH="/home/mangos/mangos-version"`
-   Now the helper tool is configured, and you only need to run the helper script again, whenever you want to set your world database to a clear state!
-   `sh ./InstallFullDB.sh`

    And check the output if the database could be set up correctly. If the helper script complains about not finding the config file, just open InstallFullDB.sh in a text editor and set

        SCRIPT_FILE="./InstallFullDB.sh"
        CONFIG_FILE="./InstallFullDB.config"

-   You can now run the script again, and it should start filling your world database.

-   `cd ../..`

If you get an error saying `./InstallFullDB.sh: line 126: mysql: command not found` then you need to add mysql.exe to the PATH variable. (Windows + Pause → Advanced System Settings → Environment Variables → System Variables → Edit Path and add the location of your mysql.exe)

## Basic concept of manual database filling

The database providers provide

**A full-dump release file:**<br>
This file contains the whole database content of one point

**Updatepacks:**<br>
An updatepack consist of
-   collected core updates for the mangos (world) database
-   collected core updates for the characters database
-   collected core updates for the realmd database
-   content fixes

So you need to:
-   Apply the latest release file
-   Apply all following updatepack files (always corepatches before updatepacks)
-   Apply the remaining updates from the core (located in C:\mangos\mangos-version\sql\updates

# Alternative Databases

-   Execute PSDB\_Installer in psmdb\_wotlk svn folder.
-   Type your info when prompted.
-   You can also edit PSDB\_Installer.bat for quick re-install of PSDB & Scriptdev2 DB by changing "set quick=on" & "set pass=".

    Example of PSDB\_Installer.bat:

        ####################################################################################################
        8888888b.   .d8888b.  8888888b.  888888b.  (LK)
        888   Y88b d88P  Y88b 888  "Y88b 888  "88b
        888    888 Y88b.      888    888 888  .88P
        888   d88P  "Y888b.   888    888 8888888K.
        8888888P"      "Y88b. 888    888 888  "Y88b
        888              "888 888    888 888    888
        888        Y88b  d88P 888  .d88P 888   d88P
        888         "Y8888P"  8888888P"  8888888P"

        Credits to: Factionwars, Nemok and BrainDedd

        What is your MySQL host name?           [localhost]   :
        What is your MySQL user name?           [root]        :
        What is your MySQL password?            [ ]           :
        What is your MySQL port?                [3306]        :
        What is your World database name?       [mangos]      :
        What is your ScriptDev2 database name?  [scriptdev2]  :
        What is your Characters database name?  [characters]  :
        What is your Realmd database name?      [realmd]      :

        This will wipe out your current World database and replace it.
        Do you wish to continue? (y/n)

        This will wipe out your current ScriptDev2 database and replace it.
        Do you wish to continue? (y/n)

        This will wipe out your current Characters database and replace it.
        Do you wish to continue? (y/n)

        This will wipe out your current Realm database and replace it.
        Do you wish to continue? (y/n)

        This will optimize your current database.
        Do you wish to continue? (y/n)
        ####################################################################################################

    **Support for YTDB Needed.**

# Configuring CMaNGOS

This part should be an extra wiki-page: Meaning of config files from mangos/sd2

With the default installations, you should get a working environment out of the box :)

## (OPTIONAL) Update \*.conf files

You will need to manually update the configuration files within your "run" directory (ie C:\\mangos\\run ).

The files are:

-   mangosd.conf: Holds configuration for the mangosd executable
-   realmd.conf: Holds configuration for the realmd executable
-   scriptdev2.conf: Holds configuration for ScriptDev2’s settings(no longer used and may not exist)
-   (Very optional) ahbot.conf: Holds configuration for AHBot (by default disabled)
-   (optional, only if you enabled PlayerBots during complilation) playerbot.conf: Holds configuration for PlayerBots (by default disabled)

Most important to configure are the database settings. You will need this if you decided to use a different password/user then the "default" combination of mangos/mangos.

These settings are relatively self-explaining, you should look for the settings of "LoginDatabaseInfo", "WorldDatabaseInfo", "CharacterDatabaseInfo" and "ScriptDev2DatabaseInfo" (no file contains all of these options)

## (OPTIONAL) Update realmd.realmlist

You need to change this only if you changed the mangosd.conf settings "WorldServerPort" or "RealmID"

This information is required so that the realmd "knows" to which mangosd he should forward a player after authentication, so if you want to use your server outside itself (e.g. on your LAN) please change `127.0.0.1` by your server ip !

Apply code to realmd database, adapt to your wishes

```sql
DELETE FROM realmlist WHERE id=1;
INSERT INTO realmlist (id, name, address, port, icon, realmflags, timezone, allowedSecurityLevel)
VALUES ('1', 'MaNGOS', '127.0.0.1', '8085', '1', '0', '1', '0');
```

Where of course the data must match the configs:

-   port (above 8085) must match the value in the mangosd.conf (Config option: "WorldServerPort")
-   id (above 1) must match the value in the mangosd.conf (Config option: "RealmID")

# Configuring your WoW-Client

-   Copy `C:\World Of Warcraft\Data\enEN\realmlist.wtf` to `realmlist.old` within the same folder

Your locale folder may be named differently according to your region ("enUS", "enGB", "frFR", "deDE", etc)

-   Open `realmlist.wtf` in Notepad and change the contents to the following:<br>
    `set realmlist 127.0.0.1`

**Always use the wow.exe and NOT the launcher to start your WoW-Client**

# Running your Server

On Windows system launch `C:\mangos\run\mangosd.exe` and `C:\mangos\run\realmd.exe`

On \*nix run the corresponding binary files :

```bash
/home/mangos/mangos-version/run/bin/mangosd -c /home/mangos/mangos-version/run/etc/mangosd.conf -a /home/mangos/mangos-version/run/etc/ahbot.conf
```

```bash
/home/mangos/mangos-version/run/bin/realmd -c /home/mangos/mangos-version/run/etc/realmd.conf
```

## Tip1

**Don’t run mangosd or realmd as root !**

```bash
su mangos
```

This command will connect you as **mangos** user.

## Tip2

you can run mangosd and realmd in separate screens

```bash
exec screen -dmS mangosd /home/mangos/mangos-version/run/bin/mangosd -c /home/mangos/mangos-version/run/etc/mangosd.conf -a /home/mangos/mangos-version/run/etc/ahbot.conf
```

```bash
exec screen -dmS realmd /home/mangos/mangos-version/run/bin/realmd -c /home/mangos/mangos-version/run/etc/realmd.conf
```

## Tip3

if you want to start mangosd and realmd at your server boot, you can use a cron task. create a `/home/mangos/cmangos-launcher.sh` file with this content :

```bash
#!/bin/bash
exec screen -dmS mangosd /home/mangos/mangos-version/run/bin/mangosd -c /home/mangos/mangos-version/run/etc/mangosd.conf -a /home/mangos/mangos-version/run/etc/ahbot.conf++
exec screen -dmS realmd /home/mangos/mangos-version/run/bin/realmd -c /home/mangos/mangos-version/run/etc/realmd.conf++
```

and then, as `mangos` user, run `crontab -e` and add this line :

```
@reboot /bin/bash /home/mangos/cmangos-launcher.sh
```

It’ll run this script at your server boot.

# Creating first account:

Once everything in mangosd has loaded, here are some commands you can use.

In your Mangosd window, there is tons of text; not to worry, keep typing anyway, it doesn’t matter

## Creating the actual account

```
account create [username] [password]
```

Example:

```
account create MyNewAccount MyPassword
```

## Enabling expansions for a user

```
account set addon [username] [0 to 3]
```

-   0: Basic version
-   1: The Burning Crusade
-   2: Wrath of the Lich King

Example:

```
account set addon MyNewAccount 2
```

## Changing GM levels

```
account set gmlevel [username] [0 to 3]
```

-   0: Player
-   1: Moderator
-   2: Game Master
-   3: Administrator

Example:

```
account set gmlevel MyNewAccount 2
```

## Shutdown your server

```
.server shutdown [delay]
```

The delay is the number of seconds

# First login:

**Always use the wow.exe and NOT the launcher to start your WoW-Client**

Start your WoW-Client with the wow.exe and login with your previously created account name (NOT email) and password.

Note that if this account is GM-Account, you can use lots of nice commands to get around, (remark the . with which they all start) ie:

-   `.tele <location>`
-   `.lookup`
-   `.npc info and .npc aiinfo`
-   `.modify aspeed <rate>`
-   `.gm fly on` (note that although the command is available, it does not work on the classic core)

**Enjoy running and messing with your CMaNGOS server!**

[1]: Detailed-installation-guide-for-Microsoft-Windows
