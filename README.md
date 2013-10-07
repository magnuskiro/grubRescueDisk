grubRescueDisk
==============

USB Rescue disk with multiple Linux live cds and install partitions. 

## Description
I now have a usb drive with three different linux iso installs on it. 

I partitioned the device with gparted, into 4 partitions, grub, mint 15, lmde,
ubuntu server. 

The install iso's are available from the maintainer sites. ubuntu.com and
linuxmint.com. 

Then i used unetbootin to write the iso images to partitions. 

Continuing to do the grub configuration. See /boot/grub/grub.cfg.
* Create grub config with the first grub command.
* Writing the configuration to the device with the second command. 

The files in this repo is the grub partition. 

## Grub commands
* Creates a separate config folder on given device. 
	* `sudo grub-mkconfig -o /media/usb/boot/grub/grub.cfg`

* Installs grub on the MBR of the selected device. 
	* `sudo grub-install --root-directory=/media/usb /dev/sdd`

## Useful commands and one-liners.
* mount - edit - unmount : for testing
  sudo mount /dev/sdd1 /media/usb && vi /media/usb/boot/grub/grub.cfg && sudo umount /media/usb
* General mounting  
 sudo mount /dev/sdd3 /medias/usb2
* Partitioning tool
 sudo gparted
* iso writer, dd or maybe cat can be used.
 sudo unetbootin 

## References / Resources
* Grub Manual
[http://www.gnu.org/software/grub/manual/grub.html#Making-a-GRUB-bootable-CD_002dRO]

* Good guides to the grub commands. Really helpful. 
[http://members.iinet.net/~herman546/p20/GRUB2%20Bash%20Commands.html#grub-mkconfig]

* Getting a copy of the partition table. 
[http://blog.dhampir.no/content/save-and-restore-partition-tables-with-sfdisk]

## Todo
* Update the config to use iso images. This makes it easier to upgrade the
  versions later.  
