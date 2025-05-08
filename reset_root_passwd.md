Title: Resetting Root Password on RHEL 9 / CentOS 10 via Single-User Mode

Problem:

The system administrator forgot the root password on a RHEL 9 (or CentOS 10) machine and was unable to perform administrative tasks. Standard emergency mode was prompting for the root password, preventing access.



Troubleshooting/Diagnose

	1. Rebooted the system and interrupted GRUB boot by pressing e on the default entry.

	2. Located the line beginning with linux or linuxefi.

	3. Modified the line:

		○ Append rw init=/bin/bash at the end
	
	4. Press CTRL + X to boot

	5. Reset the password

		○ passwd root
	
	6. touch /.autorelabel

	7. Rebooted the system

	8. exec /sbin/init