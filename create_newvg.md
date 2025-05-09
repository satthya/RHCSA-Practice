Title: Creating a New Volume Group 'vgnewvg' with 4 GiB Size on RHEL 9

Problem:

A system administrator needs to create a new volume group named vgnewvg using 4 GiB of available disk space on a RHEL 9 system. 
This requires creating a partition, initializing it as a physical volume, and then using it to create the volume group.


Troubleshooting/Diagnose

	1. Check for available disks and partitions:
		
		○ lsblk

	2. Create a 4 GiB partition on an available disk (e.g., /dev/sda):

		○ fdisk /dev/sda

	3. Create a physical volume:

		○ pvcreate /dev/sda1
		
	4. Create the volume group:

		○ vgcreate vgnewvg /dev/sda1

	5. Confirm the volume gorup:
	
		○ vgs

Outcome:

A new volume group named vgnewvg was successfully created using a 4 GiB partition. It is now ready for use in logical volume creation.