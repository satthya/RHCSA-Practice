Title:  Daily Scheduled Task Using Cron


Problem Statement:

You are required to configure an automated task on a Linux system using cron. The task must execute the following command:

	• echo hello

This command should run every day at exactly 14:23 (2:23 PM). Ensure that the cron job is set up correctly so that it runs without requiring manual intervention each day.



Step

	1. Check if the cronie package is installed. If not, install it.
	
		a. rpm -qa | grep cronie
		b. yum install cronie -y

	1. Start and enable the cron service.
	
		a. systemctl enable crond.service
		b. systemctl start crond.service
	
	2. Edit the crontab to schedule the task.
	
		a. crontab -e
			i. 23 14 * * * echo hello

	4. Confirm the cronjob.
	
		a. crontab -l
