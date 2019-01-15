First of all you should know that it isn't that difficult to get your own server up and running with all of the tools provided by the CMaNGOS team. Once you have the necessary programs installed it takes about 10 minutes to compile the source code and start up a server. You don't need to be a programmer and you don't really need to be _that_ tech savvy. As long as you can follow instructions and aren't afraid to ask questions on the forums, you will get there with no (major) problems.

## Mangos... like the fruit?
Why is it called CMaNGOS? It is just a fun acronym that is easy to remember and say... like the fruit. Here is what it stands for:

**C**(ontinued) **Ma**(ssive) **N**(etwork) **G**(ame) **O**(bject) **S**(erver). The originating project was just called MaNGOS and so this is a "continued" version of the original.

## What is git?
Git is a source code revision control system and that's all you need to know about it for now (even though that may make no sense to you anyway). Github is the important thing to understand at the moment; it is a sort of social networking site for programmers and collaborators to share ideas and keep track of projects and it uses "git" to operate.

Every time something is changed in the source code of a project it is tracked and recorded on Github. It also enables multiple people to work on their own versions of a project and then submit updates to the main version once they are perfected. Think of it like the project being a binder with a bunch of pages. If you wanted to, for example, add a new section to the binder, Github makes it so you can copy the whole thing and take it home with you to work on in your spare time. Then once you've finished adding the pages to your copy, you bring it back to the main project and suggest that the original project be updated with your changes. As you can imagine, this makes the whole process a lot easier to manage because you can have any number of people working on their own ideas without breaking the initial project.

Github also has features to track issues with the code so that programmers can pickup various reported bugs, fix them, apply the fix to the main project, and then show that the fix was implemented.

## What are all these words?
There are a lot of terms ahead that you may not be familiar with so let's get started with some vocabulary:

**Source Code** > Source Code is the basic foundation of programming; it is the actual code that is typed out by programmers in any of the thousands of different programming languages.

**C++ or CPP** > Written both ways interchangeably, C++ (pronounced "see-plus-plus") is a programming language. Everything in CMaNGOS (except for the databases) is written in C++.

**Server** > In a client-server relationship, the "server" is where information is stored. The server hosts an environment or database of information for clients to connect to and retrieve. In the context of CMaNGOS, "Server" could refer to many things such as the game server, the login server, or the database server.

**Client** > In a client-server relationship, the "client" is where information is viewed. The client connects to the server and retrieves packets of information to display to the user. In the context of CMaNGOS, "Client" will always refer to the WoW game client that you have installed on your computer.

**Repository** > If Github was a filing cabinet then a repository would be a single folder in said cabinet. Projects are referred to as "repos" in this world because you are basically referring to a folder with a bunch of source code in it.

**Open Source** > Open source refers to the concept of everything being open and available to share with anyone. In the programming world, open source means that the code is openly shared and available to anyone to add to, edit, or copy as they wish (within the bounds of the respective terms of use).

**Compile** > When code is written it just looks like a bunch of text and symbols organized in strange ways that makes no sense to non-programmers. "Compiling" is the process of turning said code into a working program.

**Compiler** > Code doesn't compile itself and so we must use other programs to do it. These programs are called compilers.

**Bug** > A bug is a term programmers use to describe problems with code. A bug is usually the culprit when a program you are using shuts down for no apparent reason or when something just doesn't work.

**Database** > A database is a big heap of information typically organized in columns and rows much like an excel spreadsheet.

**SQL** > SQL is another programming language which stands for Structured Query Language and is used for managing databases.

**SQL Server** > An SQL Server is a virtual database (see above) that stores a bunch of stuff and uses the SQL language to operate.

**SQL Client** > Just because an SQL Server exists doesn't mean you can look at it like you would an excel sheet, at least not without another program. An SQL Client is a program that visualizes an SQL Server so that you can actually click and open things on the screen.

**MySQL** > MySQL is a version of SQL that CMaNGOS uses. Continuing with the spreadsheet example, it would be like deciding to use Microsoft Excel vs Google Spreadsheet. Both basically do the same thing but have different interfaces, styles, and associated programs.

**Query** > A query is a command being executed in SQL. When you update something on the server it sends a query just as when you pull information from the server it uses a query. Within the instructions, using a query will typically refer to entering a specific command into the command prompt or terminal you are using.

## Step-by-step

So from start to finish, this is a quick summary of the steps you will take to get a server running. You may not understand many (or any) of these yet but you have to start somewhere!

1. Download and install all the tools mentioned in the installation instructions (e.g. Git, Visual Studio, etc).</br>
2. Download or install a WoW client and patch it to the proper version of the server you want to build (e.g. if you were building a Classic server you would need a WoW client patched to version 1.12.1).</br>
3. Setup a MySQL Server.</br>
4. Create a folder on your hard drive to place all of your work.</br>
5. Copy the necessary repositories from Github to said folder.</br>
6. Compile the source code.</br>
7. Create and populate your MySQL Server databases.<br>
8. Extract resources from your WoW client.</br>
9. Move all necessary files and resources to your "run" folder.</br>
10. Edit the configuration files.</br>
11. Run realmd.exe.</br>
12. Run mangosd.exe.</br>
13. If updates are needed to your databases, apply them as needed and restart mangosd.exe.</br>
14. Update your client's realmlist.wtf document to point to your server.</br>
15. Run wow.exe and enjoy!

## Where do I start?
The next sections of this guide will focus on all of the different pieces of CMaNGOS and how they work together. Remember that this guide will not tell you _how_ to put them together, it will just give you a simplified explanation of what everything is. The Installation Instructions (found [here](Installation-Instructions)) is where you should go for the actual process of building a CMaNGOS server.

Next: [What Everything Is](Beginners-Guide-What-Everything-Is)

[Beginner's Guide Home](Beginners-Guide-Home)
