Title: Directory Creation with Group-Based Access Control

Problem Statement:

Create a directory named admins under /home with the following requirements:

	• The directory must belong to the group admin.
 
	• Only members of the admin group should have read and write access to it.
 
	• All other users should not be allowed to access the directory.
 
	• Ensure that any files created inside the directory by group members automatically inherit the admin group ownership.
.

Step

	1. Navigate to home directory and create admins directory
	
		○ cd /home
		○ mkdir admins

	2. Change the directory group name
	
		○ chgrp admin admins

	3. Change the access right 
	
		○ chmod 770 admins

	4. Change the access right  so group members automatically inherit the admin group
	
		○ chmod g+s admins
