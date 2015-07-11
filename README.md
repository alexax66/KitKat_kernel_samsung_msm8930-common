################################################################################

1-1. How to Build kernel
	- get Toolchain
		From android git server , codesourcery and etc ..
		 - arm-eabi-4.7
		
	- edit Makefile
		edit "CROSS_COMPILE" to right toolchain path(You downloaded).
		  EX)  export CROSS_COMPILE= $(android platform directory you download)/android/gcc/prebuilts/linux-x86/arm/arm-eabi-4.7/bin/arm-eabi-
       		  Ex)  export CROSS_COMPILE=/usr/local/toolchain/arm-eabi-4.7/bin/arm-eabi-          // check the location of toolchain
		$ export CROSS_COMPILE=(compiler path)
		$ export ARCH=arm
		$ mkdir output
		$ make -C $(pwd) O=output msm8930_serrano_defconfig VARIANT_DEFCONFIG=msm8930_serrano_eur_lte_defconfig SELINUX_DEFCONFIG=selinux_defconfig
		$ make -C $(pwd) O=output 
		$ cp output/arch/arm/boot/zImage arch/arm/boot/zImage

1-2. excute build command after edit Toolchain path.
          ./build_kernel.sh

2. Output files
	- Kernel : output/arch/arm/boot/zImage
	- module : output/drivers/*/*.ko

3. How to Clean	
		$ cd output
		$ make clean
################################################################################
