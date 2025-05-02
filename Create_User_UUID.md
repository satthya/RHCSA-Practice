Title:Create a User Named Alley with a Specific UID and Password


problem statement:

A new user account is required on the system for an employee named Alley. The account should meet the following requirements:

	• The username should be Alley

	• The User ID (UID) must be explicitly set to 1234

	• The account should be secured with the password Alley131

The solution must ensure the user is created correctly with the specified UID and that the password is securely set.



Step:

	Step

	1. Create the user with UID 1234

		○ useradd --uid 1234 Alley
	
	2. Verify the id

		○ id Alley
	
	3. Set the password

		○ passwd Alley

