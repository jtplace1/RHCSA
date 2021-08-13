Configure local storage

# Configure local storage

 - List, create, delete partitions on MBR and GPT disks
- Create and remove physical volumes
- Assign physical volumes to volume groups
- Create and delete logical volumes
- Configure systems to mount file systems at boot by universally unique ID (UUID) or label
- Add new partitions and logical volumes, and swap to a system non-destructively


| **Storage**                        |                                                              |
| ---------------------------------- | ------------------------------------------------------------ |
| Df -h                              | Show info about the file system (total space and available space) |
| Df -hT                             | Show info about the file system (total space and available space) and the filesystem type |
| Du                                 | Showing disk usage by directory                              |
| Iostat                             | Show disk statystics by partition                            |
| Lsblk                              | Show current partitions sizes and mounting points            |
| fdisk -l                           | Show all physical disk (MBR partition scheme (BIOS))         |
| fdisk -d                           | Delete a partition (MBR partition scheme (BIOS))             |
| gdisk -l                           | Show all physical disk (GPT partition scheme (UEFI))         |
| gdisk -d                           | Delete a partition (GPT partition scheme (UEFI))             |
|                                    |                                                              |
|                                                            |
| **Mount**                          |                                                              |
| Mount -t ext4 /dev/sdb1 /media/usb | Mounting device /dev/sdb1 to /media/usb                      |
| /etc/fstab                         | For automatic mounting drives when the system boots          |
| /etc/mtab                          | Showing all the current mounted volumes                      |
|                                    |                                                              |

| **Mounting** |                                                              |
| ------------ | ------------------------------------------------------------ |
| Mount        | Show all the current mounts                                  |
| findmnt      | Show all the current mounts with its relations               |
| Df -Th       | Show all available disk space with the system mounts (including the filesystem) |
|              |                                                              |


| **Swap**                                                     |                                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| First create a LV disk that you want to enable for swap with Lvcreate ! |                                                              |
| Parted /dev/vg_disk/lv_disk2                                 |                                                              |
| ![image-20210123122356112](images/RHCSA8_notes/image-20210123122356112.png) |                                                              |
| Mkswap /dev/vdb1                                             | Makeswap partition                                           |
| Free -m                                                      | Showing how many swap space there is before                  |
| Swapon /dev/vdb1                                             | Enable the swap partition                                    |
| Free -m                                                      | Showing how many swap space there is now                     |
| /etc/fstab <br />![image-20210123122425808](images/RHCSA8_notes/image-20210123122425808.png) | Enable to the /etc/fstab                                     |
| Mount -a                                                     |                                                              |
| Ls -l /dev/mapper                                            | Dm-0 etc. should be the names corresponding to the output of swapon -s |
