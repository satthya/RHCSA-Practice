Title:  Daily Scheduled Task Using Cron


Problem Statement:

You are tasked with finding all files owned by the user nayan across the system and copying them to the directory /opt/dir. While copying, ensure that the original folder structure is preserved, and any errors such as permission-denied should not be displayed.

You need to accomplish this using the appropriate Linux command, ensuring it works efficiently across the entire filesystem.



Step

	1. find the file and copy to dir
		a. find / -user nayan -type f -exec cp --parents {} /opt/dir/ \;

