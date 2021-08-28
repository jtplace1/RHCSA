
	- groupadd
	- /etc/profile





| **Create, delete, and modify local user accounts** |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| /etc/skel                              | When a user is created files from this folder will be copied to the user folder |
| /etc/passwd                            | **Home directory**: The absolute path to the directory the user will be in when they log in. If this directory does not exists then users directory becomes / **Command/shell**: The absolute path of a command or shell (/bin/bash). Typically, this is a shell. Please note that it does not have to be a shell. For example, sysadmin can use the nologin shell, which acts as a replacement shell for the user accounts. If shell set to **/sbin/nologin** and the user tries to log in to the Linux system directly, the /sbin/nologin shell closes the connection. |
| chfn                                   | Change personal information (5th field /etc/passwd)          |
| Usermod -L \<username\>                | Lock a user                                                  |
| Usermod -U \<username\>                | Unlock a user                                                |
| Usermod -d \<username\>                | Change the default home directory (with -m : move the current directory of that user) |
| Userdel -r                             | Deleting a user including all the files (homefolder)         |
| Useradd \<username\>                           | Adding a user                                                |




| **Change passwords and adjust password aging for local user accounts** |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| Passwd \<username\>                    | Creating a password for a user                               |
| Passwd -d \<username\>                 | Deleting a user password                                     |
| Passwd -e \<username\>                 | Change password as expired                                   |
|                                        |                                                              |
| Chage -l \<username\>                  | Showing a account’’s password status, human readable (better then passwd -S) |
| Chage \<username\>                     | Changing account password settings                           |
             

| **Create, delete, and modify local groups and group memberships** |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| Groups \<username\>                    | Showing where a user is member off                           |
| Groupadd \<group name\>                | Adding a group                                               |
| /etc/gshadow                           | File where group passwords are stored                        |
|                                        |                                                              |
| Groupmod \<group name\>                | Modify a group                                               |
| Groupdel \<group name\>                | Deleting a group                                             |
| usermod -g                             | Changing users group                                         |
| Gpasswd                                | Change a group password                                      |
| /etc/group                             | Group name Encrypted password for the group, if “x” -> /etc/gshadow has the password Group id Comma separated list of al the users |



| **Configure superuser access** |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| /etc/login.defs                        | Changing global variables such as password age etc.          |



| **User creation/ Group creation etc.** |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| Useradd -D                             | Show the default parameters that are used when useradd command has been used |
| **Getent**                             | Searching for a term in a administrative database            |
| Getent passwd root                     | Showing info about a user in the passwd file                 |
| Getent shadow root                     | Showing info about a user in the show file                   |
|                                        |                                                              |
                           |                                                              |



| **Creating a user / group**                    |                                                              |
| ---------------------------------------------- | ------------------------------------------------------------ |
| /etc/login.defs                                | Config file that has been used to store default variables for users etc. |
| Passwd \<username\>                            | Changing the password of the user                            |
| Usermod -aG \<groupname\> \<username\>         | Append a user to a group                                     |
| Usermod \<username]> -d \<newhomedirectory\>   | Changing the default homedirectors for a user **excluding** copying the old homefolder data! |
| Usermod \<username\> -m -d <newhomedirectory\> | Changing the default homedirectors for a user **including** copying the old homefolder data! |


