Title:  Find and Write Matching Lines to Another File


Problem Statement:

You are tasked with processing the file /etc/testfile and finding all lines that contain the string abcde.
The entire line containing abcde must be written to a new file /tmp/testfile.

Ensure that:
	• Only lines containing the exact string abcde are selected.
	• The sequence of lines in /tmp/testfile is the same as in /etc/testfile.
	• No extra lines or content should be added.

Use appropriate Linux commands to accomplish this task efficiently.


Step

grep 'abcde' /etc/testfile > /tmp/testfile