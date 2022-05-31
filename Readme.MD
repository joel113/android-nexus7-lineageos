# Install Lineage OS Android on a Nexus 7 device

https://lineageos.org/

https://download.lineageos.org/flox#!user

https://wiki.lineageos.org/devices/flox/install

## Unlocking the Bootloader

```
adb reboot bootloader

fastboot devices

fastboot oem unlock

```

## Install a custom recovery

```
adb reboot bootloader

fastboot devices

fastboot boot recovery.img

```

## EFS/Persist backup

```
dd if=/dev/block/mmcblk0p2 of=/sdcard/modemst1.img
dd if=/dev/block/mmcblk0p3 of=/sdcard/modemst2.img
dd if=/dev/block/mmcblk0p4 of=/sdcard/persist.img
exit
```

```
adb pull /sdcard/modemst1.img
adb pull /sdcard/modemst2.img
adb pull /sdcard/persist.img
```

## Repartition

```
adb sideload flo-deb_clamor_repartition_20201203.zip 
fastboot
fastboot devices
fastboot -w
```

## Install Lineage OS

```
adb sideload lineage-18.1-20220530-nightly-flox-signed.zip 
```

## Backup

```
adb pull /sdcard/ .
```


## Useful ADB commands

https://gist.github.com/joel113/94f59ef35840f92fbb2b16eeeab42816
