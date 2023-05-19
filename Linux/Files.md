1. Create a new file and write something into it `echo something > file.fileExtension`
2.  Print permissions of a file `ls -l filename`
	 An example of the permissions is `-rwxr--r--`  
	 If the first letter is `d` it means this object is a directory otherwise is a file.  
	 The next 9 letters conclude three sections of 3 letters in each. The sections are the user owning the file, the group owning the file and others, respectively.  
	 The letters, `w` is for writing, `r` for reading and `x` for executing the file.
3. Change permission of a file for a user is by `+` or `-` option in `chmod` command. Add execution permission to the **user** `chmod u+x filename`
 4. 
	 