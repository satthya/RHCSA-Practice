Title: Enabling IPv4 Packet Forwarding Permanently on RHEL 9

Problem:

A system administrator needs to enable IPv4 packet forwarding on a RHEL 9 system to allow the machine to route traffic between networks. However, the change must persist across reboots.



Troubleshooting/Diagnose

	1. Verified current IP forwarding status
	
		Output was 0, indicating IP forwarding was disabled.
	
		○ cat /proc/sys/net/ipv4/ip_forward

	2. Open the system configuration file:

		○ vi /etc/sysctl.conf

	3. Add the line:

		○ net.ipv4.ip_forward = 1
		
	4. Apply the changes immediately:

		○ sysctl -p
