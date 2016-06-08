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
    *  Distribution suite : jessie
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
