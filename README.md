Overclocked realtime kernel sources for LF2000 devices for use with retroleap

Overclocks the CPU in Leapfrog devices with LF2000 CPUS, also enables realtime support which also has a small performance increase.

This kernel can only be built with the RetroLeap buildroot or an exremely ancient GCC

The RetroLeap buildroot is here https://github.com/mac2612/retroleap.git

You'll want to use the source code options and point the menuconfig to my this git repo, the prebuilt releases use the stock RetroLeap kernel

For SD card, NTFS, FAT32, and Swap support, you'll want to use my kernel config file here https://github.com/DCFUKSURMOM/retroleap-configs.git My buildroot config and the original kernel patch files are also here.

If you use my buildroot config it'll automatically point the buildroot to my kernel. As well as enable useful tools
like nano, bash, file, and htop.
