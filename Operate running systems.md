Operate running systems

# Operate running systems

- Boot, reboot, and shut down a system normally
- Boot systems into different targets manually
-  Interrupt the boot process in order to gain access to a system
-  Identify CPU/memory intensive processes and kill processes
-  Adjust process scheduling
- Manage tuning profiles
- Locate and interpret system log files and journals
- Preserve system journals
- Start, stop, and check the status of network services
- Securely transfer files between systems

**Grub**

| **Grub**                               |                                                              |
| -------------------------------------- | ------------------------------------------------------------ |
| Boot legacy                            | Location: /boot/grub/menu.lst                                |
| Grub2                                  | Location: /boot/grub2/grub.cfg (BIOS) Location: /boot/efi/EFI/distro-name/grub.cfg (UEFI) |
|                                        |                                                              |
| /etc/default/grub                      | Changing settings for grub                                   |
| Grub2-mkconfig -o /boot/grub2/grub.cfg | Making a config for grub2                                    |



**Booting**



Memory:

Show active partition where the swapfile is stored:

- Swapon -s

Get information about the usage of virtual memory:

\- vmstat

Root 


| **Root password reset:**                                     |                                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Press “e” on boot menu                                       |                                                              |
| Add rd.break to the linux line  | The rd.break parameter interrupts the boot process before the control is passed over to the kernel. |
| Cntrl x<br />![image-20210123122022764](images/RHCSA8_notes/image-20210123122022764.png) |                                                              |
|                                                              |                                                              |
|                                                              |                                                              |




| **Syslog / Logging**                                         | **Port 514**                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Rsyslogd                                                     | /etc/rsyslogd.conf and /etc/rsyslog.d directory              |
| Rsyslog                                                      | Facility -> level -> action ofwel facility.level action   **Facility:** Type of application / service **Level:** Debug, informational etc. |
| *. * @192.168.10.254:514                                     | Append this to /etc/rsyslog.conf to enable remote logging    |
| Logrotate                                                    | Archiving logs based ont the /etc/logrotate.conf             |
| Systems-cat                                                  | Creating manual log entries in the syslog (alternative for logger) |
| logger                                                       | Creating manual log entries in the syslog                    |
| DINWECAP (7: debug, 6: infom, 5: notice 4: warning, 3: error, 2: critical, 1: alert, 0: panic) | Syslog levels                                                |
| Journalctl                                                   | /var/log/journal stores the files                            |
| Journalctl -f                                                | The same as tail -f                                          |
| Journalctl -u <system d process>                             | Show logging a systemd process                               |
| Journalctl -r                                                | Show all the newest messages (on the top) r stands for reverse |
| Journalctl -e                                                | Show the end of the journal                                  |
|                                                              | ![image-20210123124240928](../../images/LPIC_notes/image-20210123124240928.png) |
|                                                              | ![image-20210123124255862](../../images/LPIC_notes/image-20210123124255862.png) |




| **Journald Log persistant**                                  |                               |
| ------------------------------------------------------------ | ----------------------------- |
| Mkdir -p /var/log/journal                                    |                               |
| vi  [/etc/systemd/journald.conf](https://www.freedesktop.org/software/systemd/man/journald.conf.html) | Edit the journald config file |
| #Storage=auto -> Storage=persistent                          |                               |
| systemctl restart systemd-journald                           | Restart the journald config   |
|                                                              |                               |





