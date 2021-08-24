Understand and use essential tools

# Understand and use essential tools


- Access a shell prompt and issue commands with correct syntax

| **Command**                                            |                                                              |
| ------------------------------------------------------ | ------------------------------------------------------------ |
| w                                                      | Show who is logged in to the machine and what they are doing |
| wc                                                     | Counting rows, words, bytes                                  |
| Split -l 2                                             | Split files with 2 rows each                                 |
| Head                                                   | Showing the first 10 lines of a file (-n 2 for last 2 lines etc) |
| Tail                                                   | Showing the last 10 lines of a file (-n 2 for last 2 lines etc) |
| Diff                                                   | Show differences                                             |
| Sort                                                   | Sorting the output                                           |
| Nl                                                     | Numbering the lines in the output                            |
| ping [google.com](http://google.com) \| tee output.txt | Write the STDOUT to a file and also shows the STDOUT         |
| Cut                                                    |                                                              |
| Set                                                    | Print all the environment variables                          |
| Uniq                                                   | Finding uniq file lines                                      |
| jobs                                                   | Show all background tasks running in the current shell       |






| **Use input-output redirection (>, >>, |, 2>, etc.)** |     |
| -------- | ------------------------------------------------ |
| >        | Overwrite file                                   |
| >>       | Appending to a file                              |
| 2>       | Redirect all errors to a file (overwrite)        |
| 2>>      | Redirect all errors to a file (appending)        |
| &>       | Redirect output and errors to a file (overwrite) |
| &>>      | Redirect output and errors to a file (apending)  |
| <        | is used to redirect the input of a command.      |

 
	- head / tail
	- less / more

- Use grep and regular expressions to analyze text
	- awk
	- wc
		
| **Grep**                                 |                                                              |
| ---------------------------------------- | ------------------------------------------------------------ |
| Grep \<pattern\> \<filename\>            | Search for a keyword in a file                               |
| Grep -lr cron /etc                       | Search for patterns in all the files in a folder (including all subdirectories because of -r) |
| **Egrep (Extended Regular Expressions)** |                                                              |
| Egrep -I ‘hello.*world’ \<filename\>     | -I : ignore case sensitive ‘hello.*world’: hello and world in it |
| Egrep -I ‘hello\|world’ \<filename\>     | -I : ignore case sensitive ‘hello.*world’: hello or world in it |
| Egrep -v ‘hello\|world’ \<filename\>     | -v: everything that does not contain hello or world in it    |
| **Fgrep (Fixed, same as Grep -f)**       |                                                              |


**Regular Expressions**  |                                                              |
| ------------------------ | ------------------------------------------------------------ |
| \<keyword\>$ bijv: test$ | Matches and of the the string                                |
| ^\<keyword\> bijv: ^test | Matches start of string and represents characters not in the string. |
| [a-z ]     [0-9]               | Matches on range                                       |
|   ?                       |                 match any single charachter                                             |
|[abc]|match any one of the charachters in the list, case sensitive.|
|[^abc]|matches any one charachter except those in the list case sensitve|





| **Access remote systems using SSH**         |                                                           |
| ------------------------------------------- | --------------------------------------------------------- |
| Ssh -I \<identity file\>                    |                                                           |
| Ssh -X \<ip address\>                       | Connecting to a remote ssh server with GUI / Terminal Gun |
| ssh-add -l                                  | List all the keys from the agent                          |
| Ssh-add -D                                  | Delete all the keys from the SSH Agent                    |
| Scp test.txt 192.168.0.1:/etc/home/test.txt | Copying a file from localhost to a remote server          |
|                                             |                                                           |
| Ssh-keygen                                  |                                                           |
|                                             |                                                           |
| ~/.ssh/authorized_keys                      | Location where it stores it authorised keys               |
|                                             |                                                           |
| **Key-Based Authentication SSH**                             |                                                     |

| Ssh-keygen -t rsa -b 4096                                    | Creating a key pair (private and public) in the root folder ~/.ssh |
| Ssh folder 700                                               |                                                              |
| Contents in ssh folder 600                                   |                                                              |
| Ssh-copy-id [root@192.168.82.128](mailto:root@192.168.82.128) | Copy the public key to a different host                      |


	- /etc/ssh/sshd_config
	- systemctl status sshd
	- journalctl -u sshd -r 
	- scp
	- sftp
- Log in and switch users in multiuser targets
-
- Archive, compress, unpack, and uncompress files using tar, star, gzip, and bzip2

| **TAR**                |                                                              |
| ---------------------- | ------------------------------------------------------------ |
| -t                     | Shows the full archive                                       |
| **ZIP**                |                                                              |
| Zip test.zip file1.txt | Zipping a file                                               |
| **Gzip**               | Open source zip file format                                  |
| Tar -czvf              | -c = create -z = gzip -v = verbose (display each file name) -f = file |
| Tar -xzvf              | -x = extract -z = gzip -v = verbose (display each file name) -f = file |
| **Bzip2**              | Higher compression then Gzip                                 |
| Tar -cjvf              | -c = create -j = bzip2 -v = verbose (display each file name) -f = file |
| Tar -xjvf              | -x = extract -j = bzip2 -v = verbose (display each file name) -f = file |
| **Xz**                 | Highest compression but slower                               |
| tar -cJvf              | -c = create -J = XZ -v = verbose (display each file name) -f = file |
| Tar -xJvf              | -x = extract -J = XZ -v = verbose (display each file name) -f = file |
	
	- star
 
- Create and edit text files
	- vim
	- touch

| **Sed (change words)**       					|	                                |
| -----------------------------------  | ------------------------------- |
| Sed ’s/parttime/fulltime/‘ team      | Change every word from parttime to fulltime (s stands for substitution ofwel vervangen) (display it, not changing the original file) |
| Sed ‘/fulltime/w fulltime.txt’ team            | Write every line that has the word fulltime in it to a new file fulltime.txt (display it, not changing the original file) |
| Sed ‘0,/parttime/s/parttime/promotion’ team    | Change the first parttime with to promotion (display it, not changing the original file) |
| Sed -i ‘0,/parttime/s/parttime/promotion’ team | Change the first parttime with to promotion (change it, changing the original file) |
			




- Create, delete, copy, and move files and directories
	- mv
	- cp
	- rm
	- find
	- ls
	- pwd
	- mkdir
	- mktemp
	- rmdir
	- which
	- ~

| **Create hard and soft links**     |                                     |
| -------------------------------- | ----------------------------------- |
| Ln [filename] [hardlink]         | Creating a hardlink                 |
| Ln -s [filename] [symbolic link] | Creating a softlink / symbolic link |
|                                  |                                     |
|                                  |                                     |



-  List, set, and change standard ugo/rwx permissions
	- umask
	- chmod
	- chgrp
	- chown
	- 
- Locate, read, and use system documentation including man, info, and files in /usr/share/doc
	- man
	- info
	- whatis
	- ls /usr/share/doc/ntp/*



| **Find files**         |                                      |
| ---------------------- | ------------------------------------ |
| Locate                 |                                      |
| Locate \<search item\> |                                      |
| Updatedb               | Updates the locate database          |
| Find /etc -name “motd” | Finding files with the motd included |


| **Find**                                          |      |
| ------------------------------------------------- | ---- |
| find / -user jan -exec tar -cvzf file.tar.gz {} + |      |
| find / -user peter -exec cp {} /root/backup \;    |      |


| **Archiving**                        | **Description**                          |
| ------------------------------------ | ---------------------------------------- |
| Creating a iso from a file or CD-ROM | sudo dd if=/dev/cdrom of=/tmp/cdimg1.iso |
|                                      |                                          |


| **File management**  |                                                        |
| -------------------- | ------------------------------------------------------ |
| Ls -R                | Show all files in a directory including subdirectories |
| Cp -R /etc /home/dir | Copies all the files including the subdirectories      |
|                      |                                                        |
|                      |                                                        |


