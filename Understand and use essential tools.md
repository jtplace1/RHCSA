Understand and use essential tools

# Understand and use essential tools


| **Use input-output redirection (>, >>, 2>, etc.)** |        |
| -------- | ------------------------------------------------ |
| >        | Overwrite file                                   |
| >>       | Appending to a file                              |
| 2>       | Redirect all errors to a file (overwrite)        |
| 2>>      | Redirect all errors to a file (appending)        |
| &>       | Redirect output and errors to a file (overwrite) |
| &>>      | Redirect output and errors to a file (apending)  |
| <        | is used to redirect the input of a command.      |

 
		
| **Use grep and regular expressions to analyze text**           |                                        |
| ---------------------------------------- | ------------------------------------------------------------ |
| **Grep**                                 |                                                              |
| Grep \<pattern\> \<filename\>            | Search for a keyword in a file                               |
| Grep -lr cron /etc                       | Search for patterns in all the files in a folder (including all subdirectories because of -r) |
| **Egrep (Extended Regular Expressions)** |                                                              |
| Egrep -I ‘hello.*world’ \<filename\>     | -I : ignore case sensitive ‘hello.*world’: hello and world in it |
| Egrep -I ‘hello\|world’ \<filename\>     | -I : ignore case sensitive ‘hello.*world’: hello or world in it |
| Egrep -v ‘hello\|world’ \<filename\>     | -v: everything that does not contain hello or world in it    |
| **Fgrep (Fixed, same as Grep -f)**       |                                                              |
|**Regular Expressions**  |                                                              |
| \<keyword\>$ bijv: test$ | Matches and of the the string                                |
| ^\<keyword\> bijv: ^test | Matches start of string and represents characters not in the string. |
| [a-z ]     [0-9]               | Matches on range                                       |
|   ?                       |                 match any single charachter                                             |
|[abc]|match any one of the charachters in the list, case sensitive.|
|[^abc]|matches any one charachter except those in the list case sensitve|





| **Access remote systems using SSH**         |                                                           |
| ------------------------------------------- | --------------------------------------------------------- |
|  /etc/ssh/ssh_config			      |		Change system wide config			  |
| ~/.ssh/config				      |		Set user ssh config				  |
| Ssh -I \<identity file\>                    |                                                           |
| ssh-add -l                                  | List all the keys from the agent                          |
| Ssh-add -D                                  | Delete all the keys from the SSH Agent                    |
| Scp test.txt 192.168.0.1:/etc/home/test.txt | Copying a file from localhost to a remote server          |
| Ssh-keygen                                  |                                                           |
| ~/.ssh/authorized_keys                      | Location where it stores it authorised keys               |
| **Key-Based Authentication SSH**            |			                                          |
| Ssh-keygen -t rsa -b 4096                   | Creating a key pair (private and public) in the root folder ~/.ssh |
| Ssh-copy-id [root@192.168.82.128] 	      | Copy the public key to a different host |


	- journalctl -u sshd -r 
	
	

| **Archive, compress, unpack, and uncompress files using tar, star, gzip, and bzip2** ||
| ---------------------- | ------------------------------------------------------------ |
| **Tar**                |                                                              |
| -t                     | Shows the full archive                                       |
| **Gzip**               | Open source zip file format                                  |
| Tar -czvf              | -c = create -z = gzip 					|
| Tar -xzvf              | -x = extract 						|
| **Bzip2**              | Higher compression then Gzip                                 |
| Tar -cjvf              | -j = bzip2 							|
| Tar -xjvf              | 	 							|
| **Xz**                 | Highest compression but slower                               |
| tar -cJvf              | -J = XZ	 						|
| Tar -xJvf              | 								|
	
	
|**Create and edit text files**	       |     			         |
| -----------------------------------  | ------------------------------- |
| **Sed (change words)**       	       |	                         |
| Sed ’s/parttime/fulltime/‘ team      | Change every word from parttime to fulltime (s stands for substitution ofwel vervangen) (display it, not changing the original file) |
| Sed ‘/fulltime/w fulltime.txt’ team            | Write every line that has the word fulltime in it to a new file fulltime.txt (display it, not changing the original file) |
| Sed ‘0,/parttime/s/parttime/promotion’ team    | Change the first parttime with to promotion (display it, not changing the original file) |
| Sed -i ‘0,/parttime/s/parttime/promotion’ team | Change the first parttime with to promotion (change it, changing the original file) |
| wc                                                     | Counting rows, words, bytes                                  |
| Split -l 2                                             | Split files with 2 rows each                                 | | Diff                                                   | Show differences                                             |
| patch 						 | takes a file containing a difference listing produced by the diff program and applies those differences to the original files |
| Sort                                                   | Sorting the output                                           |
| Nl                                                     | Numbering the lines in the output                            | | Cut                                                    |                                                              |
| Set                                                    | Print all the environment variables                          |
| Uniq                                                   | Finding uniq file lines                                      | | awk                 				   |								  |			


| **Create, delete, copy, and move files and directories**  |                   |
| -------------------- | ------------------------------------------------------ |
| Ls -R                | Show all files in a directory including subdirectories |
|     ls-al            | Lists files and directories with detailed information like permissions,size, owner, etc.    |
| Cp -R /etc /home/dir | Copies all the files including the subdirectories      |
| cat file1 file2 > file3   |  Joins two files (file1, file2) and stores the output in a new file (file3) |
|    find . -type      |                                                        |
|       less           |                                                        |
| Tail                 | Showing the last 10 lines of a file (-n 2 for last 2 lines etc) | 
| Head                 | Showing the first 10 lines of a file (-n 2 for last 2 lines etc) |
|                      |                                                        |



| **Create hard and soft links**   |                                     |
| -------------------------------- | ----------------------------------- |
| Ln [filename] [hardlink]         | Creating a hardlink                 |
| Ln -s [filename] [symbolic link] | Creating a softlink / symbolic link |


| **List, set, and change standard ugo/rwx permissions**   |             |
| -------------------------------- | ----------------------------------- |
|        umask 777		   |  default file mask 666   		 |
|  				   |  default directory mask 777	 |
|	/etc/profile		   |		login shells		 |
|	/etc/bashrc		   |		interactive shells	 |  
	- 
	- chmod
	- chgrp
	- chown
	- suid
	- gsuid
| **Locate, read, and use system documentation including man, info, and files in /usr/share/doc** |                      |
| -------------------------------- | ----------------------------------- |
| man -k 		           | Search the short  manual  page  descriptions  for keywords and display any matches  |
| 					 | 				 |
	
	- man
	- info
	- whatis
	- ls /usr/share/doc/ntp/*



| **Find files**         |                                      |
| ---------------------- | ------------------------------------ |
| Locate   file.txt      |                                      |
| Updatedb               | Updates the locate database          |
| **Find**               |				        |
| find /etc -name “motd” | Finding files with the motd included |
| find / -user jan -exec tar -cvzf file.tar.gz {} + |   	|
| find / -user peter -exec cp {} /root/backup \;    |      	|
| which 		 |  locate the executable file associated with the given command |





