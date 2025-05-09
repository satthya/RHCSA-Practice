Title: Creating a 1 GiB Logical Volume 'lvnewlv' in Volume Group 'vgnewvg' on RHEL 9

Problem:

A system administrator needs to create a logical volume named lvnewlv with a size of 1 GiB inside an existing volume group called vgnewvg on a Red Hat Enterprise Linux 9 system.


Troubleshooting/Diagnose

	1. Check available volume groups and free space:
		
		○ vgs

	2. Create 1gb logical volume:

		○ lvcreate -L +1G -n lvnewlv vgnewvg

	3. Confirm the logical volume was created:
	
		○ lvs

Outcome:

A new logical volume named lvnewlv was successfully created inside the vgnewvg volume group using 1 GiB of space. It is now ready for formatting and mounting.