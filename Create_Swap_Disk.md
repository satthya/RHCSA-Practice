Title:Creating an Additional 2GB Swap Partition That Persists Across Reboots Without Affecting the Original Swap


problem statement:

The system currently has a default swap partition configured. However, due to increased memory usage by 
applications, an additional 2GB swap space is required. The new swap partition must:

	• Be created and enabled alongside the existing swap.

	• Be persistent across system reboots.

	• Not interfere with or replace the original swap configuration.

The solution involves creating a dedicated swap partition, enabling it, updating system configuration, and verifying its functionality.



Step:

	1. Check for available disk

			○ lsblk
		
	2. Create Swap Partition

			○ fdisk /dev/sdb
	
		Then inside fdisk:-
	
			○ n         :-  New partition
		
			○ p         :- primary
		
			○ 1         :- partition number
		
			○ Enter     :- accept default first sector
		
			○ +2G       :- set size to 2GB
		
			○ t         :- change partition type
		
			○ 82        :- linux swap
		
			○ w         :- write disk

	3. Format the partition to swap

			○ mkswap /dev/sdb1
		
			○ swapon /dev/sdb1


	4. Ensure the swap disk persist across reboot.

			○ vi /etc/fstab
		
			○ UUID=334058dd-ee3c-4e3e-99e2-d2bfe37d3d04 /swap swap    defaults        0       0
