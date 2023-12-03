# MMI3G-HDD-Prep-Tool
QNX shell script to prepare a HDD/SDD device for MMI3GP.

QNX shell script mkmmi3gphdd prepares a new/unpartioned HDD/SDD for use in a Harman-Becker MMI3GP system.

Usage:

Copy the script to a QNX 6.5.0SP1 or later VM running in VMware Player.  chmod +x mkmmi3gphdd2

Attach a new or unpartitioned HDD/SDD to the VM as a UMASS device.  Use ls -o /dev/umass* to determine the umass NUMBER.

Run the script in the current working directory: ./mkmmi3gphdd2 UMASSNR [NAVCYL]

The script accepts up to two (2) command line arguments: the umass device NUMBER (for example, /dev/umass0, UMASSNR is '0') is required, followed by an optional NAV partition size (in cylinders); this value can be used to increase the size of the NAV parition for 60 GB devices.  The default value is 3590 cylinders (about 28.2 GB).  A recommended value for use with the EU nav database is 3700 cylinders.  Note that increasing the size of the NAV partition will decrease the size of the MEDIADISK (Jukebox) partition.

If the HDD/SDD device is not unpartitioned, the script will remind you to delete all partitions first with fdisk.

The size of the nav parition is determined by the size of the HDD/SDD: an 80 GB drive assumes the EU nav database size; a 60 GB drive assumes the US nav database size.  Smaller HDD/SDD devices are not supported by the script at this time.  QNX 6.5 and earlier VMs are unsupported.
