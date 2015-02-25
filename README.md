UBER LINARO MANIFEST
===========

I'm trying to make it easier for folks to build LINARO toolchains so I created this manifest. The method of building is the traditional aosp way but with ALL Linaro components/patches etc. I tuned these builds to cortex-a15 which works for krait cpus because that is what I use.  If you don't have a krait CPU navigate to build/Makefile.in after you sync and change --with-tune=cortex-a15 to the appropriate value.  You may also want to change the other values on that same line like --with-float=hard --with-fpu=neon-vfpv4 to the appropriate values before building as well.

Building an arm-eabi linaro toolchain is a simple process. All you have to do is run:

    repo init -u https://github.com/UBERTC/linaro-manifest.git -b master 

followed by

    repo sync

Also make sure to install dependencies (while you wait for it to sync)

    sudo apt-get install mercurial flex bison ncurses-dev texinfo gcc gperf patch libtool automake g++ libncurses5-dev gawk subversion expat libexpat1-dev python-all-dev binutils-static libgcc1:i386 bc

**Note: I also have an entire android environment setup as well apart from these.  I currently use Ubuntu 15.04 repos on my build server.  You may be missing dependencies that already came preinstalled with my android environment setup.  I'll let you figure out what you need for any other distro you may be running. Usually though errors will tell you the dependency you are missing.**

Once you have everything synced locally go to the scripts directory and run any of the scripts. All scripts will checkout the needed GCC version before build so don't worry which branch you ran repo init with you can build them all using master branch.

When you finished running the script you will find a toolchain located wherever the script tells you it is found.  Usually ~/uber_toolchain and labeled accordingly.

Enjoy!
