# MMI3G-HDD-Prep-Tool
QNX shell script to prepare a HDD/SDD device for MMI3GP.

QNX shell script mkmmi3gphdd prepares a new/unpartioned HDD/SDD for use in a Harman-Becker MMI3GP system.

Usage:

Copy the script to a QNX 6.5.0SP1 or later VM running in VMware Player.  chmod +x mkmmi3gphdd

Attach a new or unpartitioned HDD/SDD to the VM as a UMASS device.  Use ls -o /dev/umass* to determine the umass NUMBER.

Run the script in the current working directory: ./mkmmi3gphdd UMASSNR

The script accepts a single command line argument: the umass device NUMBER (for example, /dev/umass0, UMASSNR is '0').

If the HDD/SDD device is not unpartitioned, the script will remind you to delete all partitions first with fdisk.

The size of the nav parition is determined by the size of the HDD/SDD: an 80 GB drive assumes the EU nav database size; a 60 GB drive assumes the US anv database size.  Smaller HDD/SDD devices are not supported by the script at this time.  QNX 6.5 and earlier VMs are unsupported.
