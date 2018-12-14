This section covers some frequently asked questions about MinGW toolchains.

Keep in mind, that MinGW toolchains have enthusiast and DIY meaning to them, many distributions are highly customized, so its nearly impossible to answer every possible question or solve every possible issue you may have with a particular distribution. This page is intended to only provide a kickstart for your own journey.

Reasons to consider using MinGW instead of MSVC++
=================================================

MinGW toolchains are ports of GCC for Windows. GCC can offer a number of advantages over MSVC++ even on Windows, which include, but not limited to:

-   Open source and licensing policy. More details at <http://mingw.org/license>
-   GCC tends to implement newer C++ standards and drafts much faster than MSVC++.
    It was brought to light in the early 2010s, with Visual C++ often lagging years behind with C++11 features, MinGW gained a large following as a result of that.
-   It offers a much higher customizability in terms of build options than MSVC++.
    An expert with a fresh GCC version can try to take advantages of new architectures like AMD's Zen by rebuilding the program and it's dependencies with new instruction sets.

Choosing a MinGW toolchain variant for your needs
=================================================

Threading model
---------------

The first and foremost quality of a MinGW toolchain distribution.

### POSIX threading model

Implements C++11 threads by default through a dependency POSIX compatibility layer (such as WinPthread). A fail-safe variant for cross-platfrom development. However, most pre-built POSIX distributions include only dynamic Libwinpthreads library (a DLL), so if you aim for a fully static self-contained build, this may not fit your needs, as you have to carry at least one or two DLLs (Libwinpthreads and Libgcc) from the distribution alongside resulting binaries.

### WIN32 threading model

In the recent past, these variants did not include C++11 threads by default, therefore were unfit for cross-platform development. Newer versions from some toolchain builders started to include C++11 threads support through alternative implementations, such as a win32 port of pthreads or mingw-std-threads. You should carefully study contents of such distributions to make sure its equipped with std::thread support.

Exception Handling
------------------

Second most important quality, deciding whether its fit for development and debugging or release builds.

### DWARF (Debugging With Attributed Record Formats)

-   Architecture: 32bit target toolchains only.
-   Speed: Fastest for 32 bit, nearly zero overhead, directly competes with MSVC++.
-   Compatibility: Worst among all listed. Compatible only with other DWARF binaries. May introduce errors with linking and debugging, therefore generally unfit for development.
-   Origin: Unix ELF binaries standard, an alien species to Windows ecosystem.
-   Usage recommendation: Release builds distribution only, unfit for debugging and development due to compatibility issues.

### SJLJ (SetJmp / LongJmp)

-   Architecture: 32bit and 64bit target toolchains.
-   Speed: Slowest among all listed, introduces constant fixed penalty to produced binaries.
-   Compatibility: Best compatibility among all listed. Safely binds together DLLs, allows handling exceptions outside of code built with MinGW all the way up to system libraries.
-   Origin: Cross-platform standards.
-   Usage recommendation: Best option for development and debugging for 32bit builds. A fail safe option for 64bit development and debugging due to compatibility. Not recommended for any release builds due to speed penalty.

### SEH (Structured Exception Handling)

-   Architecture: 64bit target toolchains only.
-   Speed: Fastest for 64bit, directly competes with MSVC++.
-   Compatibility: Very good, compatible with MSVC++ symbol mangling.
-   Origin: A variety of standards. 32bit SEH option for MinGW is not available due to patent issues.
-   Usage recommendation: Best option overall for 64bit for all purposes due to balance of speed and compatibility.

MinGW Distribution
------------------

Once you've decided which is the variant you want, all thats left to do is pick your MinGW distribution.

At the time of the writing, the most frequently updated distribution project is MinGW-w64, which seems to be recognized as the distribution of choice for many major projects (such as popular Linux distributions and Qt). Distributions from MinGW team and TDM-GCC are less frequently updated.

If you are cross-compiling on Linux, you should probably stick to versions found in your package manager, so you can ask maintainers for support if any issue arises.

Some popular IDE software with C++ and MinGW support
====================================================

-   Code::Blocks (cross-platform, open source)
-   QtCreator (cross-platform, open source)
-   Eclipse (cross-platform, open source)
-   CLion (cross-platform, commercial)

Quickstart: Building Boost library for use with your MinGW toolchain on Windows
===============================================================================

In this example we will use Boost 1.64.0.

1.  Unzip downloaded Windows boost sources (“boost\_1\_64\_0.zip” in our case) to a folder of choice.
2.  Open Command Line (cmd.exe), navigate to the root folder of the extracted boost source (it must have file “bootstrap.bat” in it).
3.  Add the “bin” folder of your MinGW toolchain to your PATH environment, example:
    set PATH=%PATH%;C:\\Path\\To\\Your\\MinGW\\bin
4.  Configure boost for GCC with the following command:
    start /b /wait bootstrap.bat gcc
5.  Once configuration is complete, let's build a static Boost library into a fresh clean folder, let's say “C:\\Boost”:
    start /b /wait b2 install --prefix=“C:\\Boost” --build-type=complete toolset=gcc variant=release link=static threading=multi runtime-link=static
6.  After build is successfully done, you need to add it to your MinGW:
    Move “boost” directory from “C:\\Boost\\include\\boost-1\_64” into “include” subdirectory of your MinGW toolchain;
    Move all library files (\*.a) from “C:\\Boost\\lib” into “lib” subdirectory of your MinGW toolchain.
7.  Done. Your MinGW toolchain now contains a ready-to-use Boost library. You can now safely remove the now empty folder we used to built into (“C:\\Boost”).

