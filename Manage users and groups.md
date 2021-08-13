Manage users and groups

# Manage users and groups

- Create, delete, and modify local user accounts
- Change passwords and adjust password aging for local user accounts
- Create, delete, and modify local groups and group memberships
	- groupadd
- Configure superuser access
	- su
	- /etc/profile





| **User creation/ Group creation etc.** |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| /etc/login.defs                        | Changing global variables such as password age etc.          |
| /etc/skel                              | When a user is created files from this folder will be copied to the user folder |









| **User creation/ Group creation etc.** |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| /etc/login.defs                        | Changing global variables such as password age etc.          |
| /etc/skel                              | When a user is created files from this folder will be copied to the user folder |
| /etc/passwd                            | Stores general user info: **Username**: It is used when user logs in. It should be between 1 and 32 characters in length. **Password**: An x character indicates that encrypted password is stored in /etc/shadow file. Please note that you need to use the passwd command to computes the hash of a password typed at the CLI or to store/update the hash of the password in /etc/shadow file. **User ID (UID)**: Each user must be assigned a user ID (UID). UID 0 (zero) is reserved for root and UIDs 1-99 are reserved for other predefined accounts. Further UID 100-999 are reserved by system for administrative and system accounts/groups. **Group ID (GID)**: The primary group ID (stored in /etc/group file) **User ID Info**: The comment field. It allow you to add extra information about the users such as user’s full name, phone number etc. This field use by finger command. **Home directory**: The absolute path to the directory the user will be in when they log in. If this directory does not exists then users directory becomes / **Command/shell**: The absolute path of a command or shell (/bin/bash). Typically, this is a shell. Please note that it does not have to be a shell. For example, sysadmin can use the nologin shell, which acts as a replacement shell for the user accounts. If shell set to **/sbin/nologin** and the user tries to log in to the Linux system directly, the /sbin/nologin shell closes the connection. |
| /etc/shadow                            | **Username** : It is your login name. **Password** : It is your encrypted password.  **Last password change (lastchanged)** : Days since Jan 1, 1970 that password was last changed **Minimum** : The minimum number of days required between password changes i.e. the number of days left before the user is allowed to change his/her password **Maximum** : The maximum number of days the password is valid (after that user is forced to change his/her password) **Warn** : The number of days before password is to expire that user is warned that his/her password must be changed **Inactive** : The number of days after password expires that account is disabled **Expire** : days since Jan 1, 1970 that account is disabled i.e. an absolute date specifying when the login may no longer be used. |
| /etc/group                             | Group name Encrypted password for the group, if “x” -> /etc/gshadow has the password Group id Comma separated list of al the users |
| /etc/gshadow                           | Group name Encrypted password for the group Group administrator Comma separated list of al the users |
| Useradd -D                             | Show the default parameters that are used when useradd command has been used |
| **Getent**                             | Searching for a term in a administrative database            |
| Getent passwd root                     | Showing info about a user in the passwd file                 |
| Getent shadow root                     | Showing info about a user in the show file                   |
|                                        |                                                              |
| Passwd \<username\>                    | Creating a password for a user                               |
| Passwd -d \<username\>                 | Deleting a user password                                     |
| Passwd -l \<username\>                 | Lock a user                                                  |
| Passwd -e \<username\>                 | Change password as expired                                   |
| Passwd -S \<username\>                 | Showing the status of the password                           |
|                                        |                                                              |
| Chage -l \<username\>                  | Showing a account’’s password status, human readable (better then passwd -S) |
| Chage \<username\>                     | Changing account password settings                           |
|                                        |                                                              |
| Usermod -L \<username\>                | Lock a user                                                  |
| Usermod -U \<username\>                | Unlock a user                                                |
| Usermod -d \<username\>                | Change the default home directory (with -m : move the current directory of that user) |
|                                        |                                                              |
| Userdel -r                             | Deleting a user including all the files (homefolder)         |
| **Groups**                             |                                                              |
| Groups \<username\>                    | Showing where a user is member off                           |
| Groupadd \<group name\>                | Adding a group                                               |
| /etc/gshadow                           | File where group passwords are stored                        |
|                                        |                                                              |
| Groupmod \<group name\>                | Modify a group                                               |
| Groupdel \<group name\>                | Deleting a group                                             |
| Newgrp                                 | Changing form a group in the current shell                   |
| Gpasswd                                | Change a group password                                      |
| chfn                                   | Change personal information (5th field /etc/passwd)          |
|                                        |                                                              


| **Creating a user / group**                    |                                                              |
| ---------------------------------------------- | ------------------------------------------------------------ |
| /etc/login.defs                                | Config file that has been used to store default variables for users etc. |
| Useradd \<username\>                           | Adding a user                                                |
| Passwd \<username\>                            | Changing the password of the user                            |
| Usermod -aG \<groupname\> \<username\>         | Append a user to a group                                     |
| Usermod \<username]> -d \<newhomedirectory\>   | Changing the default homedirectors for a user **excluding** copying the old homefolder data! |
| Usermod \<username\> -m -d <newhomedirectory\> | Changing the default homedirectors for a user **including** copying the old homefolder data! |
| groupmems -g \<groupname\> -l                  | Showing which users a member of a group                      |


