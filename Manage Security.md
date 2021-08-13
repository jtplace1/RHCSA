Manage Security

# Manage Security

- 
- Create and use file access control lists
- 
- Set enforcing and permissive modes for SELinux
- List and identify SELinux file and process context
- Restore default file contexts
- Use boolean settings to modify system SELinux settings
- Diagnose and address routine SELinux policy violations

| **Configure firewall settings using firewall-cmd/firewalld**                             |                                                         |
| ----------------------------------------- | ------------------------------------------------------- |
| Firewall-cmd —add-service=http —permanent | Add a service                                           |
| firewall-cmd —add-port=80/tcp —permanent  | Add a port                                              |
| firewall-cmd —reload                      | Reload the firewall                                     |
| firewall-cmd —list-services               | Show witch services are allowed throughout the firewall |
| firewall-cmd —list-ports                  | Show all the ports that are been enabled                |
| Systemctl status firewalld.service        | Show the status of the firewall Deamon                  |


| **Selinux**                                          |                                         |
| ---------------------------------------------------- | --------------------------------------- |
| Semanage port -l                                     | List of all the ports                   |
| semanage port -a -t http_port_t -p tcp 90            | Change the default http port to port 90 |
| Getsebool -a                                         |                                         |
| Setsebool -P \<boolean name\> (from getsebool) on/of |                                         |
| yum install selinux-policy-doc                       |                                         |
|                                                      |                                         |

| **Selinux**  |                            |
| ------------ | -------------------------- |
| sestatus     | Show the status of selinux |
| Setenforce 0 | Set selinux to permissive  |
| Setenforce 1 | Set selinux to enforced    |
|              |                            |

| **Configure key-based authentication for SSH**                             |                                                     |
| ------------------------------------------- | --------------------------------------------------------- |
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
| Ssh-keygen -t rsa -b 4096                                    | Creating a key pair (private and public) in the root folder ~/.ssh |
| Ssh folder 700                                               |                                                              |
| Contents in ssh folder 600                                   |                                                              |
| Ssh-copy-id [root@192.168.82.128](mailto:root@192.168.82.128) | Copy the public key to a different host                      |

