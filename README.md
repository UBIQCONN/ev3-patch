
## EV3 Linux Source from
    1. PX30 Linux SDK :Provide by Rockchip. 
    2. EV3 Linux SDK:Provide by UTI
           
## EV3 SDK install steps
 Download Rockchip PX30 Linux SDK, please follow:
``` sh 
$ repo init  -u https://github.com/UBIQCONN/ev3.git -b linux -m px30_linux4.19_release.xml
$ repo sync -c 
$ export  PX30_SDK_PATH=`pwd`
$ cd ..
```
    
Command for patch EV3 package:
```sh
$ git clone https://github.com/UBIQCONN/ev3-patch.git
$ export PATCH_PATH=`pwd`/ev3-patch
$ cp ev3-patch/ev3-patch-apply  $PX30_SDK_PATH/.
$ cd $PX30_SDK_PATH
$ chmod a+x  ev3-patch-apply
$ ./ev3-patch-apply  $PATCH_PATH  px30_ev3_release
```
## EV3 SDK build steps
Please reference “Rockchip PX30 Linux SDK Release Note”’s chapter 7: SDK building Introduction, EV3’s DVT Board level configuration name is BoardConfig-px30-ev3-ddr3-dvt.mk
	Below is build package sample: 

Platform Configuation:
```sh
$  ./build.sh device/rockchip/px30/BoardConfig-px30-ev3-ddr3-dvt.mk
```
	
Build Buildroot, kernel and bootloader :
```sh
$  ./build.sh all	
```

Build Yocto and yocto image ’s kernel :
```sh
 $  ./build.sh yocto
```
	 
BoardConfig-px30-ev3-ddr3-dvt.mk is for DVT board
BoardConfig-px30-ev3-ddr3.mk is for EVT board

# EV3 image install
Please reference “Rockchip PX30 Linux SDK Release Note”’s chapter 8:Upgrade introdution.

              
