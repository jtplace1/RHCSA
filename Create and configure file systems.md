Create and configure file systems


# Create and configure file systems
- Create and configure set-GID directories for collaboration
- Configure disk compression
- Manage layered storage

| **Folders** |                                                              |
| ----------- | ------------------------------------------------------------ |
| /etc/       | Config files                                                 |
| /var/       | Files that frequent change                                   |
| /dev/       | Device file location                                         |
| /proc/      | Provides all the info about the processes (Virtual)          |
| /sys        | Stores all the modifications to devices (Virtual)            |
| /lib/       | Stores al the binaries files                                 |
| /usr/       | all system-wide, read-only files installed by (or provided by) the OS |


|**Create, mount, unmount, and use vfat, ext4, and xfs file systems**||
| ----------------------------------------------- | ------------------------------------------------------------ |
| **EXT**                                         |                                                              |
| Ext2                                            |                                                              |
| Ext3 (standard)                                 | Has journaling                                               |
| Ext4                                            | Has journaling + bigger drive supports (up to 32TB drives)   |
|                                                 |                                                              |
| **MKFS**                                        |                                                              |
| Mkfs -t ext3 /dev/xvdf                          | Make filesystem                                              |
| Mkfs -t ext3 /dev/xvdf -m 25 -c                 | -m: reserved space for a crash (default is 5%) -c: check if the blocks are good on the drive |
|                                                 |                                                              |
| **SWAP**                                        |                                                              |
| dd if=/dev/zero of=/swap.swp bs=1024 count=800k | Creating a swap file                                         |
| Mkswap swap.swp                                 | Make swapfile                                                |
| Swapon swap.swp                                 | Enable swapfile                                              |
| Edit fstab file! /etf/fstab                     |                                                              |
| Swapoff -a                                      | Disables all swapfiles (based on fstab file)                 |

|**Diagnose and correct file permission problems**||
| ------------------------ | ------------------------------------------------------------ |
|      getfacl        |                                                              |
|  **setfacl** |                          |
|   setfacl -m u:testuser:rwx filename   |         add ACL permissions for user                                |
|     setfacl -x u:testuser file        |                     remove ACL persmissions for user                       |
|    setfacl -b filename              |                       remove all ACL permissions                       |
|   setfacl -d -m u:testuser:rwx directory | add defualt ALC permissions to new file created for that user        |
|   setfacl -k directory        |         remove default ACL on directory                            |
|   getfacl file1 \|\ setfacl --set-file=- file2 |          copy the ACL permissions of one file to another             |


| **Mount and unmount network file systems using NFS**    |                                                       |
| --------------------------------------------------------| ----------------------------------------------------- |
| Show mount -e \<IP address of the server\>       | Showing witch directories are available to make a connection to |
| mount 192.168.82.132:/var/share /var/share                   | Mounting the share                                 |
| 192.168.82.132:/var/share	/var/share/	nfs	defaults	0 0 | Add this row to the /etc/fstab/                          |
| Umount /var/share                                            | Unmount the share on the client                     |
| mount                                                        | Show all the current mounts                        |
| **AutoFS NFS Share**                                         |                                                  |
| Yum install autofs                                           |                                                 |
| Systemctl enable —now autofs                                 |                                                    |
| Vi /etc/auto.master                                        |                                             |        |Vi /etc/auto.home                                            |                                                      |


| **Extend existing logical volumes**                  |                                |
| -------------------------------------- | ------------------------------ |
| Lvextend -L +1GB /dev/vg_disk/lv_disk3 | Extend the filesystem with 1GB |
| resize2fs /dev/vg_disk/lv_disk         | Resize the filesystem          |

