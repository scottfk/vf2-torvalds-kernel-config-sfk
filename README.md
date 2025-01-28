# vf2-torvalds-kernel-config-sfk
My minimal .config to build Linus' kernel on and for VisionFive2.

I configured in only devices I know to be on the board based on how I use it.  If I've missed anything, please let me know and I will add it.
NB:  I tend to favor built-in over modules.  My mind can be changed on this, however.

I will update this on each RC, always saying "NO" to any new setting that is not relevant to the VF2.  Once a kernel version gets released, I will do a final build and from there create a new config file for the next version's first RC.

The config here will have been tested to have compiled on my VF2:

- Machine model: StarFive VisionFive 2 v1.3B
- OS (lsb_release --description): Ubuntu Plucky Puffin (development branch)
- Compiler: gcc (Ubuntu 14.2.0-12ubuntu1) 14.2.0
- Binary Utilities: binutils (Ubuntu 2.43.90.20250127-1ubuntu1) 20250127-1ubuntu1
- Boot device: MMC
- u-boot and spl from Ubuntu package u-boot-starfive:riscv64 version 2024.01+dfsg-5ubuntu3
- pahole: pahole (1.29-1ubuntu1) v1.29

How I build:

- git pull the latest sources immediately after Linus announces the RC/Release
- gmake -j5 mrproper to clean up after previous build
- copy this kernel config as .config in the top level of the kernel sources
- gmake -j5 oldconfig
- nohup make INSTALL_MOD_STRIP=1 BUILD_TOOLS=y -j5 bindeb-pkg &

