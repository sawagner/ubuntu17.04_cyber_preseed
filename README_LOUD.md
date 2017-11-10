Requirements:

1. Root access to a Linux machine (Sysstaff machines recommended)
 
2. A blank USB drive

Instructions:

1. Log in to a sysstaff machine which has 16.04 Xenial installed.


2. Download the Ubuntu net installation ISO for release 16.04.
   As of 7/2016, this ISO is located at:
   http://archive.ubuntu.com/ubuntu/dists/xenial/main/installer-amd64/current/images/netboot/mini.iso
   Time: Less than 2 Minutes


3. Download SSH Host Keys
   $ scp imageserver001:/export/installer-images/keys/keys.tar .
   Time: Less than a minute

4. Clone lxeus/lxerus-doc repository
   $ git clone git@webgit.lcseecloud.net:lxerus/lxerus-doc.git


5. Execute lbm-inject
     $ sudo lbm-inject -n -i /path/to/mini.iso -p /path/to/lxerus-doc/INSTALL/233AER-DESKTOP/233AER-DESKTOP.cfg -t /path/to/keys.tar
     Time: Less than a minute


6. Write the ISO file to a USB drive using the dd utility:

	$ sudo dd if=/path/to/lbm-inject.iso of=/dev/sdX

	...where X is the letter assigned to your USB drive.


7. Begin installation:

> - Insert USB drive into target machine
> - Turn off the machine
>>- Find the boot menu key (Option for Macs)
>>- Turn on the machine
		- Press boot menu key until boot menu appears
		- Select the USB drive
	- Select "Install" from the GRUB menu

	This will begin the Debian installer.


8. Pull the USB drive from the machine when the installer begins loading.


9. When asked for partitioning settings, select:

	Guided - use entire disk


10. Select the hard drive to install to.

11. Select "yes" to write changes to disk.

12. The installer will now complete.
