Title: User Account Creation with Group and Shell Configuration

Problem Statement:

Create three users on the system with the following specifications:

	• Users: sam, nayan, and tom
	• Add users sam and nayan to an additional group named admin
	• Set tom's login shell to a non-interactive shell
	
Ensure all users are created successfully and their configurations meet the specified requirements.

Step

	1. Create user
	
		○ useradd sam
		○ useradd nayan
		○ useradd tom
	
	2. Verify the User Exist
	
		○ cat /etc/passwd 

	2. Create group

		○ groupadd admin
	
	3. Validate the Group

		○ cat /etc/group
	
	4. Add Users to admin Group

		○ usermod -aG admin sam
		○ usermod -aG admin nayan
	
	5. Check Group Membership

		○ groups sam
		○ groups nayan
	
	6. Set tom's login shell to a non-interactive shell

		step1

		○ vi /etc/passwd
		○ tom:x:1002:1003::/home/tom:/bin/nologin
	
		step2
	
		○ usermod -s /sbin/nologin tom