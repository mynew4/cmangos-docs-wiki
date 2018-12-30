# Motivation

Development on Mac OS X is mostly done with the Developer Tools provided by Apple (Xcode).

The most common option on Mac OS X 10.6 is to install Xcode 3.2 (3.2.6 is the most recent version). This version comes with several compilers (Apple GCC 4.0, Apple GCC 4.2, Apple LLVM/clang), but none of them is able to compile C++11 code.

It is possible to get a more recent compiler on Mac OS X 10.6 by installing the Snow Leopard build of Xcode 4.2. Sadly, this version is only available for paying developer accounts. But more importantly, this version only has partial C++11 support, which is not good enough.

In summary: the Xcode versions that support Mac OS X 10.6 do not provide a modern C++ compiler that is able to compile the C++11 source code of the CMaNGOS project.

# Building GCC on Mac OS X

Therefore, we suggest to install a recent versions of GCC (this guide uses GCC 4.8.5). This toolchain can be installed next to an existing Xcode installation, so you can continue to use Xcode as before, while the new GCC can be used to build the CMaNGOS sources.

You will need about 3 GB of free disk space for the entire process. Once installed, you can remove the temporary files and reclaim most of this disk space again.

We're assuming that you have a working Xcode 3.2 installation, with the command line tools installed.

Open the Terminal application, and follow the steps below to install GCC 4.8.5.

**1. Create a temporary directory for GCC's sources and build.**

    $ mkdir ~/src && cd ~/src
**2. Download the GCC 4.8.5 sources.**

    $ curl -o gcc-4.8.5.tar.bz2 https://ftp.gnu.org/gnu/gcc/gcc-4.8.5/gcc-4.8.5.tar.bz2
**3. Download and verify the source's signature [optional]**

It's rather unlikely, but if you know you have gpg installed, you can download the relevant signatures to verify the integrity of the GCC source tarball. If you trust the download from the previous step, feel free to skip this step.

    $ curl -o gcc-4.8.5.tar.bz2.sig https://ftp.gnu.org/gnu/gcc/gcc-4.8.5/gcc-4.8.5.tar.bz2.sig
    $ curl -o gnu-keyring.gpg https://ftp.gnu.org/gnu/gnu-keyring.gpg
    $ gpg --verify --no-default-keyring --keyring ./gnu-keyring.gpg gcc-4.8.5.tar.bz2.sig
**4. Extract the sources.**

    $ tar xvjf gcc-4.8.5.tar.bz2 
**5. Download additional requirements for GCC.**

GCC requires some additional packages to build, so we'll make sure these are available in GCC's source tree. Note that different GCC versions might require different versions of these packages, so if you're building a different version of GCC than 4.8.5, please check its requirements and adjust the commands below as needed.

    $ cd gcc-4.8.5
    $ for prereq in mpfr-2.4.2 gmp-4.3.2; do curl -o $prereq.tar.bz2 ftp://gcc.gnu.org/pub/gcc/infrastructure/$prereq.tar.bz2 && tar xjf $prereq.tar.bz2 && ln -sf $prereq ${prereq%%[^a-z]*}; done
    $ for prereq in mpc-0.8.1; do curl -o $prereq.tar.gz ftp://gcc.gnu.org/pub/gcc/infrastructure/$prereq.tar.gz && tar xzf $prereq.tar.gz && ln -sf $prereq ${prereq%%[^a-z]*}; done
    $ cd ..

**6. Create a build directory for GCC next to its source tree.**

    $ mkdir gcc-4.8.5-build && cd gcc-4.8.5-build
**7. Run GCC's configure step.**

We're assuming that you have Xcode 3.2 installed in /Applications. Please verify that the path to Xcode's SDKs directory is correct! We're also telling the configure step to install GCC in a directory 'toolchains/gcc-4.8.5'. If you prefer to install GCC in a different folder, this is the time to change it.

    $  ../gcc-4.8.5/configure --prefix=$HOME/toolchains/gcc-4.8.5 --enable-languages=c,c++ --with-sysroot=/Applications/Xcode/SDKs/MacOSX10.6.sdk

**8. Build GCC.**

Assuming the previous step was successful, build GCC now. This might take a while.

    $ make

**9. Install GCC.**

    $ make install

# Finishing

If all commands were successful, you now have a C++11 compiler capable of building CMaNGOS on your system!

Now is a good time to do a quick test and verify that you can actually run it (change the path accordingly if you've changed the installation folder in step 7):

    $ ~/toolchains/gcc-4.8.5/bin/g++ --version

If GCC prints its version, you can clean up the temporary files and folders if you want, by deleting the 'src' folder in your home folder.