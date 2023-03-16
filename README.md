Overclocked realtime kernel sources for LF2000 devices for use with retroleap

Overclocks the CPU in Leapfrog devices with LF2000 CPUS, also enables realtime support which also has a small performance increase.

The overclock patch is from mac2612 https://github.com/mac2612

The realtime patch is an old one from kernel.org archives that happened to be compatible

This kernel can only be built with the RetroLeap buildroot (use "make lf2000_rt_defconfig to point the buildroot to my kernel)

The latest retroleap aplha has a prebuilt version of my kernel available, there is also one here https://github.com/DCFUKSURMOM/lf2000_kernel-rt-oc/releases/download/3.4.24-rt-oc-p2/lf2000_uImage

My prebuilt kernel (this includes the one in the latest retroleap alpha) has SD, Swap, and Fat32 support enabled

To use an SD card you'll need an SD card adapter cartridge, I've designed on that works but its not pre-assembled and can be pricy to put together, the most expensive part is the board shipping.

I don't see a dingle dime of the money, the board files are free, services like jlcpcb and pcbway are just expensive (especially if you go with full assembly)

Board files for my SD cart are here https://github.com/DCFUKSURMOM/LeapSD

If you are ballsy like me you can sacrifice the cartridge slot and hardwire an SD to Micro-SD adapter in like I did for the initial testing, however I plan on attempting to do a combo Wifi/SD cart in the future so I wouldnt recommend it

RETROLEAP BUILDROOT ENVIRONMENT REQUIRED BEYOND THIS POINT!! ADVANCED USERS ONLY!!

If you want to use my custom buildroot settings (which adds stuff like nano, htop, mc, nefoetch, and util-linux) build the kernel first using "make lf2000_rt_defconfig", then "make linux" 

If you want a custom splash screen, do "make menuconfig" before you do "make linux" and in the menuconfig settings go to the kernel settings and point the custom splash screen option to your image, the image should not be over 320x240.

A pre-made splash image is here https://github.com/DCFUKSURMOM/retroleap-splash-screen/raw/main/splash.png (created by Th3KillinJok3)

After pointing to the custom image save the settings and do "make linux" as normal

Then download my buildroot config from here https://raw.githubusercontent.com/DCFUKSURMOM/retroleap-configs/main/lf2000-buildroot-config and save it to your buildroot folder. remove the .config file and rename lf2000-buildroot-config to .config and do "make rootfs-tar" 

This will take a while to build as my config uses gcc12 (which is why you had to to the gcc4 only kernel first) and buildroot has to build a gcc12 cross compiler for arm. Its an extra step but allows much newer packages to be used than normal.

In the future I intend to find a prebuilt gcc12 arm cross compiler to get the build time back to a more normal level)

After you have both the kernel (will be named uImage) and rootfs.tar.gz, rename them to lf2000_uImage and lf2000_rootfs.tar.gz (or if you are using the latest sshflash comit, lf2000_rt_uImage and lf2000_rt_rootfs.tar.gz)
