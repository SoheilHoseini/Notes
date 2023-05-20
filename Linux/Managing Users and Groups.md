#### Users
1. Add a new user `useradd username`  
	 1.1. Another command is `adduser username` which is more interactive and we can set more information about the user at the time of creating it  
2. Print info of all users; Go to the home directory and then `cat /etc/passwd`
3. Passwords of all users (only accessible to the root user) `cat /etc/shadow`
4. Delete a user `userdel username`

#### Groups
We can use groups to control the permission of all users in the group. Every user at the time it is being created, is added to a **primary** group with the name of the user. But the user could be added to multiple **supplementary** groups in the future. When the user creates a file, ownership of it is for the primary group.
1. Add a new group `addgroup groupname
2. Add user to a supplementary group `usermod -G gName username`
3. See all groups of a user `groups username`

