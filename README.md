UBER LINARO MANIFEST
===========

I'm trying to make it easier for folks to build LINARO toolchains so I created this manifest. The method of building is the traditional aosp way but with ALL Linaro components/patches etc. There are many different script options with many different tunings availaible.  If you don't know which to use the generic arm-eabi-4.8, arm-eabi-4.9, arm-eabi-5.1 scripts will work fine. I also have included the latest gmp, cloog, isl, osl, mpc, and mpfr to bring the best level of stability/optimization possible.

Building an arm-eabi linaro toolchain is a simple process. All you have to do is run:

    repo init -u https://github.com/UBERTC/linaro-manifest.git -b master 

followed by

    repo sync

Also make sure to install dependencies (while you wait for it to sync)

    sudo apt-get install flex bison ncurses-dev texinfo gcc gperf patch libtool automake g++ libncurses5-dev gawk subversion expat libexpat1-dev python-all-dev binutils-static libgcc1:i386 bc pkg-config

**Note: I also have an entire android environment setup as well apart from these.  I currently use Ubuntu 15.04 repos on my build server.  You may be missing dependencies that already came preinstalled with my android environment setup.  I'll let you figure out what you need for any other distro you may be running. Usually though errors will tell you the dependency you are missing.**

Once you have everything synced locally go to the scripts directory and run any of the scripts. All scripts will checkout the needed GCC version before build so don't worry which branch you ran repo init with you can build them all using master branch.

When you finished running the script you will find a toolchain located wherever the script tells you it is found.  Usually the out directory which is created inside the folder where you ran the repo init command.

Enjoy!
