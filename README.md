# vf2-torvalds-kernel-config-sfk
My minimal .config to build Linus' kernel on and for VisionFive2.

I configured in only devices I know to be on the board based on how I use it.  If I've missed anything, please let me know and I will add it.
NB:  I tend to favor built-in over modules.  My mind can be changed on this, however.

I will update this on each RC, always saying "NO" to any new setting that is not relevant to the VF2.  Once a kernel version gets released, I will do a final build and from there create a new config file for the next version's first RC.

The config here will have been tested to have compiled on my VF2:

- Machine model: StarFive VisionFive 2 v1.3B
- OS (lsb_release --description): Debian GNU/Linux forky/sid
- Compiler: gcc (Debian 15.2.0-12) 15.2.0
- Binary Utilities: binutils (GNU Binutils for Debian) 2.45.50.20251209-1
- Boot device: MMC
- pahole: pahole v1.31-1

How I build:

- git pull the latest sources immediately after Linus announces the RC/Release
- gmake -j5 mrproper to clean up after previous build
- copy this kernel config as .config in the top level of the kernel sources
- gmake -j5 oldconfig
- nohup make INSTALL_MOD_STRIP=1 BUILD_TOOLS=y -j5 bindeb-pkg &

*20250310:  Currently frozen at rc4 due to https://github.com/scottfk/vf2-torvalds-kernel-config-sfk/issues/4*
*20251026:  Big changes.  I've moved to Debian, as Ubuntu abandoned all RISC-V cores that actually/currently exist.  And I have restarted trying to pare down a minimal kernel from Debian's out-of-the-box config.
