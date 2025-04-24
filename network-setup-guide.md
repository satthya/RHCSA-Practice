Title: Linux IP, Hostname, Gateway, DNS Setup

Problem:

Configure the following on your CentOS system:

	• Set the hostname to laptop-john.kl.example.com using:
	• Set the following network settings:
	
		○ IP Address: 172.24.40.40/24
		○ Gateway: 172.24.40.1
		○ DNS Server: 172.24.40.1

Method 1 : Using nmcli

	1. Set HostName
	
		○ hostnamectl set-hostname laptop-john.kl.example.com

	2. Check network interface name and status

		○ nmcli dev status



	3. Configure static IP Settings

		○ nmcli connection modify eth1 ipv4.addresses 172.24.40.40/24
		○ nmcli connection modify eth1 ipv4.gateway 172.24.40.1
		○ nmcli connection modify eth1 ipv4.dns 172.24.40.1
		○ nmcli connection modify eth1 ipv4.method manual
	
	4. Reactivate network interface
	
		○ nmcli connection down eth1
		○ nmcli connection up eth1

	5. Restart NetworkManager

		○ systemctl restart NetworkManager

Method 2 : Manual File Editing

	1. Set HostName

		○ vi /etc/hostname
			§ edit the configuration file with the hostname
	
	2. Configure Static IP via FIle

		○ cd /etc/NetworkManager/system-connections/
		○ ls   # (select the network interface)
		○ vi eth1.nmconnection
	
	

	3. Reactivate Network Interface

		○ nmcli connection down eth1
		○ nmcli connection up eth1

	4. Restart NetworkManager

		○ systemctl restart NetworkManager