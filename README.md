Overclocked realtime kernel sources for LF2000 devices for use with retroleap

Overclocks the CPU in Leapfrog devices with LF2000 CPUS, also enables realtime support which also has a small performance increase.

The overclock patch is from mac2612 https://github.com/mac2612

The realtime patch is an old one from kernel.org archives that happened to be compatible

This kernel can only be built with the RetroLeap buildroot or an exremely ancient GCC

If you want a prebuilt kernel image go here https://github.com/DCFUKSURMOM/lf2000_kernel-rt-oc/releases/download/3.4.24-rt-oc-p2/lf2000_uImage

The RetroLeap buildroot is here https://github.com/mac2612/retroleap.git

You'll want to use the source code options and point the menuconfig to my this git repo, the prebuilt releases use the stock RetroLeap kernel

My prebuilt kernel as well as the default kernel config for my kernel (retroleap_lf2000_defconfig) have SD, Swap, and Fat32 support enabled

You'll need an SD card adaptor cartridge, there are a few out there already that should work fine but I'm in the process of designing my own specific for LF2000

You'll have to point buildroot to the where you saved the config file

My buildroot config and the original kernel patch files are also here https://github.com/DCFUKSURMOM/retroleap-configs.git

If you use my buildroot config it'll automatically point the buildroot to my kernel.

As well as enable useful tools like nano, bash, file, and htop.

You'll still have to point it to the kernel config though as it looks for it on my desktop by default and my desktop is obviously not going to be on someone elses system. I tried doing ~/Desktop (~ being an env variable the automatically finds the users desktop, but buildroot didnt seem to like it)

My buildroot config also looks for splash.png on the desktop, you'll have to point the buildroot to it like with the kernel config, or disable the option. 

splash.png is the splash screen shown by the kernel during boot. 

It can be whatever image you like, but its not recommended to go over 320x240 in resolution

The default splash image is located here https://github.com/DCFUKSURMOM/retroleap-splash-screen.git

The default splash image was created by Th3KillinJok3 https://github.com/Th3KillinJok3
