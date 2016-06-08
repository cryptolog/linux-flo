Debian Stretch ARMHF tutorial

1. Need software:
  * Linux Deploy
  * bVNC or ConnectBot

2. Download rootfs steps:
  * Install Linux Deploy
    - install busybox
    - click on arrow in linux deploy
    - Select:
    *  Distribution : Debian
    *  Distribution suite : stretch
    *  Architecture : armhf
    *  Instalation path : /sdcard/root.img
    *  User password : android
    *  Desktop environment : Xterm
    *  Select components : select all
    * Select install and wait for <<< install
  * Open bVNC
    *  VNC Server : localhost
    *  VNC Username : android
    *  VNC Password : android
  * If you are connected type:
    *  sudo passwd
    * toor
    * toor
    *  sudo apt-get install
    *  sudo apt-get install mate [lxde,xfce4,plasma-desktop,]
    *  
3. Kernel
  I use ElementalX for best CPU and GPU performance.
 * Download config and patches
 * root@porteus:# git clone https://github.com/Szybol7/linux-flo.git
 * Download ElementalX from https://github.com/flar2/flo/archive/ElementalX-5.00.zip
 * Extract archive using command:
 * root@porteus:# unzip flo-ElementalX-5.00.zip
 * Download gcc linaro from: https://releases.linaro.org/components/toolchain/binaries/4.9-2016.02/arm-linux-gnueabihf/gcc-linaro-4.9-2016.02-x86_64_arm-linux-gnueabihf.tar.xz
 * Extract archive using command:
 * root@porteus:# tar -C ./ -xpzvf ./gcc-linaro-4.9-2016.02-x86_64_arm-linux-gnueabihf.tar.xz
 * Copy config file:
 * root@porteus:# mv linux-flo/config flo-ElementalX-5.00/.config
 * Copy patch:
 * root@porteus:# mv linux-flo/flo-ElementalX-5.00.patch flo-ElementalX-5.00.patch
 Apply patch:
 * root@porteus:# cd flo-ElementalX-5.00
 * root@porteus:# patch -p1 < ../flo-ElementalX-5.00.patch

Open terminal in folder flo-ElementalX-5.00 and type:
* root@porteus:# export ARCH=arm
* root@porteus:# export SUBARCH=arm
* root@porteus:# export CROSS_COMPILE=../gcc-linaro-4.9-2016.02-x86_64_arm-linux-gnueabihf/bin/arm-linux-gnueabihf-
* root@porteus:# export PATH=../gcc-linaro-4.9-2016.02-x86_64_arm-linux-gnueabihf/bin/:$PATH

Time to compile kernel.
* root@porteus:# make -j3

Install modules and firmware:
* root@porteus:# make modules_install INSTALL_MOD_PATH=../modules && make firmware_install INSTALL_FW_PATH=../firmware

Kernel and modules is ready.
