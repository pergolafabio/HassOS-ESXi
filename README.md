# HassOS-ESXi

Because there are no official HassOS releases for VMware ESXi, I decided to create one myself using the official VMDK release.

The official VMDK release is a VMware Workstation disk which can only be used in ESXi as an IDE harddrive.

The problem with that is that you cannot create a snapshot while the VM is running. It also means you cannot create a backup using backup software line Nakivo which I'm using to backup my VM's.

I've created this image by converting the VMDK file using StarWind V2V converter. After that I created a new VM in ESXi and imported the disk. I'm running ESXi 6.7.0 Update 1.

The result is a VM with a default of 2GB RAM end a 16GB HDD connected to to the VMware SCSI adapter instead of IDE. Also the network interface is of the VMXNET3 type instead of the E1000 you need to use with the official image.

I will soon try to create a wiki on how to import the VM, expand the disk, set a static IP and add a second network interface.