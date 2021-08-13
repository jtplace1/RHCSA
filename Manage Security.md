Manage Security

# Manage Security

- Configure firewall settings using firewall-cmd/firewalld
- Create and use file access control lists
- Configure key-based authentication for SSH
- Set enforcing and permissive modes for SELinux
- List and identify SELinux file and process context
- Restore default file contexts
- Use boolean settings to modify system SELinux settings
- Diagnose and address routine SELinux policy violations

| **Firewalld**                             |                                                         |
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

