Deploy, configure, and maintain systems

# Deploy, configure, and maintain systems

- Schedule tasks using at and cron
- Start and stop services and configure services to start automatically at boot
- Configure systems to boot into a specific target automatically
- Configure time service clients
- Install and update software packages from Red Hat Network, a remote repository, or from the local file system
- Work with package module streams
- Modify the system bootloader


 **Package**              |                                                              |
| ------------------------ | ------------------------------------------------------------ |
| **RPM**                  | Red Hat based machines (CentOS, Red Hat, YellowDog, Suse, Fedora) |
| Rpm -i dropbox.dpkg      | Installes package                                            |
| Rpm -qi dropbox.dpkg     | Information about package                                    |
| Rpm -q —list dropbox     | Finding files that are installed by a package                |
| Rpm -qR dropbox          | Query al the requirements that the package needs             |
| Rpm -qI dropbox          | Verify that a package has been installed                     |
| Rpm -qa                  | Show all installed rpm packages                              |
|                          |                                                              |
| **YUM**                  |                                                              |
| /etc/yum.repos.d         | Repo’s folder                                                |
| /etc/yum.conf            | Yum config file                                              |
| Yum update               | Update repo db                                               |
| Yum search httpd         | Search for a package                                         |
| Yum install httpd        | Installes package                                            |
| Yum check-update httpd   | Checks for update of a package                               |
| Yum uppgrade             | Upgrade all packages                                         |
| Yum remove httpd         | remove package                                               |
| Yum list httpd           | Show information about installed package                     |
| Yum deplist httpd        | Show all the dependecys of a package                         |
| Yum clean                | Clear yum cache                                              |



Process:

| **Processes (top)**                                         |                                                              |
| ----------------------------------------------------------- | ------------------------------------------------------------ |
| Top                                                         | Load Average: 1 - 5 - 15 (minutes)                           |
| Shift M                                                     | Sort on Memory utilisation                                   |
| Shift P                                                     | Sort on CPU utilisation                                      |
| R (Renice value, Change priority of the process (-20 to 19) | Values -20 to 19                                             |
| K (15: Quit), 9 Force Quit                                  | Kill process                                                 |
|                                                             |                                                              |
| Nice -n 10 bash test.sh                                     | Running the script in the bash terminal with nice level 10   |
| Renice 15 -p 1949                                           | Changing the nice value of the process 1949 (can find it through ps command) |
| Kill \<pid id\>                                             | Kill a process (default: 15 TERM)                            |
| Kill -s Kill \<pid id\>                                     | Kills a process                                              |
| Kill -9 \<pid id\>                                          | Force quit a process                                         |





|

| **Hardware**               |                                                              |
| -------------------------- | ------------------------------------------------------------ |
| lsdev                      | Showing all the devices installed on the system              |
| lsblk                      | Showing al the block devices                                 |
| lspci                      | Showing al the pci cards                                     |
| lsusb                      | Showing al the usb devices                                   |
| **Modules**                |                                                              |
| lsmod                      | Showing al the modules that are installed                    |
| modinfo \<module name\>    | Showing info about a module                                  |
| insmod \<module name.ko\>  | Install a module (can find it in /lib/modules)               |
| modprobe \<module name\>   | Install a module (can find it in /lib/modules) + all the dependencies |
| modpobe -r \<module name\> | Removes the module                                           |


| **Cronjob**                                                | **Runs a command regularly and repeatedly at a given time**  |
| ---------------------------------------------------------- | ------------------------------------------------------------ |
| Crontab -l                                                 | Show all the cronjobs from the current user                  |
| Crontab -e                                                 |                                                              |
| Minute - hour - day of the month - month - day of the week |                                                              |
| /etc/cron.allow                                            | If the /etc/cron.allow file exists, then you must be listed (one user per line) therein in order to be allowed to use this command. |
| /etc/cron.deny                                             | If the /etc/cron.allow file does not exist but the /etc/cron.deny file does exist, then you must not be listed in the /etc/cron.deny file in order to use this command. |
|                                                            | If both files exist then /etc/cron.allow takes precedence. Which means that /etc/cron.deny is not considered and your user must be listed in /etc/cron.allow in order to be able to use the crontab. |
| /var/spool/cron                                            | User specific cron jobs are stored here                      |
|                                                            | Minutes 0-59 Hours 0-23 Days of month 0-31 Months 1-12 Days of week 0-7 command with options and parameters |

| **At**             | **Runs commands once at a given time**          |
| ------------------ | ----------------------------------------------- |
| Atq or at -l       | Showing al the job at jobs                      |
| Atrm <job number>  | Delete a at job                                 |
| At -d <job number> | Delete a at job                                 |
| Cntrl-D            | Enter at the end of the list of the At commands |
| /etc/at.allow      | Allow users to use At                           |
| /etc/at.deny       | Deny users to use at                            |





| **Services**                             |                                                             |
| ---------------------------------------- | ----------------------------------------------------------- |
| SysV                                     | /etc/init.d                                                 |
| /etc/inittab                             | SysV uses this configfile                                   |
|                                          |                                                             |
| Systemd                                  | /usr/lib/systemd/                                           |
| /usr/lib/systemd/system/                 | Systemd uses this folder                                    |
| /usr/lib/systemd/system/default.target e |                                                             |
| Systemctl get-default                    | Show what your default target is                            |
| stat /proc/1/exe                         | Check if you are running SysV or Systems                    |
| systemctl list-unit-files                | Showing witch services are started when the system boots    |
| systemctl \| grep running                | Showing witch services are currently running on the machine |



| **Packages**                       |                                                              |
| ---------------------------------- | ------------------------------------------------------------ |
| Yum info nmap                      | Show info about a package                                    |
| Yum list \| less                   | Show all the installed packages                              |
| Yum groups list                    | Show all the groups that are available te install            |
| Yum groups info “Basis Web Server” | Show which packages are in the group basic web server        |
|                                    |                                                              |
| Yum history                        | Show which packages you installed en when                    |
| Yum history undo \<number\>        | Undo the action that take place (show info through yum history) |
|                                    |                                                              |

id: a3a51ec43c3d4b9eafdd9b1d42d8d3ed
parent_id: 3c240cf25d284d35a70da82bc0bf33e6
created_time: 2021-07-10T16:55:38.471Z
updated_time: 2021-08-12T18:58:03.131Z
is_conflict: 0
latitude: 33.94020000
longitude: -84.53950000
altitude: 0.0000
author: 
source_url: 
is_todo: 1
todo_due: 0
todo_completed: 0
source: joplin-desktop
source_application: net.cozic.joplin-desktop
application_data: 
order: 1625936194386.3125
user_created_time: 2021-07-10T16:55:38.471Z
user_updated_time: 2021-08-12T18:58:03.131Z
encryption_cipher_text: 
encryption_applied: 0
markup_language: 1
is_shared: 0
share_id: 
conflict_original_id: 
type_: 1