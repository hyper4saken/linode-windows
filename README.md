## Windows Installation on Linode

Assume u are using or create new Linode with Linux system , for example, Ubuntu Dist.

- Power down your Ubuntu Linode server, then free some disk space for new disk from `/dev/sda` (Ubuntu) by resize at Storage Tab in Linode Manager ,then Add New disc, Label it window with `ext4` and set disk size u like, and then add new configuration with full virtualization, boot option , choose direct disk ,block device assignment at `/dev/sda` select window

- Edit existing Ubuntu configuration at Configuration Tab and add block device at `/dev/sdc` select window

- Reboot to Ubuntu, then install woeusb program on any Linux shell type command once u are at Linux shell

`root#lsblk`

> u will see /dev/sda, /dev/sdb (SWAP), /dev/sdc disk

https://www.linuxuprising.com/2020/10/how-to-make-bootable-windows-10-usb-on.html

Then type command to install woeusb
1- `wget https://raw.githubusercontent.com/WoeUSB/WoeUSB/master/sbin/woeusb -O /tmp/woeusb`
2-`sudo install /tmp/woeusb /usr/local/bin`
3- `apt-get install wimtools`
4- `wget http://the-path-for-your window.iso-file-location`

> Or you can use you custom windows like using Winscp/filezilla to upload iso

5- `sudo woeusb --device <your file="" for="" iso="" location="" name="" path="" window=""> /dev/sdc --target-filesystem ntfs</your>`

now your window.iso is already installed at /dev/sdc
6-Power off your Linode
7- Go back Linode at your new configuration with label "window - Direct disk" at Configuration Tab, then click boot button at right hand side
7- go GLish console, u will see window is activating and ready for installation

Note:
At Ubuntu Configuration, Disk, /dev/sdc is equal to "Window- Direct Disk" configuration, Disk, /dev/sda. If u won't use woeusb to install window anymore, u can remove /dev/sdc block device in Ubuntu configuartion .Now you can boot the installed window at /dev/sda at "WIndow- Direct Disk" configuration by click boot button.

The method can install all window versions iso(XP,7,8,10,etc) on Linode just for testing purpose only.